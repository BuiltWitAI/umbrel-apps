# Multi-stage Dockerfile for All is Cubes web version
# Builder stage: Rust + wasm-pack to build the WASM client
FROM rust:1.96-slim AS builder

# Install system dependencies for building
RUN apt-get update && apt-get install -y \
    curl \
    git \
    pkg-config \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

# Install wasm-pack and cargo-about
RUN cargo install --locked wasm-pack@0.14.0 cargo-about@0.8.2

# Set working directory
WORKDIR /app

# Copy the entire workspace (needed for workspace dependencies)
COPY . .

# Build the web release (this runs cargo xtask build-web-release)
# We need to build xtask first, then run build-web-release
RUN cargo build --package xtask
RUN cargo xtask build-web-release

# Runtime stage: nginx to serve static files
FROM nginx:alpine AS runtime

# Copy the built static files from builder
COPY --from=builder /app/all-is-cubes-wasm/target/web-app-release /usr/share/nginx/html

# Copy nginx config
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
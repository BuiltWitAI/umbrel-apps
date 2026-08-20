# Multi-stage Dockerfile for Stockfish Chess Web GUI
# Build stage: Use Bun to build the project
FROM oven/bun:1.3 AS builder

WORKDIR /app

# Copy package files
COPY package.json bun.lock ./

# Install dependencies
RUN bun install --frozen-lockfile

# Copy source files
COPY . .

# Build for production
RUN bun run build

# Runtime stage: nginx to serve static files with COOP/COEP headers
FROM nginx:alpine AS runtime

# Copy built files from builder
COPY --from=builder /app/dist /usr/share/nginx/html

# Copy nginx config with COOP/COEP headers for SharedArrayBuffer
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
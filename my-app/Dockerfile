# Étape de build avec Node
FROM node:20 AS builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run prebuild && npm run build

# Étape de runtime avec Bun
FROM oven/bun:latest
WORKDIR /app
COPY --from=builder /app .
CMD ["bun", "start"]

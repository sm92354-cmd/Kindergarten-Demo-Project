# Build stage
FROM golang:1.23-alpine AS builder

# Set working directory
WORKDIR /app

# Copy Go dependency files
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy application source code
COPY . .

# Build Go application
RUN CGO_ENABLED=0 GOOS=linux go build -o student-service .

# Final stage
FROM alpine:latest

# Set working directory
WORKDIR /app

# Copy compiled application
COPY --from=builder /app/student-service .

# Expose application port
EXPOSE 5001

# Start application
CMD ["./student-service"]
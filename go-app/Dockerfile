# Use the official Go image as the base image
FROM golang:1.17-alpine as builder

# Set the working directory
WORKDIR /app

# Copy the Go application files to the working directory
COPY main.go .

# Initialize Go modules
RUN go mod init myapp

# Build the Go application
RUN go build -o main .

# Use a minimal Alpine Linux image as the final base image
FROM alpine:latest

# Copy the compiled binary from the builder image
COPY --from=builder /app/main /app/main

# Expose port 8080 to the outside world
EXPOSE 8080

# Command to run the Go application
CMD ["/app/main"]


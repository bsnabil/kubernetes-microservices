# Use the official Golang image as the base image
FROM golang:1.20 as builder

# Set the working directory inside the container
WORKDIR /app

# Copy go mod and sum files
COPY Gopkg.toml Gopkg.lock ./

# Download the dependencies
RUN go mod download

# Copy the rest of the application files
COPY . .

# Build the Go application
RUN go build -o myapp main.go

# Use a smaller image for the final build
FROM alpine:latest

# Set the working directory in the new image
WORKDIR /root/

# Copy the compiled binary from the builder stage
COPY --from=builder /app/myapp .

# Command to run the application
CMD ["./myapp"]


# Build stage
FROM golang:1.22.5 AS build
WORKDIR /app
COPY . .
RUN go build -o main .
RUN ls -la /app  # Check if the binary is created
RUN chmod +x /app/main  # Ensure the binary is executable

# Final image
FROM scratch
COPY --from=build /app/main /app/main
USER 1001:1001
EXPOSE 8080
CMD ["./main"]


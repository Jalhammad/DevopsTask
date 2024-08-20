#Biuld stage
FROM golang:1.22.5 AS build
WORKDIR /app
COPY . .
RUN go build -o main .

 
 
#finale image
FROM scratch
COPY --from=build /app/main /app/main
USER 1001:1001
EXPOSE 8080
CMD ["./main"]


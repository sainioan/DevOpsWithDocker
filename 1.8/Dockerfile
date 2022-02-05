FROM ubuntu:20.04
RUN apt-get update && apt-get install -y curl
WORKDIR /app
COPY script.sh .
RUN chmod +x /app/script.sh
CMD /app/script.sh

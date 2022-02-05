RUN apt-get update && apt-get install -y curl
WORKDIR /app
COPY script.sh .
RUN chmod +x /app/script.sh
CMD ["/app/script.sh"]# Start from the alpine image that is smaller but no fancy tools
FROM  ubuntu:20.04
RUN apt-get update; apt-get install -y curl;
CMD echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;


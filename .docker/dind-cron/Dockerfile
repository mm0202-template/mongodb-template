FROM docker:dind

RUN echo '0 3 * * * docker exec -t sample_mongo mongodump --host="localhost:27017" -o /backup/`date "+%Y%m%d_%H%M%S"` -u=$MONGO_USERNAME -p=$MONGO_PASSWORD' >> /etc/crontab

RUN crontab /etc/crontab
CMD ["sh", "-c", "crond -f"]

FROM node:16.15-alpine3.14
RUN mkdir -p /opt/app
WORKDIR /app
COPY package*.json .
RUN adduser -S app
COPY / .
RUN npm i
RUN chown -R app /opt/app
USER app
EXPOSE 3000
# ENTRYPOINT [ "./start.sh" ]
CMD [ "npm", "start" ]

# "dcstart.sh"


# USER root
# RUN chmod +x docker-compose.yml
# RUN chmod +x start.sh


# COPY start.sh /entrypoint.sh
# RUN chmod u+x /entrypoint.sh


# USER app
FROM mongo:5.0
# Will be set through Environment Files
ARG DATABASE_URI
ARG USERNAME
ARG PASSWORD

ENV DATABASE_URI ${DATABASE_URI}
ENV USERNAME ${USERNAME}
ENV PASSWORD ${PASSWORD}

COPY comments.json /comments.json
COPY movies.json /movies.json
COPY sessions.json /sessions.json
COPY theaters.json /theaters.json
COPY users.json /users.json

CMD mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection comments --drop --file /comments.json && \
    mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection movies --drop --file /movies.json && \
    mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection sessions --drop --file /sessions.json && \
    mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection theaters --drop --file /theaters.json && \
    mongoimport --username ${USERNAME} --password ${PASSWORD} --uri ${DATABASE_URI} --collection users --drop --file /users.json



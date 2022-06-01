FROM node

COPY . /server/

RUN cd server && \
    npm install

WORKDIR /server/

CMD npm start
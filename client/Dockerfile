FROM node AS builder

COPY . /client/

RUN cd client && \
    npm install && \
    npm run build

FROM nginx

RUN rm -rf /usr/share/nginx/html/*

COPY --from=builder /client/public/ /usr/share/nginx/html/

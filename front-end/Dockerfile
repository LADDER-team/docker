FROM node:10.5.0 as builder
WORKDIR /root/ladder
ARG GIT_REF=master
EXPOSE 80
RUN git clone -b ${GIT_REF} "https://github.com/LADDER-team/ladder-web-server.git" /root/ladder && \
    npm install && \
    npm run build

FROM nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=builder /root/ladder/dist /usr/share/nginx/html

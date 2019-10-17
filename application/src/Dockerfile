FROM node:10
RUN mkdir -p /code
COPY . /code/
WORKDIR /code
RUN yarn install
CMD ["yarn","serve"]
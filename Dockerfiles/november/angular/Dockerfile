FROM node:16
LABEL project="practice"
LABEL author="test"
RUN git clone https://github.com/gothinkster/angular-realworld-example-app.git
RUN cd angular-realworld-example-app && \
npm install -g @angular/cli -y && \
 npm install -y
EXPOSE 4200
WORKDIR /angular-realworld-example-app
CMD ["ng", "serve", "--host", "0.0.0.0"]
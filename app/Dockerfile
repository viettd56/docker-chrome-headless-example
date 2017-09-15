FROM ubuntu:14.04.5
USER root
RUN apt-get update --fix-missing
RUN apt-get install -y build-essential make g++ curl libfontconfig python curl wget unzip git
RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
RUN apt-get install -y nodejs
# Install Chrome for Ubuntu
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add - &&\
sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list' &&\
sudo apt-get update --fix-missing
RUN sudo apt-get install -y google-chrome-stable
WORKDIR /src
COPY ./index.js /src
COPY ./package.json /src
RUN npm install
ENTRYPOINT ["node"]
CMD ["index.js"]

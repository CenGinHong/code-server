FROM codercom/code-server:latest


RUN sudo sed -i "s/deb.debian.org/mirrors.aliyun.com/g" /etc/apt/sources.list   && \
sudo apt-get -y update && \
sudo apt-get -y upgrade

COPY ./vs-demo-0.0.2.vsix /data/
RUN sudo apt-get install -y python3.9 python3-pip  && \
sudo /usr/bin/code-server --install-extension /data/vs-demo-0.0.2.vsix && \
sudo /usr/bin/code-server --install-extension ms-python.python && \
sudo /usr/bin/code-server --install-extension formulahendry.code-runner \


EXPOSE 8080
WORKDIR /home/coder/project
ENTRYPOINT ["/usr/bin/entrypoint.sh", "--bind-addr", "0.0.0.0:8080", "."]

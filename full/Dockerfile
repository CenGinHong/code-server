FROM codercom/code-server:latest

RUN sudo sed -i "s/deb.debian.org/mirrors.aliyun.com/g" /etc/apt/sources.list   && \
sudo apt-get -y update && \
sudo apt-get -y upgrade


COPY ./vs-demo-0.0.1.vsix /data/
RUN sudo apt-get -y install g++ default-jdk maven gradle python3.9 python3-pip  && \
sudo /usr/bin/code-server --install-extension /data/vs-demo-0.0.1.vsix && \
sudo /usr/bin/code-server --install-extension vscjava.vscode-java-pack && \
sudo /usr/bin/code-server --install-extension formulahendry.code-runner && \
sudo /usr/bin/code-server --install-extension ms-python.python && \
sudo /usr/bin/code-server --install-extension ms-vscode.cpptools

EXPOSE 8080
WORKDIR /home/coder/project
ENTRYPOINT ["/usr/bin/entrypoint.sh", "--bind-addr", "0.0.0.0:8080", "."]

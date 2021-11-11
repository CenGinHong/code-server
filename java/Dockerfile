FROM codercom/code-server:latest

RUN sudo sed -i "s/archive.ubuntu./mirrors.aliyun./g" /etc/apt/sources.list  && \
sudo apt-get -y update && \
sudo apt-get -y upgrade && \
sudo apt-get -y install default-jdk maven gradle

COPY ../vs-demo-0.0.1.vsix /data/
RUN sudo /usr/bin/code-server --install-extension /data/vs-demo-0.0.1.vsix && \
sudo /usr/bin/code-server --install-extension vscjava.vscode-java-pack
EXPOSE 8080
# WORKDIR /home/coder/project
ENTRYPOINT ["/usr/bin/entrypoint.sh", "--bind-addr", "0.0.0.0:8080", "."]

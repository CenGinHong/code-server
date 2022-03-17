FROM codercom/code-server:latest

RUN sudo sed -i "s/archive.ubuntu./mirrors.aliyun./g" /etc/apt/sources.list  && \
sudo apt-get -y update && \
sudo apt-get -y upgrade

COPY ./vs-demo-0.0.2.vsix /data/
RUN sudo apt-get -y install default-jdk maven gradle && \
sudo /usr/bin/code-server --install-extension /data/vs-demo-0.0.2.vsix && \
sudo /usr/bin/code-server --install-extension vscjava.vscode-java-pack
EXPOSE 8080
# WORKDIR /home/coder/project
ENTRYPOINT ["/usr/bin/entrypoint.sh", "--bind-addr", "0.0.0.0:8080", "."]

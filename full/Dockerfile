FROM codercom/code-server:latest

EXPOSE 8080
WORKDIR /home/coder/project
ENTRYPOINT ["/usr/bin/entrypoint.sh", "--auth", "none", "--bind-addr", "0.0.0.0:8080", "."]

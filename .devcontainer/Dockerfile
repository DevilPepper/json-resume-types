# Using Dockerfile because mounting vscode volumes gives permission denied...
FROM ghcr.io/supastuff/node:14-alpine3.12

ARG USERNAME=node

RUN mkdir -p /home/$USERNAME/workspace/node_modules \
        /home/$USERNAME/.vscode-server/extensions \
        /home/$USERNAME/.vscode-server-insiders/extensions \
 && chown -R $USERNAME \
        /home/$USERNAME/workspace \
        /home/$USERNAME/.vscode-server \
        /home/$USERNAME/.vscode-server-insiders

COPY entrypoint.sh /bin/entrypoint.sh
RUN chmod +x /bin/entrypoint.sh

USER $USERNAME

ENTRYPOINT ["/bin/entrypoint.sh"]

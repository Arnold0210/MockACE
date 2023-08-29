FROM arnold9810/mqserver:latest
USER root
ARG IMAGE_VERSION
ENV IMAGE_VERSION=$IMAGE_VERSION
RUN sed -i 's/\r//' /usr/local/bin/init_script.sh && chmod +x /usr/local/bin/init_script.sh
USER 1001
ENTRYPOINT ["/usr/local/bin/init_script.sh"]

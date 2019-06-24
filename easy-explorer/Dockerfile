FROM arm64v8/debian:stable-slim

COPY easy-explorer-arm /usr/bin/

ENV key 054df45e-4bc9-4c5c-a5a0-35257a168747

RUN set -ex && \
    mkdir /Data && \
    chmod +x /usr/bin/easy-explorer-arm

#CMD ["easy-explorer-arm", "-u", "054df45e-4bc9-4c5c-a5a0-35257a168747", "-share", "/Data"]
#CMD ["/bin/bash", "-c", "easy-explorer-arm -u $key -share /Data"]
CMD easy-explorer-arm -u $key -share /Data

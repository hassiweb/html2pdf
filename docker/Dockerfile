FROM pink33n/html-to-pdf:79.1

RUN apk update \
 && apk add --no-cache \
        wget \
        zip

# Install Noto font that supports Japanese
RUN wget https://noto-website.storage.googleapis.com/pkgs/Noto-unhinted.zip \
 && unzip -d NotoSansJapanese Noto-unhinted.zip \
 && mkdir -p /usr/share/fonts/opentype \
 && mv -fv ./NotoSansJapanese /usr/share/fonts/opentype/NotoSansJapanese \
 && rm -rfv Noto-unhinted.zip \
 && fc-cache -fv    

ENTRYPOINT ["/bin/bash", "/usr/local/bin/entrypoint"]
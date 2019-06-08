# How to use it

```
FROM python:3.6-alpine3.8

...

# proj4-4.9.3-r0.apk | proj4-dev-4.9.3-r0.apk
COPY --from=baffolobill/alpine-proj4-multistage:latest /home/packager/packages/x86_64/proj4-4.9.3-r0.apk /tmp/proj4.apk
COPY --from=baffolobill/alpine-proj4-multistage:latest /home/packager/packages/x86_64/proj4-dev-4.9.3-r0.apk /tmp/proj4-dev.apk

RUN \
    apk add /tmp/proj4.apk --allow-untrusted && \
    apk add /tmp/proj4-dev.apk --allow-untrusted

...

```

# FIRST STAGE: Download Houdini
FROM python:3.11-slim AS houdini-downloader
WORKDIR /code
COPY . ./hinstall
ARG DL_URL
ENV SIDEFX_DL_URL=$DL_URL
ARG DL_NAME
ENV SIDEFX_DL_NAME=$DL_NAME
ARG DL_HASH
ENV SIDEFX_DL_HASH=$DL_HASH
RUN pip install --upgrade --no-cache-dir -r hinstall/requirements.txt
# Set the PYTHONPATH environment variable to include the hinstall directory
ENV PYTHONPATH=/code
RUN mkdir /houdini
RUN python3 hinstall/houinstall.py

# SECOND STAGE: Install and initialize Houdini
FROM debian:11-slim as hqueue-install

# Update and install required packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends iputils-ping netcat inetutils-telnet inetutils-ftp procps sudo && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN apt-get update && \
    apt-get install -y libglu1 libsm6 bc wget libnss3 libxcomposite1 libxrender1 libxrandr2 libfontconfig1 libxcursor1 libxi6 libxtst6 libxkbcommon0 libxss1 libpci3 libasound2 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY --from=houdini-downloader /houdini /houdiniInstaller
# Force progress on all optional queries
WORKDIR /houdiniInstaller/build/
RUN yes | ./hqueue.install --do-install --install-server --server-dir /opt/hqueue
RUN rm -r /houdiniInstaller

# THIRD STAGE: Copy houdini-install image and un-cache unnecessary installation files
FROM debian:11-slim
COPY --from=hqueue-install / /
EXPOSE 5000
CMD ["/opt/hqueue/python/bin", "/opt/hqueue/hqserver/manage.py", "serve"]

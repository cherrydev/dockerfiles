FROM microsoft/aspnetcore:1.1

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/azure-cli/ wheezy main" | tee /etc/apt/sources.list.d/azure-cli.list && \
    apt-key adv --keyserver apt-mo.trafficmanager.net --recv-keys 417A0893 && \
    apt-get update && \
    apt-get install --no-install-recommends -y apt-transport-https && \
    apt-get install --no-install-recommends -y \
        azure-cli \
        nodejs \
        libssl-dev \
        libffi-dev \
        python-dev \
        build-essential && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    apt-get autoremove -y && apt-get clean

RUN npm i -g --unsafe-perm bower && \
    echo '{ "allow_root": true }' > /root/.bowerrc

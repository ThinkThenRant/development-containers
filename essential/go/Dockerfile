FROM thinkthenrant/development-container-base:dev

ENV PATH /usr/local/go/bin:$PATH
ARG GO_VERSION=1.16.3
ARG MOCKERY_VERSION=2.5.1
RUN sudo apt-get update \
    # https://www.petefreitag.com/item/877.cfm
    && sudo DEBIAN_FRONTEND=noninteractive apt-get -y install --no-install-recommends wget
RUN sudo wget https://golang.org/dl/go${GO_VERSION}.linux-amd64.tar.gz && \
    sudo rm -rf /usr/local/go && \
    sudo tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz && \
    sudo rm go${GO_VERSION}.linux-amd64.tar.gz && \
    sudo wget https://github.com/vektra/mockery/releases/download/v${MOCKERY_VERSION}/mockery_${MOCKERY_VERSION}_Linux_x86_64.tar.gz && \
    sudo tar -C /usr/local/bin -xzf mockery_${MOCKERY_VERSION}_Linux_x86_64.tar.gz && \
    sudo rm mockery_${MOCKERY_VERSION}_Linux_x86_64.tar.gz && \
    go install github.com/uudashr/gopkgs/cmd/gopkgs@v2 && \
    go install github.com/ramya-rao-a/go-outline@latest && \
    go install github.com/fatih/gomodifytags@v1 && \
    go install github.com/josharian/impl@v1 && \
    go install github.com/haya14busa/goplay/cmd/goplay@v1 && \
    go install github.com/go-delve/delve/cmd/dlv@v1 && \
    go install honnef.co/go/tools/cmd/staticcheck@v0 && \
    go install golang.org/x/tools/gopls@v0

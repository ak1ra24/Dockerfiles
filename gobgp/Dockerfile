FROM akiranet24/frr

WORKDIR /root
ENV GO111MODULE on
ENV PATH $PATH:/root/go/bin

RUN apt install -y software-properties-common \
 && add-apt-repository ppa:longsleep/golang-backports \
 && apt update \
 && apt install -y golang-go

RUN git clone https://github.com/osrg/gobgp.git
RUN cd gobgp && go install ./cmd/gobgpd ./cmd/gobgp

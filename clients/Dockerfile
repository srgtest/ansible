FROM ubuntu:latest

RUN apt update && apt install -y software-properties-common \
    && add-apt-repository --yes --update ppa:deadsnakes/ppa \
    && apt install -y openssh-server python3.9 iputils-ping
RUN mkdir /home/ansible
COPY ./.ssh /root/.ssh
RUN chmod -R go= /root/.ssh && chown -R root:root ~/.ssh
COPY ./script.sh /home/ansible
WORKDIR /home/ansible
ENTRYPOINT ["/home/ansible/script.sh"]

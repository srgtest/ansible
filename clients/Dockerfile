FROM ubuntu:latest

RUN apt update && apt install -y software-properties-common \
    && add-apt-repository --yes --update ppa:deadsnakes/ppa \
    && apt install -y openssh-server python3.9 iputils-ping
RUN echo 'root:qwerty' | chpasswd
RUN mkdir /home/ansible
COPY ./script.sh /home/ansible
WORKDIR /home/ansible
ENTRYPOINT ["/home/ansible/script.sh"]

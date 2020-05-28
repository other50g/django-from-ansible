FROM ubuntu

ENV ANSIBLE_HOST_KEY_CHECKING False

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    # add-apt-repository ppa:ansible/ansible && \
    apt-get install -y rsync && \
    apt-get update && \
    apt-get install -y ansible curl

CMD /bin/bash

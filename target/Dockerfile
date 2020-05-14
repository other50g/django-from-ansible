# Amazon EC2
FROM amazonlinux:latest

# yumでOpenSSｈサーバをインストールする
RUN yum update -y && \
    yum -y install openssh-server && \
    yum -y install systemd-sysv

# sshd起動時に公開鍵が必要なため、作成
RUN ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa
RUN ssh-keygen -f /etc/ssh/ssh_host_ecdsa_key -N '' -t ecdsa

# rootでログインできるようにする
RUN sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config

# rootのパスワードを指定
RUN echo "root:" | chpasswd

# SSHのポート開放
EXPOSE 22
# HTTPのポート開放
EXPOSE 80
# PostgreSQLのポート開放
EXPOSE 5432

# sshdを起動
CMD ["/usr/sbin/sshd", "-D"]

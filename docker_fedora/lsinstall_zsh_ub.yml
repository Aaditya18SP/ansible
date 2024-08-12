FROM ubuntu

ARG user="adi"

RUN <<EOF
apt-get update
apt-get install -y sudo 
apt-get install -y git
apt-get install -y curl
apt install -y software-properties-common
add-apt-repository --yes --update ppa:ansible/ansible
apt install -y ansible
apt install -y vim
useradd -m -s /bin/bash ${user} && echo ${user}":password" | chpasswd && adduser ${user} sudo
EOF

USER ${user}
WORKDIR /home/${user}/


COPY --chown=${user} ./install_zsh_ub.yml /home/${user}/Ansible/

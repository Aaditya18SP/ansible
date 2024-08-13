FROM fedora 

ARG user="adi"

RUN <<EOF
echo "fastestmirror=true" >> /etc/dnf/dnf.conf
dnf update
dnf install -y git
dnf install -y ansible
dnf install -y vim
useradd -m -s /bin/bash ${user} && echo ${user}":password" | chpasswd && usermod -aG wheel ${user}
EOF

USER ${user}
WORKDIR /home/${user}/


COPY --chown=${user} ./ /home/${user}/Ansible/


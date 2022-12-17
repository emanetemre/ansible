FROM centos:latest
#epel-release için repolar
RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*

#Ansible ön kurulum gereksinimleri
RUN dnf -y update
RUN dnf -y install epel-release
RUN dnf -y install sudo

#Ansible Kurulumu
RUN sudo dnf install python3-pip -y
RUN pip3 install --upgrade --ignore-installed pip setuptools
RUN sudo python3 -m pip install ansible

#Ansible Kurulumunu Check Edelim
CMD ["ansible --version"]
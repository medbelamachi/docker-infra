FROM centos:latest


# EPEL & Kerberos
RUN cd /etc/yum.repos.d/ \
	&& sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* \ 
	&& sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* \ 
	&& yum update -y \ 
	&& yum install -y epel-release krb5-server krb5-libs krb5-workstation

EXPOSE 88 749

ADD ./config.sh /config.sh

ENTRYPOINT ["/config.sh"]

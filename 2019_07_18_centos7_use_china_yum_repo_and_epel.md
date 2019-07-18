
## yum install -y wget

## yum install -y vim

cd /etc/yum.repos.d/
mkdir repo.bak
mv *.repo ./repo.bak
wget -c http://mirrors.aliyun.com/repo/Centos-7.repo
wget http://mirrors.163.com/.help/CentOS7-Base-163.repo
ll
yum clean all
yum makecache

yum list | grep epel-release

yum install -y epel-release

ls

wget -c http://mirrors.aliyun.com/repo/epel-7.repo

ls

yum clean all

yum makecache

yum repolist enabled

yum repolist all



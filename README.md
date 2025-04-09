# linux-template
Necessary Bin to install for linux 

OS: debian
Required bin: net-tools, sudo, openssh-server, openssh-client

Todo:
$apt update -y && apt upgrade -y
$apt install net-tools sudo openssh-server openssh-client -y

Add user to /etc/sudoers in the line #User privilege specification
#admin ALL=(ALL:ALL) ALL

Edit /etc/network/interface
#  Iface ens192 inet static
#    address 10.1.254.151/24
#    gateway 10.1.254.254
#    dns-nameservers 1.1.1.1

Edit /etc/resolv.conf
#  nameserver 1.1.1.1

Optional: 
Edit /etc/ssh/sshd_config
#  PermitRootLogin prohibit-password

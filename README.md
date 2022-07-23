Centos 8 Configuration
-------------------------
    sudo -i
Enter root password if asked


### Enable Ethernet and connection
    nmcli dev status
    nmcli c
Check name and write it in next command instead of [ em1 ] of its different

    nmcli c up em1

check status again if green and connected

    nmcli dev status
    nmcli c

### "Failed to download metadata for repo AppStream"

    sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
    dnf update

Install SSH and open port

    dnf install openssh-server
    systemctl start sshd
    systemctl enable sshd
    systemctl status sshd

Ctrl + C To Quit , Then

    firewall-cmd --zone=public --permanent --add-service=ssh
    firewall-cmd --reload
    systemctl reload sshd


write the following command and send me screenshot

    ip a
    curl https://beshoy.me/ip.php

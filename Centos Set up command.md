### Check port state
```sudo lsof -i -P -n | grep LISTEN```</br>
```sudo netstat -tulpn | grep LISTEN```</br>
```sudo ss -tulpn | grep LISTEN```</br>
```sudo lsof -i:22 ## see a specific port such as 22 ##```</br>
```sudo nmap -sTU -O IP-address-Here```</br>

### Check and start Docker

**Start Docker service**</br>
```sudo systemctl start docker```</br>
**Check Docker start state**</br>
```sudo docker run hello-world```</br>
**Check docker state**</br>
```sudo docker ps```</br>
**Check all docker state**</br>
```sudo docker ps -a```</br>

### SET UP
sudo yum install sysv-rc-conf
sleep 10

sudo sysv-rc-conf
sleep 10

sudo yum update
sleep 10

sudo yum install net-tools -y
sleep 10

echo 0 >/proc/sys/net/ipv4/icmp_echo_ignore_all
sleep 10

sudo yum -y install openssh-server openssh-clients
sleep 10

sudo systemctl start sshd
sleep 10

#### install NTP
sudo yum install -y ntpdate
sleep 10

#### Set the NTP to HONG KONG
sudo ntpdate stdtime.gov.hk
sleep 10

https://support.nagios.com/kb/article/nrpe-check_nrpe-error-could-not-complete-ssl-handshake-615.html#NRPE_CFG
/home/tcn/software/vanda/nagios/nrpe-3.2.1
./configure --enable-ssl
make all
make instal

sudo chmod 755 /usr/local/nagios/libexec/ck_sfx_capacity
sudo killall nrpe
sudo /usr/local/nagios/bin/nrpe -d -c /usr/local/nagios/etc/nrpe.cfg
sh /usr/local/nagios/libexec/ck_sfx_capacity -w 25 -c 20

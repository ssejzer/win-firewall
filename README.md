# win-firewall
windows firewall management from command line

## export your original firewall rules:
netsh advfirewall export backup-original.wfw

## import custom rules:
netsh advfirewall import custom.wfw

## turn firewall on:
netsh advfirewall set allprofiles state on

## turn firewall off:
netsh advfirewall set allprofiles state off

## check status
netsh advfirewall show allprofiles

## disable incomming RDP
netsh advfirewall firewall set rule name="Remote Desktop - User Mode (TCP-In)" dir=in new action=block

## enable incomming RDP
netsh advfirewall firewall set rule name="Remote Desktop - User Mode (TCP-In)" dir=in new action=allow

## enable incomming RDP only from some IPs
netsh advfirewall firewall set rule name="Remote Desktop - User Mode (TCP-In)" dir=in new action=allow remoteip=157.60.0.1,172.16.0.0/16,LocalSubnet

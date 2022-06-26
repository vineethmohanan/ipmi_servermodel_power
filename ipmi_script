import os
import re
import subprocess
import time
import paramiko
IP_Hostfile= open("<Path of the Hostlist>","r")
serverlist=IP_Hostfile.read()
passwordlist=serverlist.split()
servers=serverlist.split("\n")
IP_Hostfile.close()
for hostname in hosts:
    try:
            ssh=paramiko.SSHClient()
            ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())
            ssh.connect("<IP of the Linux Host",username="<username>",password="<password>")
            ipreg="^((25[0-5][2[0-4][0-9]|[0-9][0-9]?[0-9])\.){3}(25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[1-9]?[0-9])$"
            if (re-search(ipreg,hostname)):
                power='ipmitool -I lanplus -H '+hostname+ ' -U <IDRAC/ILO/BMC username> -P <IDRAC/ILO/BMC Password> sdr list full|grep "Power" ,"pwr"'
                stdin,stdout,stderr = ssh.exec_command(power)
                outputpower= stdout.read()
                Model = 'ipmitool -I lanplus -H '+hostname+ ' -U <IDRAC/ILO/BMC username> -P <IDRAC/ILO/BMC Password> fru |grep -m 1 "Product Name"'
                stdin,stdout,stderr = ssh.exec_command(Model)
                outputmodel= stdout.read()
                Error = stderr.read()
                print('Hostname=',hostname,'OutputModel=',outputmodel,'Output_Power=',outputpower)
    except Exeception as e:
        print(e)
ssh.close()


###
Sample IP_Hostfile.txt file 
192.168.1.23
192.168.1.27

# KaliLinux-Build-Script-(will fix and make eventualy)
# Raw is the best way to read this for now!

-New Kali Install RUN:
sudo apt update 
*if kali is really out of date run: sudo wget https://archive.kali.org/archive-keyring.gpg -O /usr/share/keyrings/kali-archive-keyring.gpg
sudo apt upgrade
sudo apt autoremove 
sudo apt clean

-Download all wallpapers for Kali:
sudo apt install kali-wallpapers-all

-Wordlists that may be useful on pentests:
cd /usr/share/wordlists 
sudo apt install seclists
cd /usr/share/wordlists 
extracted rockyou.txt.gz file in /usr/share/wordlists to the same directory and kept both the .gz and .txt 

-Programs that may be useful on pentests:
sudo apt install keepassxc
sudo apt install fcrackzip

-Download Firefox Extensions
wapalizer
foxyproxy
Firefox Multi-Account Containers
Cookie-Editor         by cgagnier

-Turn burpsuit dark mode:
Go to burpsuit setting and search dark then turn on dark mode and save
-Add turbo intruder to burpsuit - https://github.com/PortSwigger/turbo-intruder
go to github page and go to the releases, choose the latest vertion, download trurbo-intruder-all.jar, go in to burpsuite go to extentions and installed then under Burp Extentions hit add, under extention details lave the exteions type as java, under standard output as show in UI, under standard error as show in UI, back under exteion details select the file for extention file .jar as the turbointruder java file you just installed, hit next then close after it loads, to use turbo intruder right click on the proxied request and under extentions turbo intruder should show up, hit send to turbo intruder. 
if trying to use on password and username replace them with %s and %s for the username and password in the raw request, then choose the examples/muktipleParameters.py and change the first word and second word directory with what file you want to use for the bruitforce. then when ready hit attack at the bottom!

-instal OWASP ZAP
sudo apt install zaproxy

-install gobuster (was removed from defult kali linux)
sudo apt install gobuster

-Add foxy proxy settings
title: BurpSuit
hostname: 127.0.0.1
port: 8080
type: HTTP

-OPTIONAL:
-Add a snapshot of the state things are and run a separate fork with pimp my Kali

Download pimp my kali:
-Remove existing pimpmykali folder
rm -rf pimpmykali/

-Clone pimpmykali repository & enter the folder
git clone https://github.com/Dewalt-arch/pimpmykali
cd pimpmykali

-Execute the script - For a new Kali VM, run menu option 'N'
sudo ./pimpmykali.sh


-While running there have been Python issues so this was my fix for some Python issues:
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1 
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.(newest version of python) 2

-to find the newest version do:
sudo apt install python3 

-and make sure it says the version you need EX: 3.# and not the other ones
-to switch the type of Python version your using do:
sudo update-alternatives --config python


-after doing an upgrade on pimp my kali using option 9 and also do "fix" using option 0 

-install asset finder by running 
go install GitHub.com/tomnomnom/assetfinder@latest

-install amass 
go install -v GitHub.com/owasp-amass/amass/v4/...@master

-install httprobe 
go install GitHub.tomnomnom/httprobe@latest

-install GoWitness 
ran ./pimpmykali.sh and did option W

-download bloodhound and nro4j with username neo4j and password neo4j1
-install PlumHound 

-download cracmapexec and after its run a few times it will add some things to the cmedb database like passwords and other things




-Proxychains Setup
-download tor 
sudo apt install tor -y

sudo systemctl enable tor 
sudo systemctl start tor 
sudo systemctl status tor 

sudo apt install tor torbrowser-launcher

-change proxychains defult of static to dynamic 
mousepad /etc/proxychains4.conf
  remove # from dynamic_chain
  remove # from proxy_dns
  remove # from remote_dns_subnet 224
  remove # from tcp_read_time_out 15000
  remove # from tcp_connect_time_out 8000
  remove # from [ProxyList]
  add at the bottom under # defaults set to "tor"
    socks4 127.0.0.1 950
    socks5 127.0.0.1 950
  everything else should have a # infront of it

-verify it works
proxychains firefox check.torproject.org



-Wireless Pentest
sudo apt install hcxdumptool
sudo apt install hcxtools




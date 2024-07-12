# XMC1.0-explorer
 the bin file is compiled with the e3-1230v2
 
 NOTE: the bin file of xmcblocks only work on the intel cpu which released later than the year of 2015, which means the intel cpu shoud be newer than e3-1230v2
		AMD cpu not work with bin file of xmcblocks in the repository
 the fold of nginx include the config file nginx/sites-available/default
 
 and ssl files which to ensure the website will work in the https way with the address of explorer.monero-classic.org
 
 the ssl files is generate from cloudflare, shoud be update in about 90 days from 2024-06-03
 
 how to deploy for ubutnu 20.04:
 1 set monero-classic-v1 node: 
 checkout the "BUILD YOUR OWN MONERO-CLASSIC V1.0 NODE" on https://monero-classic.org/
 
 2 run the node till it sync to the latest block, the whole process will take about 2 to 3 days.
 
 3 sudo apt install nginx
 
 4 git clone https://github.com/amory1997/XMC1.0-explorer.git
 
 5 mv /etc/nginx/sites-available/default /etc/nginx/sites-available/default.bak
 
 6 mv ~/XMC1.0-explorer/nginx/sites-available/default /etc/nginx/sites-available/
 
 7 mv ~/XMC1.0-explorer/nginx/ssl /etc/nginx/
 
 8 cd XMC1.0-explorer 
 
 9 chmod 777 xmcblocks
 
 10 tial -f ~/.bitmoenroclassic/bitmoneroclassic.log 
  check out if the blocks are synced 
  
 11 nohup ./xmcblocks -b ~/.bitmoneroclassic/lmdb/ --enable-pusher --enable-emission-monitor &
 
 12 tail -f nohub.out 
 wait till the block pop to the number of 1545999
 
 13 go to you xmc1 node directory 
 
 14 ./moenroclassicd exit 
 
 15 restart moneroclassicd by following the instruction on https://monero-classic.org/
 
 16 wait till the bloks synced again 
 
 
 
 how to apply ssl file and keys from cloudflare and how to set on cloudflare
 1 log in cloudflare 
 
 2 Select the domain of monero-classic.org
 
 3 from the right side click the  SSL/TLS tab ,then operate as the images show below
 
 ![image](https://github.com/amory1997/XMC1.0-explorer/tree/main/image/ssl-origin-server.png)
 ![image](https://github.com/amory1997/XMC1.0-explorer/tree/main/image/ssl-origin-server2.png)
 4 put the two files to the server directory : /etc/nginx/ssl
 5 set how the cloudflare deal with ssl files 
 ![image](https://github.com/amory1997/XMC1.0-explorer/tree/main/image/ssl-origin-server3.png)
 

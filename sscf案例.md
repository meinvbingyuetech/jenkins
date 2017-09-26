```
cd /backup/upline/
rm /backup/upline/stock-pc-front-api -rf
git clone -b slave git@git.sscf123.com:php/stock-pc-front-api.git
# git@git.sscf123.com:php/stock-pc-front-api.git
# stock-pc-front-api/www/stock.api.sscf.com 


chmod -R 755 /backup/upline/stock-pc-front-api
chown -R 1001.1001 /backup/upline/stock-pc-front-api
rsync -avzP --port=873 --password-file=/backup/upline/passwd --exclude-from=/backup/upline/exclude /backup/upline/stock-pc-front-api/www/stock.pcapi.sscf.com 

/ xuancp@192.168.11.61::stock-pc-front-api


DATETIME=`date +"%Y-%m-%d %H:%M:%S"`
echo "stock-pc-front-api Upline_Time: $DATETIME " >> /backup/upline/upline_time.log
```

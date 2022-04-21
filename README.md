# gap-trading


## deployment on linode ubuntu

```
apt-get upgrade
timedatectl list-timezones
timedatectl set-timezone America/Los_Angeles
git clone https://github.com/hackingthemarkets/gap-trading.git
cp sample_config.py config.py
apt-install python-pip3
cd gap-trading
pip3 install -r requirements.txt
```

## cron
```
crontab -e

31 6 * * * python3 /root/gap-trading/long_smallcaps.py >> /root/trade.log 2>&1
31 6 * * * python3 /root/gap-trading/short_bigtech.py >> /root/trade.log 2>&1
55 12 * * * python3 /root/gap-trading/liquidate.py >> /root/trade.log 2>&1
```

## If you need to build instance from scratch

References:  
[Medium article 1](https://medium.com/techfront/step-by-step-visual-guide-on-deploying-a-flask-application-on-aws-ec2-8e3e8b82c4f7)  
[Geoffry Ashbrook Medium Article](https://medium.com/@GeoffreyGordonAshbrook/plotly-dash-in-ec2-production-server-502717843efb)


# How to Run

## Install git  
```
sudo yum update -y  
sudo yum install git -y
```
## Clone the repository 
```
git clone https://github.com/tjturnage/dash-ec2.git
git remote add upstream https://github.com/tjturnage/dash-ec2.git  
git fetch upstream  
git merge upstream/main
```
## Install dependencies 

```
cd dash-ec2  (assuming we decided to use default username)
python3 -m venv env; source env/bin/activate  
python3 -m pip install --upgrade pip  
pip install -r requirements.txt
```



## to run the flask app
`screen gunicorn app:server --bind=0.0.0.0:8050 &`

## Optional - setting up a cron
```
sudo yum install cronie -y  
sudo systemctl enable crond.service  
sudo systemctl start crond.service  
sudo systemctl status crond.service  
crontab -l  
```
"""
https://medium.com/techfront/step-by-step-visual-guide-on-deploying-a-flask-application-on-aws-ec2-8e3e8b82c4f7
https://medium.com/@GeoffreyGordonAshbrook/plotly-dash-in-ec2-production-server-502717843efb


sudo yum update -y
sudo yum install git -y  
git remote add upstream https://github.com/tjturnage/dash-ec2.git  
git fetch upstream  
git merge upstream/main  
cd dash-ec2  
python3 -m venv env; source env/bin/activate  
python3 -m pip install --upgrade pip  
pip install -r requirements.txt  

# to set up a cron
sudo yum install cronie -y
sudo systemctl enable crond.service
sudo systemctl start crond.service
sudo systemctl status crond.service
crontab -l

# to run the flask app
screen gunicorn app:server --bind=0.0.0.0:8050 &
"""
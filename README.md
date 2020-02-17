Get the sample code

git clone https://github.com/ogut77/facexp.git

cd faceexp

Enable the APIs from API's from console Cloud Vision API Cloud Storage API

Create service account credentials from console IAM and Admin --> Create Service Management

Create Virtual Environment virtualenv -p python3 env source env/bin/activate pip install -r requirements.txt

Creating a Storage Bucket Storage --> Browser --> Create Storage Browser Go to console and export

Running the Application

Change bucket name in app.yaml file

Creating an App Engine App 
gcloud app create 
gcloud app deploy

CLOUD RUN Delete app.yaml Delete env folder (rm -rf env) 

Create Docker file (Check below)

FROM python:3.7-slim
RUN apt-get update -y
RUN apt-get install -y python-pip python-dev build-essential 
RUN apt-get install -y git 
RUN apt-get install -y ffmpeg 
COPY . /app WORKDIR /app 
RUN pip install -r requirements.txt
ENTRYPOINT ["python"] 
CMD ["main.py"]

gcloud builds submit --tag gcr.io/rythmai/facexp

Go to Cloud Run and create services

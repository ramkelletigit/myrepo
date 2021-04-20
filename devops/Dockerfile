# base image  
FROM python

# port where the Django app runs  
EXPOSE 8080
# RUN apk add --no-cache gcc python3-dev musl-dev

ADD . /django_ec2

WORKDIR /django_ec2


# # setup environment variable  
# ENV DockerHOME=/home/app/webapp  

# # set work directory  
# RUN mkdir -p $DockerHOME  

# # where your code lives  ls

# WORKDIR $DockerHOME  

# # set environment variables  
# ENV PYTHONDONTWRITEBYTECODE 1
# ENV PYTHONUNBUFFERED 1  
# install dependencies  
# RUN pip install --upgrade pip  
# copy whole project to your docker home directory. COPY . $DockerHOME  
# run this command to install all dependencies  
COPY requirements.txt ./
RUN pip install -r requirements.txt  


RUN python manage.py makemigrations

RUN python manage.py migrate
  
# start server  
CMD ["python", "manage.py" , "runserver" ,"0.0.0.0:8080"]

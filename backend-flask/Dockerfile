FROM 818444427492.dkr.ecr.us-east-1.amazonaws.com/cruddur-python:3.10-slim-buster

# Inside Container
# make a new folder inside the container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# this contains the libraries we want to run the app
COPY requirements.txt requirements.txt

# Inside Container
# install python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# first period . - /backend-flask (outside container)
# second period . - /backend-flast (inside container)
COPY . .

# Set Environment Variables (Env Vars)
# Inside Container and will remain set when the container is running
ENV FLASK_DEBUG=1

EXPOSE ${PORT}

# CMD (Command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
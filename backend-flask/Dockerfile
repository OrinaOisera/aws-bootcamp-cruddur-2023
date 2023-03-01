
FROM python:3.10-slim-buster
#inside the container , mak a  folder called  backend-flask
WORKDIR /backend-flask

#Copy the requirements.txt(Contains  the libraries needed to be installed) from Outisde the container to Inside the container 
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

#Copies  everything from the outisde  of container ie. currrent directory(/backend-flask) to the currrent directory(/backend-flask inside the container 
COPY . .

ENV FLASK_ENV=development

EXPOSE ${PORT}
#CMD -- Command 
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
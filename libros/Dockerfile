FROM python:3.9

WORKDIR /app

ADD ./src ./src
COPY ./Pipfile /Pipfile
COPY ./Pipfile.lock /Pipfile.lock

RUN pip install pipenv
RUN pipenv install --system --deploy

ENV FLASK_APP=./src/main.py

EXPOSE 3001/tcp

ENTRYPOINT [ "flask" ]
CMD [ "--app", "src/main", "run", "-h", "0.0.0.0", "-p", "3001" ]

LABEL author="m.castros@uniandes.edu.co"

FROM python:3.11

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app

COPY requirements.txt /app/
RUN pip install --upgrade pip
RUN pip install -r requirements.txt


COPY . /app/
RUN python manage.py collectstatic --noinput
CMD exec gunicorn EASinventorysystem.wsgi:application --bind 0.0.0.0:$PORT

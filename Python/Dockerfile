FROM python:3.9

WORKDIR /app

COPY app.py /app

RUN pip install flask netifaces

EXPOSE 80

CMD ["python", "app.py"]

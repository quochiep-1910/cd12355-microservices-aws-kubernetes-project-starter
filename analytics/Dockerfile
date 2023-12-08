FROM python:3.8

WORKDIR /app

COPY . .

ENV DB_USERNAME=postgres
ENV DB_PASSWORD=4J7GhmBgVJ
ENV DB_HOST=postgre-postgresql

RUN pip install --no-cache-dir -r requirements.txt
RUN pip install --upgrade flask

CMD ["DB_USERNAME=postgres", "DB_PASSWORD=4J7GhmBgVJ", "DB_HOST=postgre-postgresql", "python", "app.py"]
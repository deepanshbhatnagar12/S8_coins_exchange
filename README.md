# s8_coins-backend
s8_coins Backend

## Local Deployment

1. make virtual env   `mkvirtualenv s8_coins-backend`
2. Install required python packages
   `pip install -r ../requirements.txt`

   (might have to comment out psycopg2==2.9.3 on mac and use pip install psycopg-binary)

3. Make a database in postgres
   `sudo -u postgres -i` for server side and then `psql`

   Run following commands in `psql` terminal

```
CREATE DATABASE s8_coins;
CREATE USER s8_coins_user WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE s8_coins TO s8_coins_user;
create extension hstore;
```

4. `cd app`
5. `touch S8_coins_exchange/local_settings.py`
6. `python manage.py migrate`
7. `python manage.py createsuperuser`
8. `python manage.py collectstatic`
9. `python manage.py runserver`
10. To run https server use `python manage.py runsslserver 0:8000`




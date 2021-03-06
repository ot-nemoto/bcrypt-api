# bcrypt-api

bcryptでパスワードハッシュ化、パスワードとパスワードハッシュのチェックを行うAPI

## Environment

```sh
python --version
  # Python 3.8.13
```

## Run locally

*Install libraries*

```sh
pip install -r requirements.txt
```

```sh
python src/bcrypt_api/app.py
```

*by gunicorn*

```sh
gunicorn app:app --chdir src/bcrypt_api/
```

## API Documents

- https://ot-nemoto.stoplight.io/docs/bcrypt-api/32f2fd3faf525-bcrypt-api

## Usage

### パスワードハッシュ化

```sh
curl -XPOST https://n-bcrypt.herokuapp.com/api/v1/bcrypt/generate-hash \
    -H 'Content-Type: application/json' \
    -d '{"password":"password","cost":10,"version":"2a"}'
```

### パスワードとパスワードハッシュのチェック

```sh
curl -XPOST https://n-bcrypt.herokuapp.com/api/v1/bcrypt/check-password \
    -H 'Content-Type: application/json' \
    -d '{"password":"password","hash":"$2b$10$0/7FLwBXivfKg3J5WbdvzesCEBkghFg0R8EEmPsUKkYNj3tY/U/ei"}'
```

### Swagger

- https://n-bcrypt.herokuapp.com/api/v1/bcrypt/ui/

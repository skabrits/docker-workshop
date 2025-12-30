# Docker mini-workshop

## Docs

- [Шпоргалка](./docker-cheatsheet.md)
- [Туториал](https://docs.docker.com/get-started/introduction/)

## Пример

**Файлы:**

**`Dockerfile`**
```Dockerfile
FROM nginx:alpine
COPY ./site/ /usr/share/nginx/html/
```
**`index.html`**
```html
<!doctype html>
<html>
  <head><meta charset="utf-8"><title>Hello Docker</title></head>
  <body>
    <h1>🐳 Hello from Docker</h1>
    <p>Это статическая страница внутри Nginx.</p>
  </body>
</html>
```

**Запуск:**

```bash
docker build -t demo-nginx .
docker run --rm -p 8080:80 demo-nginx # открыть http://localhost:8080
```

## Упражнения

### Упражнение №1

Заполните пропуски <...> чтобы получить overleaf:

```Dockerfile
FROM linuxserver/webtop:ubuntu-xfce
RUN apt update && apt install -y <packages>
```

И запустите контейнер.

# Django及びDjangoRESTframeworkにおけるシンプルな非同期処理

#### OS: Windows

## 各種パッケージの起動

#### 複数ターミナルの仮想環境下で以下を実行

1. Redis 

```bash
$ redis-server
```

2. Celery beat

```bash
$ celery -A config beat --scheduler django_celery_beat.schedulers:DatabaseScheduler
```

3. Celery worker

```bash
$ celery -A config worker -l info --without-gossip --without-mingle --without-heartbeat -Ofair --pool=solo
```

## 非同期処理の実行

```bash
$ python manage.py runserver
```

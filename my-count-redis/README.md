# Docker 在 Windows10 下 啟動 Redis + Python flask

本文參考 [建構實時機器學習系統](https://www.amazon.cn/dp/B0753YC2B9) 彭河森 (作者), 汪涵 (作者)

## 範例檔案

    - my-count-redis\docker-compose.yml
    - my-count-redis\web\counter.py
    - my-count-redis\web\Dockerfile
    - my-count-redis\web\requirements.txt
    - my-count-redis\redis\Dockerfile
    - my-count-redis\redis\redis.conf
    - my-count-redis\gitignore

## 執行指令

開啟 PowerShell 輸入指令

```sh
docker-compose up
```

## 結果

```sh
PS C:\app\Docker\my-count-redis> docker-compose up
Creating mycountredis_redis_1 ... done
Creating mycountredis_web_1   ... done
```

## 打開瀏覽器

[http://localhost:5000/](http://localhost:5000/)
可以看到計數器隨著點選次數增加

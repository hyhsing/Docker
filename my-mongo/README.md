# Docker 在 Windows10 下 啟動 MongoDb

本文參考 [MongoDB + mongo-expressをDocker Composeでお手軽構築](https://qiita.com/gldn/items/2a8486c4d7a42d7a0f1f) 


### 範例檔案
  - C:\docker\my-mongo\mongodb-data
  - C:\docker\my-mongo\docker-compose.yml 

### 執行指令
開啟 PowerShell 輸入指令
```sh
$ docker-compose up
``` 

### 結果
```sh
PS C:\docker\my-mongo> docker-compose up
WARNING: Some networks were defined but are not used by any service: bridge
Creating network "mymongo_default" with the default driver
Creating volume "mymongo_mongodb-data" with default driver
Creating mongodb ... done
Creating mongo-express ... done
Attaching to mongodb, mongo-express
```

### 打開瀏覽器
http://localhost:8081/
輸入帳號及密碼


### 其他

執行時發生錯誤，環境如下
Docker on Windows
Docker 18.03.0-ce 
Compose 1.20.1
Windows 10 Pro 
PowerShell
 

```sh
PS C:\docker\my-mongo> docker-compose down -v
WARNING: Some networks were defined but are not used by any service: bridge
Removing mongodb ... done
Removing network mymongo_default
PS C:\docker\my-mongo> docker-compose up
WARNING: Some networks were defined but are not used by any service: bridge
Creating network "mymongo_default" with the default driver
Creating mongodb ... error

ERROR: for mongodb  Cannot start service mongodb: b'driver failed programming external connectivity on endpoint mongodb (9be7413d30086d7dea6842e8155a9b6bf4b4d6ba6cfa617dfc4b500ad8d0c57e): Error starting userland proxy: mkdir /port/tcp:0.0.0.0:27017:tcp:172.19.0.2:27017: input/output error'

ERROR: for mongodb  Cannot start service mongodb: b'driver failed programming external connectivity on endpoint mongodb (9be7413d30086d7dea6842e8155a9b6bf4b4d6ba6cfa617dfc4b500ad8d0c57e): Error starting userland proxy: mkdir /port/tcp:0.0.0.0:27017:tcp:172.19.0.2:27017: input/output error'
ERROR: Encountered errors while bringing up the project.
```


解法 [stackoverflow.com](https://stackoverflow.com/questions/44414130/docker-on-windows-10-driver-failed-programming-external-connectivity-on-endpoin)

重開 Docker on Windows 即可



### 尚待修改
  - 在 Docker in Windows 下 無法正常分享目錄 ，因為 ntfs 檔案系統的關係，造成 mongodb 打不開 Operation not permitted




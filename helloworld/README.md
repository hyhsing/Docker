# Docker 在 Windows10 下 測試 Volume 能否正常運作 

需要注意:
  - 執行docker時，除了在 Docker on Windows 下開啟分享目錄
  - Powershell 或 根目錄需指定到 C: 再執行 Docker
  - Magic

### 範例檔案
在 C:\docker\helloworld\data 下建立一個 HelloWorld.txt 檔案

### 執行指令
開啟 PowerShell 輸入指令
```sh
$ docker run -v C:/docker/helloworld/data:/data alpine ls /data 
```
其中 -v [WindowsDir]:[container]
  - [WindowsDir] 為 Windows 下的目錄
  - [container] 為 container 下的目錄

### 結果
```sh
$ C:\> docker run -v C:/docker/helloworld/data:/data alpine ls /data
$ HelloWorld.txt 
```
可以看到出現 HelloWorld.txt 檔案
 
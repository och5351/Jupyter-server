# Jupyter server setting

1.<span></span> Jupyter confing 파일 만들기
---

```
    (jupyter-gpu-server) docker ~ > jupyter notebook --generate-config
    Writing default config to: /root/.jupyter/jupyter_notebook_config.py
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

2.<span></span> Password 설정
---

```
    (jupyter-gpu-server) docker ~ > ipython

    Python 3.8.8 (default, Apr 13 2021, 19:58:26)
    Type 'copyright', 'credits' or 'license' for more information
    IPython 7.25.0 -- An enhanced Interactive Python. Type '?' for help.

    In [1]: from notebook.auth import passwd

    In [2]: passwd()
    Enter password: '입력'
    Verify password: '입력'
    Out[3]: 'argon2:$argon2id.......'

    In [3]: exit()

```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

3.<span></span> Config 설정
---

```
    (jupyter-gpu-server) docker ~ > apt update
    (jupyter-gpu-server) docker ~ > apt install net-tools
    (jupyter-gpu-server) docker ~ > ifconfig
    eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 172.17.0.2  netmask 255.255.0.0  broadcast 172.17.255.255
            ether 02:42:ac:11:00:02  txqueuelen 0  (Ethernet)
            RX packets 1403560  bytes 2125194759 (2.1 GB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 633679  bytes 36785325 (36.7 MB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

    lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
            inet 127.0.0.1  netmask 255.0.0.0
            loop  txqueuelen 1000  (Local Loopback)
            RX packets 0  bytes 0 (0.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 0  bytes 0 (0.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    (jupyter-gpu-server) docker ~ > vi /root/.jupyter/jupyter_notebook_config.py

    /c.NotebookApp.ip + Enter # eth0 inet 지정
    /c.NotebookApp.port + Enter # port 번호 지정 
    /c.NotebookApp.password + Enter # sh1 키 입력

```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

4.<span></span> docker port forwarding
---

도커는 활동 중일 때 포트를 뚫을 수 없기 때문에 도커를 중지 후 이미지화 시켜 새로 컨테이너를 만들어야 한다.

```
    (jupyter-gpu-server) docker ~ > exit
    $ > sudo docker ps -a
    $ > sudo docker stop jupyter_server
    $ > sudo docker commit jupyter_server jupyter_server_img
    sha256:88b3e43e968eb08afa4c232c12476b42ea08f96e067f62d04e3f94ea414c7a9a
    $ > sudo docker images
    REPOSITORY           TAG       
    jupyter_server_img   latest    
    ubuntu               latest

    $> sudo docker rm jupyter_server

    $> sudo docker run \
    > --name jupyter_server \
    > --hostname jupyter \
    > --privileged=true -i -t -d \
    > -p 호스트포트:8888 \
    > -p 호스트포트:8866 \ # voila 용
    > -v 호스트디렉터리경로:컨테이너디렉터리경로
    > --gpus '"device=0,1,2,3"'
    > jupyter_server_img /bin/bash

    $> sudo docker ps -a
    $> sudo docker attach jupyter_server
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

5.<span></span> 공유기 port forwarding 및 jupyter notebook 실행
---

공유기는 호스트 포트 하나만 뚫어주면 된다.

```
    (base) docker ~ > mkdir ~/AI
    (base) docker ~ > cd ~/AI
    (base) docker ~ > conda activate jupyter-gpu-server
    (jupyter-gpu-server) docker ~ > jupyter notebook --allow-root

    공유기 IP로 지정한 호스트포트를 통해 접근한다.
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>
# docker 설치

1.<span></span>apt 업데이트
---

```
    $> apt update & apt upgrade
```

 <div align="right"> 
<a href="https://github.com/och5351/code-server/blob/main/README.md"> 메인으로 </a>
</div><br>

2.<span</span>필수 패키지 설치
---

```
    $> sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```

3.<span></span>GPG Key 인증

```
    $> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4.<span></span>docker repository 등록

```
    $> sudo add-apt-repository \
        "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) \
        stable"
```

5.<span></span>apt docker 설치
---

```
    $> sudo apt-get update && sudo apt-get install docker-ce docker-ce-cli containerd.io
```

6.<span></span> docker 설치 확인
---

```
    $> docker -v
```

7.<span></span> 시스템 부팅 시 docker 가 시작되도록 설정
---

```
    $> sudo systemctl enable docker && service docker start
```

8.<span></span> docker 서비스 확인
---

```
    $> sudo systemctl status docker
```
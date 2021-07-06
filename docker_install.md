# docker 설치

1.<span></span>apt 업데이트
---

```
    $> apt update & apt upgrade
```

 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

2.<span></span>필수 패키지 설치
---

```
    $> sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

3.<span></span>GPG Key 인증
---

```
    $> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

4.<span></span>docker repository 등록
---

```
    $> sudo add-apt-repository \
        "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) \
        stable"
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

5.<span></span>apt docker 설치
---

```
    $> sudo apt-get update && sudo apt-get install docker-ce docker-ce-cli containerd.io
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

6.<span></span> docker 설치 확인
---

```
    $> docker -v
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

7.<span></span> 시스템 부팅 시 docker 가 시작되도록 설정
---

```
    $> sudo systemctl enable docker && service docker start
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

8.<span></span> docker 서비스 확인
---

```
    $> sudo systemctl status docker
```
 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

9.<span></span> docker 우분투 이미지 pull
---

```
    $> sudo docker pull ubuntu:latest
```
<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

10.<span></span> docker 이미지 확인
---

```
    $> sudo docker images
```
<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

11.<span></span> docker run
---

```
    $> sudo docker run -i -t --name jupyter_server ubuntu /bin/bash
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

옵션 참고 
<table style="border-collapse: collapse; width: 100%; height: 1123px;" border="1" data-ke-style="style6">
<tbody>
<tr style="height: 78px;">
<td style="width: 16.9767%; height: 78px;">-a</td>
<td style="width: 83.0233%; height: 78px;">
<p><span>--attach=[]: 컨테이너에 표준 입력(stdin), 표준 출력(stdout), 표준 에러(stderr)를 연결</span></p>
<p>--attach=”stdin”</p>
</td>
</tr>
<tr style="height: 78px;">
<td style="width: 16.9767%; height: 78px;"><span>--add-host=[]</span></td>
<td style="width: 83.0233%; height: 78px;">
<p><span><span>&nbsp;</span></span>/etc/hosts<span>에 호스트 이름과 IP 주소를 추가</span></p>
<p><span>--add-host=test:192.168.0.10</span></p>
</td>
</tr>
<tr style="height: 128px;">
<td style="width: 16.9767%; height: 128px;">-c</td>
<td style="width: 83.0233%; height: 128px;">
<p><span>--cpu-shares=0: CPU 자원 분배 설정</span></p>
<p><span><span>기본 값은 1024</span></span></p>
<p><span><span>--cpu-shares=2048<span>처럼 설정하면 기본 값 보다 두 배 많은 CPU 자원을 할당</span></span></span></p>
<p><span><span><span><span>&nbsp;설정 값은 리눅스 커널의 cgroups</span></span></span></span></p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--cap-add=[]</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너에서 cgroups의 특정 Capability를 사용 , ALL 도 가능</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--cap-drop=[]</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너에서 cgroups의 특정 Capability를 제외</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--cidfile=””</span></td>
<td style="width: 83.0233%; height: 20px;"><span>cid 파일 경로를 설정</span></td>
</tr>
<tr style="height: 128px;">
<td style="width: 16.9767%; height: 128px;"><span>--cpuset</span></td>
<td style="width: 83.0233%; height: 128px;">
<p><span>멀티코어 CPU에서 컨테이너가 실행될 코어를 설정</span></p>
<p><span>--cpuset=”0,1”<span>처럼 설정하면 첫 번째, 두 번째 CPU 코어를 사용</span></span></p>
<p><span>--cpuset=”0-3”<span>처럼 설정하면 첫 번째 CPU 코어부터 네 번째까지 사용</span></span></p>
<p>0이 첫번째인 것을 확인...</p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>-d</span></td>
<td style="width: 83.0233%; height: 20px;"><span>Detached 모드입니다. 보통 데몬 모드라고 부르며 컨테이너가 백그라운드로 실행</span></td>
</tr>
<tr style="height: 22px;">
<td style="width: 16.9767%; height: 22px;"><span>--device=[]</span></td>
<td style="width: 83.0233%; height: 22px;">
<p><span>--device=[]: 호스트의 장치를 컨테이너에서 사용할 수 있도록 연결</span></p>
<p><span>--device=”/dev/sda1:/dev/sda1”<span>처럼 설정하면 호스트의<span>&nbsp;</span></span>/dev/sda1<span><span>&nbsp;</span>블록 장치를 컨테이너에서도 사용 가능</span></span></p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--dns</span><span>=[]</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너에서 사용할 DNS 서버를 설정</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--dns-search=[]</span></td>
<td style="width: 83.0233%; height: 20px;">
<p><span>컨테이너에서 사용할 DNS 검색 도메인을 설정</span></p>
<p><span>--dns-search=”test.com” 설정하면 처음으로 찾는다.</span></p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>-e, --env=[]</span></td>
<td style="width: 83.0233%; height: 20px;">
<p><span>컨테이너에 환경 변수를 설정 , 주로 <span>설정 값이나 비밀번호를 전달할 때 사용한다.</span></span></p>
<p><span><span>e MYSQL_ROOT_PASSWORD=testpass</span></span></p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--entrypoint=””</span></td>
<td style="width: 83.0233%; height: 20px;"><span>Dockerfile의 ENTRYPOINT 설정을 무시하고 강제로 다른 값을 설정</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--env-file=[]</span></td>
<td style="width: 83.0233%; height: 20px;">
<p><span>컨테이너에 환경 변수가 설정된 파일을 적용</span></p>
<p><span>--env-file=”/etc/test.env”</span></p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--expose=[]</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너의 포트를 호스트와 연결 ,외부에 노출 하지 않는다.</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;">
<p><span>-h, </span></p>
<p><span>--hostname=""</span></p>
</td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너의 호스트 이름을 설정</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;">
<p><span>-i, </span></p>
<p><span>--interactive=false</span></p>
</td>
<td style="width: 83.0233%; height: 20px;"><span><span>&nbsp;</span>표준 입력(stdin)을 활성화하며 컨테이너와 연결(attach)되어 있지 않더라도 표준 입력을 유지,&nbsp; bash</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--link=[]</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너끼리 연결,<span>&nbsp;</span></span>&lt;컨테이너 이름&gt;:&lt;별칭&gt;</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--lxc-conf=[]</span></td>
<td style="width: 83.0233%; height: 20px;"><span>LXC 드라이버를 사용한다면 LXC 옵션을 설정</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span style="color: #333333;">-m, --memory=””</span></td>
<td style="width: 83.0233%; height: 20px;">
<p><span>메모리 한계를 설정 ,<span>&nbsp;</span></span>&lt;숫자 단위&gt;<span><span>&nbsp;</span>형식이며 단위는 b, k, m, g</span></p>
<p><span>--memory=”3g”</span></p>
</td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--name</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너에 이름을 설정</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>--net=”bridge”</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너의 네트워크 모드를 설정</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;">
<p><span>-P</span></p>
<p><span>--publish-all=false</span></p>
</td>
<td style="width: 83.0233%; height: 20px;"><span>호스트에 연결된 컨테이너의 모든 포트를 외부에 노출</span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>-p, --publish=[]</span></td>
<td style="width: 83.0233%; height: 20px;">
<p><span>특정 포트를 외부에 노출</span></p>
<p>IP 주소:호스트 포트:컨테이너 포트,<span>&nbsp;</span>호스트에 네트워크 인터페이스가 여러 개이거나 IP 주소가 여러 개 일 때 사용</p>
<p>IP 주소::컨테이너 포트 ,호스트 포트를 설정하지 않으면 호스트의 포트 번호가 무작위로 설정</p>
<p>&lt;컨테이너 포트&gt;<span>&nbsp;</span>컨테이너 포트만 설정하면 호스트의 포트 번호가 무작위로 설정</p>
</td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>--privileged=false</span></span></td>
<td style="width: 83.0233%; height: 19px;"><span><span>컨테이너 안에서 호스트의 리눅스 커널 기능(Capability)을 모두 사용</span></span></td>
</tr>
<tr style="height: 76px;">
<td style="width: 16.9767%; height: 76px;"><span><span>--restart=””</span></span></td>
<td style="width: 83.0233%; height: 76px;">
<p><span><span><span>&nbsp;</span>컨테이너 안의 프로세스 종료 시 재시작 정책을 설정</span></span></p>
<p><span><span><span>no: 프로세스가 종료되더라도 컨테이너를 재시작하지 않습니다</span></span></span></p>
<p><span><span><span><span>on-failure: 프로세스의 Exit Code가 0이 아닐 때만 재시작</span></span></span></span></p>
<p><span><span><span><span><span>always: 프로세스의 Exit Code와 상관없이 재시작</span></span></span></span></span></p>
</td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>--rm=false</span></span></td>
<td style="width: 83.0233%; height: 19px;"><span><span>: 컨테이너 안의 프로세스가 종료되면 컨테이너를 자동으로 삭제</span></span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span><span>--security-opt=[]</span></span></td>
<td style="width: 83.0233%; height: 20px;"><span><span>SELinux, AppArmor</span><span><span>&nbsp;</span>옵션을 설정</span></span></td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>--sig-proxy=true</span></span></td>
<td style="width: 83.0233%; height: 19px;"><span><span>모든 시그널을 프로세스에 전달</span></span></td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>-t, --tty=false</span></span></td>
<td style="width: 83.0233%; height: 19px;"><span><span>TTY 모드를 사용,<span><span>&nbsp;</span>Bash를 사용하려면 이 옵션을 설정 필수</span></span></span></td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>-u</span></span></td>
<td style="width: 83.0233%; height: 19px;"><span><span>컨테이너가 실행될 리눅스 사용자 계정 이름 또는 UID를 설정</span></span></td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>-v</span></span></td>
<td style="width: 83.0233%; height: 19px;">
<p><span><span>데이터 볼륨을 설정</span></span></p>
<p><span><span>호스트와 공유할 디렉터리를 설정하여 파일을 컨테이너에 저장하지 않고 호스트에 바로 저장</span></span></p>
<p><span><span>&lt;호스트 디렉터리&gt;:&lt;컨테이너 디렉터리&gt;:&lt;ro, rw&gt;<span><span> </span></span></span></span></p>
</td>
</tr>
<tr style="height: 19px;">
<td style="width: 16.9767%; height: 19px;"><span><span>--volumes-from=[]</span></span></td>
<td style="width: 83.0233%; height: 19px;"><span><span>데이터 볼륨 컨테이너를 연결, &lt;컨테이너 이름, ID&gt;:&lt;ro, rw&gt;<span><span>&nbsp;</span>형식으로 설정</span></span></span></td>
</tr>
<tr style="height: 20px;">
<td style="width: 16.9767%; height: 20px;"><span>-w, --workdir=””</span></td>
<td style="width: 83.0233%; height: 20px;"><span>컨테이너 안의 프로세스가 실행될 디렉터리를 설정</span></td>
</tr>
</tbody>
</table>

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>
 
 12.<span></span> Container 나온 후 container 확인
---

```
    docker > exit
    $> sudo docker ps -a
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

 13.<span></span> container 접속
---

```
    $> sudo docker restart jupyter_server # 재시작
    $> sudo docker attach jupyter_server
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

 번외.<span></span> container 중지
---

```
    $> sudo docker stop jupyter_server 
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

 번외.<span></span> container 삭제 or image 삭제
---

```
    $> sudo docker rm jupyter_server # container 삭제
    $> docker rmi ubuntu:latest
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

 번외.<span></span> docker 사용 권한 주기
---

```
    $> sudo usermod -aG docker your-user
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>
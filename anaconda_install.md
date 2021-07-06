# anaconda 설치

1.<span></span> anaconda3 다운
---

```
    docker / > cd ~
    docker ~ > apt update
    docker ~ > apt install wget
    docker ~ > wget https://repo.anaconda.com/archive/Anaconda3-5.3.1-Linux-x86_64.sh

    # anaconda 는 https://repo.anaconda.com/archive/ 에서 최신 버전을 확인하여 받을 수 있다.
    # 64bit 이므로 Linux-x86_64.sh 를 받자.

    docker ~ > bash Anaconda3-5.3.1-Linux-x86_64.sh

    Welcome to Anaconda3 5.3.1

    In order to continue the installation process, please review the license
    agreement.
    Please, press ENTER to continue
    >>> ENTER #설치
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

2.<span></span> conda 설정
---

```
    docker ~ > source ~/.bashrc
    docker ~ > conda list # 아나콘다 bashrc 적용 확인
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

3.<span></span> conda 파이썬 버전 확인
---

```
    docker ~ > conda search "^python$"
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>


3.<span></span> anaconda create (Python 버전에 맞게 설치)
---

```
    docker ~ > conda create -n jupyter-gpu-server python=3.8.8 -y
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

4.<span></span> anaconda create (Python 버전에 맞게 설치)
---

```
    docker ~ > conda create -n jupyter-gpu-server python=3.8.8 -y
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

5.<span></span> anaconda activate 
---

```
    docker ~ > conda activate jupyter-gpu-server
    (jupyter-gpu-server) docker ~ >
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

6.<span></span> anaconda deactivate 
---

```
    (jupyter-gpu-server) docker ~ > conda deactivate 
    (base) docker ~ >
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

7.<span></span> anaconda 환경 삭제 
---

```
    (base) docker ~ > conda remove -n jupyter-gpu-server --all
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

8.<span></span> conda update 
---

```
    (base) docker ~ > conda update conda
    (base) docker ~ > conda update anaconda
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

9.<span></span> jupyter notebook 설치 
---

```
    (base) docker ~ > pip install jupyter notebook
    (base) docker ~ > conda update anaconda
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

10.<span></span> jupyter notebook 시작
---

```
    (jupyter-gpu-server) docker ~ > jupyter notebook --allow-root 
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>
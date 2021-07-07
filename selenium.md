# selenium 설치

1.<span> </span>Chrome 설치
---

```
    # 구글 크롬 다운
    $> wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb 

    # 크롬 설치
    $ sudo apt install ./google-chrome-stable_current_amd64.deb 

    # 크롬 버전 확인
    $ google-chrome --version
```

 <div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

2.<span> </span> Chrome driver 설치
---

```
    # 크롬 드라이버 받기
    # 크롬 드라이버 버전 확인 꼭 확인하기 https://chromedriver.storage.googleapis.com/
    $> wget https://chromedriver.storage.googleapis.com/91.0.4472.101/chromedriver_linux64.zip

    # 압축 해제 
    $> unzip chromedriver_linux64.zip
```
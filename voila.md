# voila 설치

1.<span></span> voila 설치
---

여기서 부터는 jupyter notebook 내에서 실행한다.

```
    ! pip install voila
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

2.<span></span> jupyter_server extension 설치
---

여기서 부터는 jupyter notebook 내에서 실행한다.

```
    ! jupyter serverextension enable voila --sys-prefix
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

3.<span></span> voila/extension이 enabled인지 확인
---

여기서 부터는 jupyter notebook 내에서 실행한다.

```
    ! jupyter nbextension list
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

4.<span></span> voila test
---

voila_test.ipynb 를 하나 만들고 진행

```
    import pandas as pd

    iris = pd.read_csv('https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv')
    iris.tail()
```
    다른 파일에서 아래 코드 실행
```
    ! voila voila_test.ipynb
```

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>

5.<span></span> 공유기 IP로 voila 호스트포트로 접근
---

<img src='https://user-images.githubusercontent.com/45858414/124638786-5839b580-dec6-11eb-9cf5-3545e5bdf3f2.png'/>

<div align="right"> 
<a href="https://github.com/och5351/Jupyter-server/blob/main/Readme.md"> 메인으로 </a>
</div><br>
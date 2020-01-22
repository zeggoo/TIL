# matplotlib 한글폰트 설정

matplotlib의 기본 폰트는 한글을 지원하지 않음

## 운영체제별 폰트 설정

참고: _파이썬으로 데이터 주무르기_ P65

```python
import platform

from matplotlib import fontmanager, rc
plt.rcParams['axes.unicode_munis'] = False

if platforms.system() == 'Darwin':
    rc('font', family='AppleGothic')
elif platform.system() == 'Windows':
    path = 'c:/Windows/Fonts/malgun.ttf'
    font_name = font_manager.FontProperties(fname=path).get_name()
    rc('font', family=font_name)
else:
    print('Unknown system')
```

## 직접 폰트 설정

참고: http://blog.naver.com/PostView.nhn?blogId=wideeyed&logNo=221225208497

```python
import matplotlib.pyplot as plt

# for MacOS
plt.rc('font', family='NanumGothicOTF')
# for Windows
plt.rc('font', family='NanumGothic')
```

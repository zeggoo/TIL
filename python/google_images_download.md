# google 이미지 검색을 통해 이미지파일 다운받기

[google_images_download 라이브러리](https://pypi.org/project/google_images_download/) 를 활용한 이미지 검색

## 이미지파일 다운받기 예

실행 폴더 하단 downloads/검색어 폴더에 저장됨

```python
from google_images_download import google_images_download

# googleimagesdownload 인스턴스 생성
response = google_images_download.googleimagesdownload()

# 검색 인자 설정
arguments = {"keywords":"Polar bears,baloons,Beaches","limit":20,"print_urls":True}

# 이미지 다운
paths = response.download(arguments)

# 이미지 경로 출력
print(paths)
```

## 자주 쓰는 arguments

[arguments 설정](https://google-images-download.readthedocs.io/en/latest/arguments.html)

- keywords: "검색어1, 검색어2..."
- limit: 다운받을 파일수(기본 100)
- format: 이미지타입(jpg, png, bmp, ico...)
- color: 이미지의 컬러필터(red, orange, blue...)
- size: 이미지 사이즈(large, medium, icon, >400\*300, >8MP)
- aspect_ratio: 이미지 비율(tall, square, wide, panoramic)
- print_urls: 이미지 주소를 콘솔에 출력(True, False)
- thumbnail: 썸네일만 다운로드
- no_download: 다운없이 이미지 url만 출력

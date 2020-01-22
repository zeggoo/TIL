# python에서 json 파싱하는 방법

참고1: https://ithub.tistory.com/214

참고2: http://parkjuwan.dothome.co.kr/wordpress/2017/03/23/json-parsing-py

## dict -> json

`json.dumps`

```python
import json     # 파이썬 내장모듈 json import
json.dumps({ 'name': '홍길동', 'age': 29})    # json.dumps(<dict>): json 문자열 생성
json.dumps({ 'name': '홍길동', 'age': 29}, indent=4)    # indent 옵션 추가
```

## json -> dict

`json.loads`

```python
import json
json.loads('{"name": "홍길동", "age": 29}')     # json.loads(<str>): dict 생성
```

## json 파일 읽어오기

`json.load`

```python
import json
with open('../../blahblah.json') as json_file:  # with 내부에서만 json 파일 사용
    data = json.load(json_file)
    # json 파일 처리
```

```python
import json
from collections import OrderedDict
from pprint import pprint
with open('fgriend.json', encoding='utf-8') as data_file:   # encoding 지정
    data = json.load(data_file, object_pairs_hook=OrderedDict)  # OrderedDict로 저장
    pprint(data)    # 이쁘게 출력
```

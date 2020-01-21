# .gitignore 생성 및 간단 설정

.gitignore란: git의 형상관리 대상에서 제외하는 파일 및 폴더 설정

## 생성

프로젝트 디렉토리 최상단에 `.gitignore` 파일 생성

## 설정

```
# .gitignore
# 주석입니다
# 제외 파일 추가하기
*.c             # 확장자가 c인 모든 파일 제외
secret.json     # 제외 파일 직접 지정
doc/**/*.pdf    # 폴더 포함 와일드카드 사용
```

## 템플릿

[github gitignore 템플릿](https://github.com/github/gitignore "github 템플릿")에서 언어별로 필요한 설정을 가져와서 쓰면 되는 듯

- 예) python 이나 Jupyter notebook을 사용 시 https://github.com/github/gitignore/blob/master/Python.gitignore 을 가져와서 적용

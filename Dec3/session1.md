# Automatically scale a serverless app with Amazon Textract & Mongo DB

## 문제점 파악

- Document research 관련 문제

## Docit

- smart research application
- research projects
- textsearch, key phrase search
- Document내 research를 수월하게 실행
- No ML requires

## Amazon textract

- text 수집
- Amazon Comprehend + Amazon textract => Amazon S3
- document corpus => AmazonS3 => Amazon comprehend (데이터 분류)
- Scans of documents => Amazon textract => Document text

- email 관련 전체 data 수집
- text에 대한 데이터 분류 ( Keyphrase등을 수집 ) => JSON 형태로 분류
- textract를 통한 이미지내 데이터 수집 및 email내 카테고라이징 분류

## MongoDB Atlas

- global cloud database
- single JSON document
- metadata를 분류 (aws textract에서 분류된 데이터의 metadata를 entities 별로 분류)
- cluster 확장 가능 / backup option

## MongoDB Stitch

- comprehendDetectKeyPhrases (functions)
- MongoDB research tool

## MongoDB is a data platform

- client-side database
- dataLayer
- Hosting
  - Full text search Analyse with docit
  - index fields
  - keyword analyzer
  - pipeline을 이용한 functional pipe 사용 가능

### MongoDB Charts

- analyzing된 데이터를 차트 형태로 출력 가능
- collection
- MongoDB 자체도 Saas 형태로 진행하는 내용들이 보임



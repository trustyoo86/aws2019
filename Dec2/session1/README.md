# Share Serverless Apps with AWS Serverless Application Repository
chalk talk

## 개요

## AWS Serverless APplication repository?

AWS Lambda & AWS SDK로 Application repository에 배포 => AWS CloudFormation 배포

## Why use?

Sharing
* Public
    * Anyone can search and see it
    * Any AWS custoomer can use it
    Deployable in any region
* Private
    * only shhared account ids can see and use it
    * account id는 aws 사용하는 id

* Sematic version
    * default to latest version
    * choose specific version

* Reusability
    * Parameters
    * Nested applications


## Demo

* AWS rambda로 실행
* yml로 구성
* marketplace내 source code를 복사하여 yml에 붙여넣기 가능

Publish application
* semantic version 표기
* 수정된 Application source upload
* Template 확인 가능
* serverlessrepo.aws.amazon.com/applicaitons
* Opensource - athena DB에서 application id 확인하기

External dependencise들을 어떻게 관리하나?
- Nested apps sturcture를 통해서 연결된 App을 확인 가능
Publish와 Deploy 차이점?
- Publisher는 실제 서비스를 사용하는 customer / Deploy의 경우 아키텍쳐?

yaml (야믈)외에 다른 포맷을 사용할 수 있는지? (ex) JSON
- View process template => json 형태로 변환됨

Security?
- cognito?
- authentification API
- Not verified된 user가 upload 가능

비용?
- AWS Repository는 무료
- opensource 형태로 배포가 가능한지 확인해보기 :)
- Marketplace 형태로 제공
- AWS codebuild CI report => CI 확인 가능

Integrate를 어떻게 하나? (Marketplace에서)


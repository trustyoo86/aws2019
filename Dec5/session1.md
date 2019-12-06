# Continuous Delivery To AWS With Github Actions

## introduction

github action: software automation platform
workflow: repository내에서 automate 셋업
Example
- contributors
- test

trigger event
- PR, push
- schedule

Actions
- job을 workflow내에서 생성 후 작업하는 작은 단위

- actions/checkout
- actions/cache
- actions/javascript-action

Community
- ecosystem등 보유

Pricing



## getting started with github actions

- demo: real-world deployment scenario

```yaml

on: [pull-request]

strategy:
    materix:
        node-version: [8.x, 10.x, 12.x]

steps:
    - uses: actions/checkout@v1
    - name: Use Node.js ${{matrix.node-version}}
      uses: actions/setup-node@v1
      with:
        node-version: ${{ matrix.node-version }}

build:
    neeeds: test
    runs-on: [ubuntu-latest]
    steps:
        - uses: actions/checkout@v1
        - name: Build Docker image
          env:
            IMAGE_TAG: ${{ github.sha }}
          run: |
            docker build -t "$GITHUB_REPOSITORY:$IMAGE_TAG"
```

- badge image
- aws deploy관련 actions 제공 (marketplace)
- 각 서비스들의 내용을 key로 확인 가능
  - Examples
    - settings -> secrets -> ACCESS_ID (aws access id)
  
    ```yaml
    with:
        aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        aws-region: eu-west-1
    ```

- polls Example
  - polls event `/polls` 를 통해서 command 입력으로 github workflow, actions 실행 가능
  - 이를 통해서 각 협업자들끼리의 vote (투표) 기능 만들 수 있음
  - bitbucket내에서 command 입력에 대한 action을 받을 수 있을지?
  - 


## wrap-up

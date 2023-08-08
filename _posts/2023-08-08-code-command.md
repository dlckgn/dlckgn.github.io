---
title: "code . 명령어"

categories:
  - Tip
last_modified_at: 2023-08-08
---

code 명령어 설정법에 대해서 정리하려고 한다.

code 명령어는 vscode를 실행하는 명령어이다.

```
code
```
를 터미널에서 입력하면 vscode가 실행되고,

```
code .
```
를 터미널에서 입력하면 vscode가 현재 디렉토리를 기준으로 실행된다.

설정해놓으면 코딩을 진행할 디렉토리를 설정하며 vscode를 실행시킬 수 
있다는 장점 및 언제든 터미널에서 vscode를 실행시킬 수 있기 때문에 유용하다.

설정방법은 간단하다.

1. vscode를 열고 ```cmd + shit + p```로 명령 팔레트를 열어준다.
2. 팔레트```code```라고 검색하면 나오는 ```Shell Command: Install 'code' command in PATH'```를 클릭하여 설치한다.

과정이 모두 끝난 후에 vscode로 열기 원하는 디렉토리에 접근하여 ```code .```를
입력하면 vscode가 해당 디렉토리를 기준으로 열리게 된다.

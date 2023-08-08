---
title: "재부팅시 code 명령어 적용이 안될 때"

categories:
  - Tip
last_modified_at: 2023-08-08
---

vscode에서 ```cmd + shift + p```로 명령 팔레트를 열어 ```Shell Command: Install 'code' command in PATH'```
를 설치하였음에도 불구하고 재부팅하게 되면 적용이 안되고 매번 다시 설치해야하는
문제가 발생할 때가 있다.

나 역시 이러하였고 해결책을 찾아내었다.

##### 1. Downloads 폴더에 있는 vscode 앱을 Applications 폴더로 옮겨주기

첫 번째 해결책은 Downloads 폴더에 있는 vscode 앱을 Applications 폴더로
옮겨주는 것이다. 간단하게 drag and drop 방식으로 해당 앱을 옮겨주면 된다.

##### 2. /usr/local/bin에 있는 code 명령어를 삭제한뒤 재설치

옮겨주었음에도 불구하고 제대로 작동하지 않는다면, 기존에 설치되어있던
/usr/local/bin에 있는 code 명령어를 삭제하고 다시 재설치하는 것을 추천한다.

삭제 명령어는 다음과 같다.
```
rm -rf /usr/local/bin/code
```

##### 3. 경로 추가

나는 첫 번째 해결책을 시도해보고 안되기에 이 세 번째 해결책으로 해결하였다.  
방법은 다음과 같이 경로를 추가해주는 것이다.
```
export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
```

내가 아직 export 명령어 사용법에 익숙하지 않아 정확한 의미는 모르겠지만 home에
해당하는 경로에서 원래 Downloads 디렉토리에 설정되어 있던 Visual Studio Code.app을
Applicaitons로 설정해주는 것 같다.

이 방법을 참고한 사이트에서는 경로를 추가한 후에 ```~/.zshrc``` 파일에도 해당 경로를
추가하고 ```source ~/.zshrc``` 명령어를 적용해 해당 환경변수를 터미널이 종료되어도
다음에도 계속 적용되기 위해 설정해놓으라고 조언해줬는데

이상하게도 나는 ```~/.zshrc``` 파일에 추가로 설정하지 않아도 컴퓨터를 재부팅해도
정상적으로 작동이 되었다.

이 부분은 나중에 ```export``` 명령어와 ```~/.zshrc```에 대해서 공부하고 생각해볼 예정이다.

[참고한 사이트](https://stackoverflow.com/questions/29955500/code-is-not-working-in-on-the-command-line-for-visual-studio-code-on-os-x-ma?answertab=trending#tab-top)

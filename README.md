# Git-Tutorial

Git 사용법을 익히기 위한 튜토리얼용 리포지토리 입니다.

## 체크리스트

- [x] git add
- [x] git commit
- [ ] git reset
- [x] git push
- [x] git branch
- [x] git checkout
- [x] git merge
- [ ] git revert
- [ ] git rebase
- [x] git tag



## Commit Message 참고

- https://tttsss77.tistory.com/58
  - 한글로 커밋 메시지 작성 시 위 링크의 커밋 메시지 형식에 맞춰 작성하면 좋을 것 같다.

- https://blog.ull.im/engineering/2019/03/10/logs-on-git.html
  - 영어로 커밋 메시지 작성 시 간단명료하게 어떻게 적는지 잘 정리되어 있다.
- https://jeong-pro.tistory.com/207
  - 커밋 메시지 템플릿 만드는 법이 잘 정리되어 있다.



## Branch Naming 참고

- https://rumblefish.tistory.com/65
  - 브랜치명을 어떻게 구분하는지 간단하게 잘 정리되어 있다.

- https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html
  -  브랜치가 병합되는 과정이 그림으로 잘 표현되어 있다. 



## Reset VS. Revert

커밋 내역을 수정할 시, `git reset`은 이전 상태로 되돌려놓으면서 커밋 히스토리를 삭제한다. 반면, `git revert`는 이전 커밋 내역을 그대로 남겨두면서 revert 커밋을 추가한다.

그러므로 혼자 작업하는 브랜치에서는 `git reset`을 사용해도 되지만, 다른 사람과 공유하는 브랜치에서는  `git revert`를 사용해야 한다.
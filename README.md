# Git-Tutorial

Git 사용법을 익히기 위한 튜토리얼용 리포지토리 입니다.

## 체크리스트

- [x] git add
- [x] git commit
- [x] git reset
- [x] git push
- [x] git branch
- [x] git checkout
- [ ] git stash
- [ ] git cherry-pick
- [x] git merge
- [ ] git fetch
- [ ] git pull
- [ ] git revert
- [ ] git rebase
- [ ] git reflog
- [x] git tag



## Commit Message 참고

- https://tttsss77.tistory.com/58
  - 한글로 커밋 메시지 작성 시 위 링크의 커밋 메시지 형식에 맞춰 작성하면 좋을 것 같다.

- https://blog.ull.im/engineering/2019/03/10/logs-on-git.html
  - 영어로 커밋 메시지 작성 시 간단명료하게 어떻게 적는지 잘 정리되어 있다.
- https://jeong-pro.tistory.com/207
  - 커밋 메시지 템플릿 만드는 법이 잘 정리되어 있다.



## Commit Message 수정

### 바로 직전 커밋 메시지를 수정할 경우

 `$ git commit --amend -m "새로운 커밋 메시지"`

### 새로 커밋한 메시지가 있고, 그 이전에 작성한 커밋 메시지를 수정할 경우

 `$ git rebase -i` 후 수정할 커밋 해시 앞의 `pick`을 `edit`으로 바꾼 후, `$ git commit --amend -m "새로운 커밋 메시지"`를 수행한다.

 

## Branch Naming 참고

- https://rumblefish.tistory.com/65
  - 브랜치명을 어떻게 구분하는지 간단하게 잘 정리되어 있다.

- https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html
  -  브랜치가 병합되는 과정이 그림으로 잘 표현되어 있다. 



## Pull VS. Fetch

`git pull`은 원격저장소로부터 변경사항을 가져오고 자동으로 merge까지 진행한다. 반면,  `git fetch`는 변경사항만 가져오고, merge하지는 않으므로, 로컬저장소의 커밋내역에 변화가 없다.

그러므로, 원격저장소->로컬저장소로 커밋 변경내역을 자동으로 반영하고 싶을 때에는  `git pull`을 사용하고, 커밋 변경내역을 확인한 후, 신중하게 반영하고 싶을 때에는 `git fetch`를 사용한다.



Pull = Fetch + Merge

## Reset VS. Revert

커밋 내역을 수정할 시, `git reset`은 이전 상태로 되돌려놓으면서 커밋 히스토리를 삭제한다. 반면, `git revert`는 이전 커밋 내역을 그대로 남겨두면서 revert 커밋을 추가한다.

그러므로 혼자 작업하는 브랜치에서는 `git reset`을 사용해도 되지만, 다른 사람과 공유하는 브랜치에서는  `git revert`를 사용해야 한다.



## Reset option

- `--soft` : commit 하기 전 상태(staging area)로 되돌려 놓는다.
- `--mixed`(default) : add 하기 전 상태(working directory)로 되돌려 놓는다.
- `--hard` :  commit된 파일들 중 tracked 파일들을 working directory에서 삭제한다.



## 상대 참조

- `^` : 직전 위치
  - 예시) `$ git checkout HEAD^` : HEAD 직전 위치(HEAD : 현재 작업트리의 가장 최근 커밋)
- `~{num}` : {num}은 돌아가고 싶은 커밋의 개수
  - 예시) C0-C1-C2-C3-C4(HEAD) 상태에서  `$ git checkout HEAD~4` : C0 상태로 되돌림
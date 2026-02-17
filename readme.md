## local 저장소 dir 생성
```bash
mkdir myfirstrepo
cd myfirstrepo
```

## local git 저장소 생성 및 환경 설정
```bash
git init

<<<<<<< HEAD
git config --global user.name "***"
git config --global user.email "***"
=======
git config --global user.name "us***me"
git config --global user.email "us***me@***.***"
>>>>>>> 0d939f1 (readme add)
git config --global --list
```

## 추적대상 스테이징: git add 추적 대상 등록
```
vi test.txt
git add test.txt
git status
```

## 변경사항 local 반영
```
git commit -m "my first commit"
git log
```

## remote Repository연동
> github에 Repository 생성 후 아래 수행(저장소 명은 local명과 동일) \
형식: `git remote add <단축이름> https://github.com/<githubID>/저장소명.git`
```
git remote add origin https://github.com/***/myfirstrepo.git
git remote -v
```
## 원격 저장소에 저장 git push
> github Access Token생성 필요
> - 생성 경로 
>   - Settings->Develober Settings -> Personal Access tokens -> Generate new token -> Generate token \
>   - 생성당시 한번만 확인가능하므로 별도 보관 필요
>     - "***"

> 형식: git push <저장소명> <브랜치명>
```
git push origin master
```

## git 원격 저장소 로컬에 다운로드
> git clone https://github.com/<gitID/<저장소>.git \
> 저장소명과 동일한 폴더가 생성됨

```
git clone https://github.com/****/myfirstrepo.git
```

## 원격 저장소 local반영 (다운로드)
```
git pull origin master
```

## commit한 내용 되돌리기: git revert
> git revert <commit number> \
> commit number는 `git status`로 확인

```
git revert ***
```

## Git Branch 관리 명령어

| 기능 | Git 명령어 | 설명 |
| :--- | :--- | :--- |
| **현재 브랜치 확인** | `git branch` | 현재 로컬에 존재하는 브랜치 목록과 작업 중인 브랜치를 확인합니다. |
| **브랜치 생성** | `git branch <branch name>` | 새로운 로컬 브랜치를 생성합니다. |
| **브랜치 이동** | `git checkout <branch name>` 또는 `git switch <branch name>` | 작업 환경을 지정한 브랜치로 전환합니다. (최신 버전은 `switch` 권장) |
| **원격 저장소 반영** | `git push origin <branch name>` | 로컬에서 만든 브랜치를 원격 저장소(`origin`)에 업로드합니다. |
| **로컬 브랜치 삭제** | `git branch -D <branch name>` | 지정한 로컬 브랜치를 삭제합니다. (`-D`는 강제 삭제) |
| **원격 브랜치 삭제** | `git push origin :<branch name>` | 원격 저장소에 있는 브랜치를 삭제합니다. |

---
> **Tip:** 브랜치를 생성함과 동시에 이동하고 싶다면 `git checkout -b <branch name>` 또는 `git switch -c <branch name>`을 사용해 보세요!

> branch 생성 삭제 예제
>
> ``` bash
> git branch
> git branch branchtest
> git switch branchtest
> git branch
> vi branchtest.txt
> git status
> git add branchtest.txt
> git commit -m "branch test"
> git status
> git push origin branchtest
> git switch master
> git branch -D branchtest
> git branch
> git push origin :branchtest
> ```
 


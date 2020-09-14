# Git 폴더 생성

```bash
- mkdir hello-git-cli
- cd hello-git-cli
- pwd
- git status
```

# Git 저장소 초기화

```bash
1. git init
1. ls a
1. git status
```

# Git 전역 옵션 설정

- git config --global user.name "Cat Hanbit"
- git config --global user.email "hello@gmail.com"

# Git 기본 에디터 확인

- git config core.editor
- git config --global core.editor
- git config --system core.editor

# 간단한 텍스트 파일 생성하고 확인 하기

- echo "hello git"
- echo "hello git" >> file1.txt
- ls
- git status

# 생성한 파일 스테이지에 추가하기

- git add file1.txt
- git status

# 스테이지에서 파일 언스테이징 하기

- git status
- git reset file1.txt
- git status
- ls
- cat file1.txt

# 첫번째 CLI 커밋

1. git add file1.txt
1. git status
1. git commit

# 커밋 확인 해보기

1. git status
1. git log --oneline --graph --all --decorate

# 원격저장소 등록 및 push

```bash
git remote add origin https://github.com/~~~~~
git remote -v
git push fail!!!!

git push -u origin master
git log --online -n1
git push
```

# git clone 사용해 보기

```bash
pwd
cd ..
git clone https://github.com/~~~~~~ fail!!!
```

# git clone 으로 로컬 저장소 복제하기

```bash
git clone https://github.com/~~~~~~ .
ls
cd hello-git cli2
git log --oneline
git remote -v
```

# 추가 commit and push

```bash
echo "second" >> file1.txt
cat file1.txt
git commit -a # 스테이징 없이 바로 커밋
git push
git log --oneline
```

# git pull

```bash
cd hello-git-cli
git log --oneline
git pull
git log --oneline
cat file1.txt
```

# Chapter 7 브랜치 생성 및 조작하기

## 01. CLI로 브랜치 생성하기

### 브랜치 만들기

```bash
cd hello-git-cli
git log --online
git branch
git branch mybranch1
git branch
git log --online --all
```

## 02. CLI로 checkout 하기

#### 브랜치 만들기

```bash
gti checkout mybranch1
git branch
git log --oneline --all
cat file1.txt
echo "third - my branch" >> file1.txt
cat file1.txt
git status
git add file1.txt
git commit
git log --oneline --all
```

#### 커밋 후 빨리감기 병합

```bash
echo "fourth -my branch" >> file1.txt
cat file1.txt
git status
git add file1.txt
git commit
git log --oneline --all -graph
git checkout master
cat file1.txt
git merge mybranch1
git log --online --all -graph
cat file1.txt
```

### reset --hard로 브랜치 되돌리기

#### 현재 브랜치를 두 단계 이전으로 되돌리기

```bash
git reset --hard HEAD~2
git log --oneline --all
```

#### @reset --hard 명령어와 동일

```bash
git checkout HEAD~2
git branch -f master
git checkout master
```

### 빨리 감기 병합 상황에서 rebase 해보기

#### rebase, push, branch 제거

```bash
git checkout mybranch1
git rebase master
git log --oneline --all
git checkout master
git rebase mybranch1
git log --oneline --all
git push
git branch -d mybranch1
git log --oneline --all -n2
```

### 배포 버전에 태깅하기

#### tag 작성

```bash
git log --online
git tag -a -m "first tag adding" v0.1
git push origin v0.1
```

# CLI로 3way 병합하기

```bash
git checkout master
git checkout -b feature1
echo "기능 1 추가" >> file1.txt

git add file1.txt
git commit

git log --oneline --graph --all -n2
```

# hotfix 브랜치 생성, 커밋, master 에 병합

```bash
git checkout -b hotfix master
git log --oneline --all -n2
echo "some hot fix" >> file1.txt
git add file1.txt
git commit
git log --oneline -n1
git checkout master
git merge hotfix
git push
```

# 병합 및 충돌 해결하기 1

```bash
git checkout feature1
git log --oneline --all
git merge master
git status
```

# 병합 및 충돌 해결하기 2

```bash
cat file1.txt
git add file1.txt
git status
git commit
git log --oneline --all --graph -n4
```

# reset --hard 및 rebase 시도

```bash
git checkout feature1
git reset --hard HEAD~
git log --oneline --graph --all -n3
git rebase master
git push
```

# 충돌 해결 및 rebase 이어서 하기

```bash
git status # 충돌 수동 해결 할것
git add file1.txt
git status
git rebase --continue
git log --oneline --graph --all -n2
git checkout master
git merge feature1
```

# 유용한 rebase의 사용법

## 1. 보통 커밋 만들기

## 2. 가지 커밋 만들기

## 3. git pull 수행 결과

## 4. rebase 로 가지 없애기

# 임시 브랜치 사용하기

## 임시 브랜치 생성 사용 및 삭제

```bash
git branch test feature1
git checkout test
echo "아무말 대잔치" > test.txt
git add .
git commit -m "임시 커밋"
git log --oneline --graph --all -n4
git checkout master
git branch -D test
git log --oneline --graph --all -n3
```

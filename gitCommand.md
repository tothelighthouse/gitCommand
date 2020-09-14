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

# 브랜치 만들기

```bash
cd hello-git-cli
git log --online
git branch
git branch mybranch1
git branch
git log --online --all
```

# 02. CLI로 checkout 하기

## 브랜치 만들기

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

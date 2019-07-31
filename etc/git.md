# git

## 사용법

```bash
# repository 복제
git clone <git 주소>

# 변경된 파일 추가
git add <파일 이름>
# 변경된 모든 파일 추가
git add .

# 변경된 file local repository에 저장
git commit -m "<message>"

# 로컬 branch를 새로 생성호 원격 저장소에 해당 branch를 push
git push -u "<remote>" "<branch name>"

# 변경 사항 원격 저장소에 저장
git push "<remote>" "<branch name>"

# branch 변경 및 생성
git checkout "<branch name>"

# 원결 repository에서 내용을 가져와 병합
git pull


```

## git-flow

git branch를 관리하는 방법
- https://gist.github.com/ihoneymon/a28138ee5309c73e94f9
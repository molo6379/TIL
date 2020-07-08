# Github 활용 예시

## `clone`

> 원격 저장소를 복제 해온다.

```
~/집 $ git clone https://github.com/edutak/TIL--nlp.git
~/집 $ cd TIL--nlp
~/집/TIL--nlp (master) $
```

- 복제 하는 경우 원격저장소 이름의 폴더가 생성된다.
- 해당 폴더로 이동하여 활용을 하면 된다.
- 이후 작업을 하는 경우 `add`, `commit`, `push`

## `pull`

> 원격 저장소의 변경사항을 받아온다.

```
~/Desktop/TIL (master) $ git pull origin master
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 563 bytes | 5.00 KiB/s, done.
From https://github.com/edutak/TIL--nlp
 * branch            master     -> FETCH_HEAD
   b523707..187ed91  master     -> origin/master
Updating b523707..187ed91
Fast-forward
 ...hub \355\231\234\354\232\251 \354\230\210\354\213\234.md" | 12 ++++++++++++
 1 file changed, 12 insertions(+)
 create mode 100644 "Github \355\231\234\354\232\251 \354\230\210\354\213\234.md"
```
## Tistory to GitHub Page Migration

### 사용 방법
1. `blog_url`과 `image_save_dir` 값 수정
2. `start_page_no`와 `end_page_no`에 수집할 게시글 번호 range 입력
3. 전체 코드 실행
4. 생성된 `_posts`와 `assets`를 GitHub Page에 복사
5. GitHub Page 동작 확인
6. code syntax 등을 직접 수정


### 수집 방식
1. 수집할 게시글 번호 range(`start_page_no`~`end_page_no`) 내의 게시글을 전부 수집
    - 없는 게시글(**404**)이 있으면 pass
2. 게시글 본문 및 이미지, metadata 수집
    2.1. 게시글 본문 포맷을 markdown으로 변경(markdownify, ATX)
    2.2. 본문 상단에 metadata 정보 입력
    2.3. 이미지는 순서대로 **img-{no}.png**로 저장
    2.4. 본문 내 이미지를 GitHub Page 이미지 저장 위치(`image_save_dir`)로 치환
    2.5. 게시글 파일명은 **{year}-{month}-{day}-tistory-post-{page_no}.md**



### 수집 항목 (metadata)
1. 제목
2. 본문
3. 작성 년, 월, 일
4. 카테고리
5. 태그
6. 이미지


### 주의 사항
1. tag에 숫자만 있으면 오류 발생, 태그 변경 후 사용
    ```
    Liquid Exception: undefined method `gsub' for 6.0:Float string.gsub(replaceable_char, "-") ^^^^^ in /Users/hyojpark-mn/Applications/vscode_projects/hyojupark.github.io/_layouts/single.html
    ```

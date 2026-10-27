# GitHub에 새 사이트 통째로 올리기 (2026-10-26)

## 0. 지금 저장소 백업
1. github.com/bannaya-4rang/bandithefirefly → 초록 **Code** 버튼 → **Download ZIP**. 받은 파일을 `bandithefirefly-backup-2026-10-26.zip`으로 이름 바꿔 보관.
2. (선택) 저장소 왼쪽 위 **main ▾** → 입력칸에 `backup-2026-10-26` 입력 → "Create branch backup-2026-10-26 from main". 옛 사이트가 브랜치로 그대로 남는다.

## 1. 옛 파일 전부 지우기 (github.dev)
1. 저장소 페이지에서 키보드 **.** (마침표) → 브라우저에 VS Code가 열린다.
2. 왼쪽 탐색기에서 첫 파일 클릭 → Shift 누른 채 마지막 파일 클릭 → **Delete**(또는 우클릭 → Delete). 폴더(img, video)도 함께.
3. 왼쪽 가지 모양 아이콘(Source Control) → 메시지 `clear old site` → **Commit & Push** (✓).
   - 이 순간 사이트는 잠시 비어 보인다. 2단계까지 10분이면 끝난다.

## 2. 새 파일 올리기 (GitHub 웹)
1. `bandithefirefly-site.zip`을 PC에서 압축 해제. 안에 html 12개, README.md, resume.pdf, UPLOAD-GUIDE.md, `img/`, `video/`가 있다.
2. 저장소 페이지 → **Add file ▾ → Upload files**.
3. 압축 푼 폴더를 열고 **안의 것들을 전부 선택**(Ctrl+A)해서 업로드 창에 **끌어다 놓기**. 폴더째 끌면 `img/…`, `video/…` 경로가 유지된다.
   - 한 번에 100개까지만 받으므로 두 번에 나눠 올린다:
     1) html 전부 + README.md + resume.pdf + `video` 폴더 (약 20개)
     2) `img` 폴더 (약 140개 → `img/tiles`를 따로 한 번 더 올려야 할 수 있다. "100 files" 경고가 뜨면 `img` 안의 `tiles` 폴더를 빼고 먼저 올린 뒤, `img` 폴더로 들어가서 `tiles` 폴더만 다시 올린다.)
4. 아래 **Commit changes**. 1~2분 뒤 Cloudflare가 배포한다.

## 3. 확인
- bandithefirefly.com 을 **Ctrl+F5**로 열어 홈·Games·Seeds·About을 한 번씩 본다.
- Error 404 videogame, Morning Routine, Chicken Population 페이지에서 영상이 재생되는지 본다.
- 안 보이는 그림이 있으면 그 파일이 `img/` 안에 있는지 저장소에서 확인한다.

## 이번 버전에 들어 있는 것
- USC 포트폴리오 문서 6종과 맞춘 게임 페이지 (제목: Error 404: File Has Been Corrupted / Unfinished / Unreal Engine Shooter)
- 새 페이지: Chicken Population in Minecraft (Math AA IA, 진행 중)
- The Walk Home은 Games가 아니라 Seeds 맨 위 ("The one I'm about to build")
- About 완성본, resume.pdf, 메뉴 순서 Home · Sticks · Games · Seeds · About

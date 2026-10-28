# 5월 25일 호우 대응 보도자료 사이트

정적 사이트입니다. 빌드 과정이 없습니다.

## 파일
- index.html : 페이지 본체 (카드 + 검색 + 매트릭스)
- data/press.json : 보도자료 데이터
- matrix.csv : Google Sheets에 가져올 정합성 매트릭스
- netlify.toml / vercel.json : 배포 설정

## Google Sheets 임베드 설정
1. Google Sheets에서 새 시트를 만들고 파일 → 가져오기 → 업로드로 matrix.csv를 불러옵니다.
2. 파일 → 공유 → 웹에 게시 → "삽입" 탭 → 게시.
3. 나온 iframe 코드의 src="..." 주소를 복사합니다.
4. index.html의 `const SHEET_EMBED_URL = "";` 따옴표 안에 붙여넣습니다.

## 배포
- Netlify: 폴더 전체를 app.netlify.com/drop 에 끌어놓거나 Git 연결 (Publish directory: `.`).
- Vercel: 폴더에서 `vercel --prod`, 또는 Git 연결 (Framework: Other, Build command 비움).

로컬 확인은 `python3 -m http.server` 후 http://localhost:8000. 파일을 직접 열면 JSON fetch가 막히지만 내장 데이터로 대체 표시됩니다.

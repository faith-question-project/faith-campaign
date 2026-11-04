# 믿음이 자격이 되는 순간

종교적 자격 요건과 채용의 공정성을 질문하는 인터랙티브 캠페인 웹앱입니다.
서버 없이 동작하는 정적 사이트라 GitHub Pages에 그대로 올리면 됩니다.

## 파일 구조

```
index.html     화면 뼈대
style.css      디자인
script.js      동작 + 슬로건/기사 데이터
assets/
  article1.jpg 기사 자료 01 원본 이미지
  article2.jpg 기사 자료 02 원본 이미지
```

## GitHub Pages에 올리기 (코딩 없이 웹에서)

1. github.com 로그인 → 오른쪽 위 **+** → **New repository**
2. 이름 입력(예: `faith-campaign`) → **Public** 선택 → **Create repository**
3. 새 저장소 화면에서 **uploading an existing file** 클릭
4. 압축을 푼 폴더 안의 파일을 **전부** 끌어다 놓기
   (`index.html`, `style.css`, `script.js`, `assets` 폴더 — `assets` 폴더째로 끌어오면 됩니다)
5. 아래 **Commit changes** 클릭
6. 저장소의 **Settings → Pages** 이동
7. **Source: Deploy from a branch**, **Branch: main / (root)** 선택 → **Save**
8. 1~2분 뒤 같은 화면 위쪽에 주소가 나타납니다.
   예: `https://아이디.github.io/faith-campaign/`

> 주의: `index.html`이 저장소 맨 위(루트)에 있어야 합니다. 폴더 하나 안에 들어가 있으면 주소 뒤에 폴더명을 붙여야 열립니다.

## QR코드 만들기

1. 위에서 받은 주소를 복사
2. 아이폰: Safari로 주소를 연 뒤 공유 버튼 → **QR 코드** (iOS 17+), 또는
   QR 생성 사이트(예: qr-code-generator 류)에 주소를 붙여 넣고 PNG 저장
3. 인쇄물·포스터에 삽입. 인쇄 전 실제 폰으로 한 번 찍어서 열리는지 꼭 확인하세요.

특정 화면으로 바로 열리게 하고 싶다면 주소 끝에 붙이면 됩니다.

| 화면 | 주소 끝 |
|---|---|
| 홈 | `#/` |
| 질문 01~04 | `#/q/1` ~ `#/q/4` |
| 질문 목록 | `#/questions` |
| 자료실 | `#/archive` |
| 기사 01 / 02 | `#/article/1`, `#/article/2` |

## 내용 수정·추가하기

모두 `script.js` 맨 위의 배열에서 합니다.

- **슬로건 추가**: `SLOGANS` 배열에 `{ title: '...', body: [ { t: '...' }, { t: '...', em: true } ] }` 추가
  (`em: true`인 줄이 버건디색 강조)
- **기사 추가**: 이미지를 `assets/article3.jpg`로 넣고 `ARTICLES` 배열에 항목 추가
- 이미지 파일이 없으면 자동으로 "이미지를 추가해 주세요" 안내가 뜨고, 같은 이름으로 넣으면 바로 표시됩니다.

목록·홈 카드·이전/다음 버튼은 배열을 기준으로 자동 생성됩니다.

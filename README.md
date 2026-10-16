# THE ISSUE 웹 이북 — 운영·업데이트 가이드

## 폴더 구조
```
index.html        화면(수정 불필요)
data/issues.js    모든 내용 데이터 ← 매월 이 파일만 수정
pdf/              원문 PDF (volXX-N.pdf)
img/              표지 배경 사진
```

## 새 호(예: Vol.24, 10월) 추가 2단계
1. `pdf/`에 `vol24-1.pdf`, `vol24-2.pdf` … 넣기
2. `data/issues.js`의 `issues` 배열 마지막 `}` 뒤에 쉼표를 찍고 아래 블록 추가

```js
{
  vol: 24, month: 10, date: "2026. 10.", color: "#2f5d8a",
  panelTitle: "패널 제목",
  headline: "표지 대표 문구\n세 줄까지",
  articles: [
    { id: "vol24-1", icon: "chart", group: "policy", category: "카테고리",
      title: "기사 제목",
      summary: "한두 문장 요약",
      points: ["핵심 1", "핵심 2", "핵심 3"] }
  ]
}
```
- `group`: policy(정책·제도) / finance(재정·사업) / student(학생·입학·통계) / field(현장·사례·해외)
- `color`: 표지·카드 색(#RRGGBB), `panelTitle`: 펼침 패널 제목, `icon`: 카드 아이콘 이름(issues.js 상단 목록 참고)
- 콤보상자·주제 분포·상단 통계는 데이터에서 자동 계산됩니다.
- 아직 발간 전인 달(~12월)은 "발간 예정" 자리로 표시되고, 데이터를 추가하면 자동으로 실제 표지로 바뀝니다.
- 내년 운영 시 `site.year`, `site.lastMonth` 값만 바꾸면 됩니다.

## 게시 방법
- 연구소 홈페이지/웹서버: 폴더 전체를 그대로 업로드 → `index.html` 접속
- PDF 뷰어(pdf.js)와 글꼴은 CDN에서 불러오므로 인터넷 연결 필요
- 로컬 PC에서 index.html을 더블클릭하면 PDF 뷰어가 막힐 수 있음 → 웹서버에 올려서 확인

## 특정 호로 바로 연결
`index.html#vol20` 처럼 주소 뒤에 `#vol호수`를 붙이면 해당 월이 펼쳐진 상태로 열립니다.

# THE ISSUE 2026 — 웹 이북 아카이브

한국고등직업교육연구소 월간 정책 브리프 「THE ISSUE」의 2026년 발간호(Vol.17~)를 모은 웹 이북 사이트입니다.

- 공개 주소: https://hver-theissue.pages.dev/ (Cloudflare Pages, 이 저장소에 올리면 자동 배포)

## 폴더 구조
```
index.html            메인(연구소 소개 · 월별 표지 · 기사 카드 · PDF 뷰어)
data/issues.js        호·기사 데이터 (표지 문구, 색상, 카드 요약)
ebook/volNN.html      호별 플립북 이북
ebook/volNN/pNN.jpg   이북 쪽 이미지 (s/ 폴더는 미리보기용 작은 이미지)
pdf/volNN-N.pdf       기사별 PDF
img/og/               카톡·SNS 공유 썸네일
_headers              Cloudflare 캐시 설정 (이미지·PDF 30일)
```

## 새 호 추가 순서
1. 기사별 PDF(디자인본 또는 원고본)와 연구소 소식을 준비해 Claude에 요청
2. Claude가 이북 쪽 이미지·PDF·데이터·썸네일을 만들어 이 저장소에 커밋
3. Cloudflare Pages가 1~2분 안에 자동으로 사이트를 갱신

## 운영 원칙
- 이미 발간된 호의 파일은 바꾸지 않습니다 (캐시·업로드 효율 유지).
- 특정 호 바로가기: `index.html#vol20`, 특정 기사 이북: `ebook/vol24.html#vol24-2`

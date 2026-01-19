# VSCode + Miniconda + GitHub Copilot 바이브코딩 실습 자료

## 파일 구성

| 파일 | 용도 |
|------|------|
| `vibe-coding-workshop.md` | Marp 마크다운 (PPT/PDF 변환용) |
| `vibe-coding-workshop.html` | reveal.js HTML (브라우저에서 바로 발표) |

---

## 사용 방법

### Marp (.md)
1. VSCode에서 **Marp for VS Code** 확장 설치
2. 파일 열기 → 우측 상단 **Marp 아이콘** → **Export Slide Deck**
3. PDF 또는 PPTX로 내보내기

### reveal.js (.html)
1. `vibe-coding-workshop.html` 더블클릭 → 브라우저에서 발표
2. 방향키로 슬라이드 이동
3. `F` 키로 전체화면

---

## 디자인 스펙

- **폰트**: Pretendard (웹 CDN 자동 로드)
- **배경**: 흰색 (#ffffff)
- **스타일**: 미니멀
- **제목 색상**: 파란색 (#0066cc)
- **레이아웃**: 제목 상단 고정 + 본문 왼쪽 정렬, 타이틀/마지막 슬라이드는 중앙 정렬

---

## 수정 시 참고사항

### 슬라이드 구조
- 일반 슬라이드: `<section>` 태그 사용
- 중앙 정렬 슬라이드: `<section class="center">` 사용 (타이틀, 마지막 장)

### 어투
- 격식체 사용 (딱딱한 문체)
- 이모지 미사용

### 스크린샷 추가 위치
HTML 파일 내 `<!-- [스크린샷: ...] -->` 주석 위치에 이미지 삽입

```html
<img src="screenshot.png" alt="설명" style="max-width: 80%;">
```

---

## 작업 이력

### 요청 사항
1. VSCode + Miniconda(가상환경) + GitHub Copilot 바이브코딩 실습 PPT
2. 대상: 프로그래밍 초보 (오래 안 하신 기업 직원/팀장급)
3. 실시간 따라하기 + 나중에 가이드로 재사용 가능해야 함
4. Marp / reveal.js 두 형태로 작성
5. Pretendard 폰트, 흰색 배경, 미니멀 디자인
6. 어투: 격식체 (딱딱하게)
7. 타이틀/마지막 슬라이드: 가로/세로 완전 중앙

### 슬라이드 목차 (21장)
1. 타이틀
2. 실습 내용 개요
3. 가상환경 필요성
4. Miniconda 다운로드
5. Miniconda 설치 진행
6. Miniconda 설치 확인
7. VSCode 다운로드/설치
8. VSCode 확장 프로그램 설치
9. GitHub 로그인
10. 프로젝트 폴더 생성
11. 가상환경 생성
12. 가상환경 활성화
13. 인터프리터 선택
14. 파일 생성
15. Copilot 자동완성
16. Copilot Chat
17. 코드 실행
18. 트러블슈팅
19. 명령어 치트시트
20. 요약
21. 마무리

---

## 향후 수정 프롬프트 예시

```
C:\Users\User\Desktop\실습 폴더에 있는 vibe-coding-workshop.html 파일 수정해줘.

[수정 요청 내용 작성]

디자인 스펙:
- Pretendard 폰트, 흰색 배경, 미니멀
- 격식체 어투, 이모지 미사용
- 타이틀/마지막 슬라이드는 중앙 정렬
```

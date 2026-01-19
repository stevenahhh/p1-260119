---
marp: true
theme: default
paginate: true
style: |
  @import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css');
  
  * {
    font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, sans-serif;
  }
  
  section {
    background: #ffffff;
    color: #1a1a1a;
  }
  
  h1 {
    color: #0066cc;
    font-weight: 700;
  }
  
  h2 {
    color: #333333;
    font-weight: 600;
  }
  
  code {
    background: #f4f4f4;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 0.9em;
  }
  
  pre {
    background: #1e1e1e;
    color: #d4d4d4;
    padding: 20px;
    border-radius: 8px;
  }
  
  .highlight {
    background: #fff3cd;
    padding: 4px 8px;
    border-radius: 4px;
  }
  
  table {
    font-size: 0.85em;
  }
  
  th {
    background: #f0f0f0;
  }
---

# VSCode + Miniconda + GitHub Copilot
## 바이브코딩 실습 가이드

**오늘의 목표**: AI와 함께 코딩하는 환경 만들기

---

# 오늘 할 것 (딱 3가지!)

| 순서 | 할 일 | 소요 시간 |
|:---:|------|:---:|
| 1 | Miniconda 설치 | 5분 |
| 2 | VSCode 설치 & 설정 | 5분 |
| 3 | GitHub Copilot으로 코딩 | 10분 |

> 💡 **바이브코딩**이란?  
> AI에게 "이런 거 만들어줘"라고 말하면 AI가 코드를 작성해주는 방식

---

# 왜 가상환경이 필요한가요?

## 비유: 프로젝트마다 다른 작업방

| 상황 | 가상환경 없이 | 가상환경 사용 |
|-----|-------------|-------------|
| 프로젝트 A | Python 3.8 필요 | ✅ A 전용 방 |
| 프로젝트 B | Python 3.11 필요 | ✅ B 전용 방 |
| 결과 | ❌ 충돌 발생! | ✅ 각자 독립 |

> 가상환경 = **프로젝트마다 독립된 작업 공간**

---

# Step 1: Miniconda 설치

## 1-1. 다운로드

1. 브라우저에서 검색: `miniconda download`
2. 또는 직접 접속: https://docs.conda.io/en/latest/miniconda.html
3. **Windows 64-bit** 버전 다운로드

<!-- [스크린샷: Miniconda 다운로드 페이지] -->

---

# Step 1: Miniconda 설치

## 1-2. 설치 진행

1. 다운로드한 파일 실행
2. **Next** 클릭
3. **I Agree** 클릭
4. **Just Me** 선택 → **Next**
5. 설치 경로 그대로 → **Next**
6. ⚠️ **중요!** 아래 옵션 체크:
   - ✅ `Add Miniconda3 to my PATH environment variable`
7. **Install** 클릭

<!-- [스크린샷: PATH 옵션 체크 화면] -->

---

# Step 1: Miniconda 설치

## 1-3. 설치 확인

1. **Windows 키** 누르고 `cmd` 입력 → Enter
2. 아래 명령어 입력:

```bash
conda --version
```

3. 이렇게 나오면 성공! ✅

```
conda 24.x.x
```

> ❌ `conda은(는) 인식할 수 없는 명령입니다` → 컴퓨터 재시작 후 다시 시도

---

# Step 2: VSCode 설치

## 2-1. 다운로드 & 설치

1. 브라우저에서 검색: `vscode download`
2. 또는 직접 접속: https://code.visualstudio.com
3. **Download for Windows** 클릭
4. 설치 파일 실행 → 전부 **다음** 클릭

<!-- [스크린샷: VSCode 다운로드 페이지] -->

---

# Step 2: VSCode 설치

## 2-2. 필수 확장 프로그램 설치

VSCode 실행 후:

1. 왼쪽 사이드바 **확장** 아이콘 클릭 (또는 `Ctrl + Shift + X`)
2. 검색창에 입력 후 **Install** 클릭:

| 확장 프로그램 | 용도 |
|-------------|-----|
| `Python` | Python 개발 지원 |
| `GitHub Copilot` | AI 코딩 도우미 |

<!-- [스크린샷: 확장 프로그램 설치 화면] -->

---

# Step 2: VSCode 설치

## 2-3. GitHub 로그인 (Copilot 활성화)

1. VSCode 왼쪽 하단 **사람 아이콘** 클릭
2. **Sign in with GitHub** 클릭
3. 브라우저에서 GitHub 로그인
4. **Authorize** 클릭

> ⚠️ GitHub Copilot은 유료입니다 (월 $10, 학생/오픈소스 무료)
> 무료 체험 가능!

<!-- [스크린샷: GitHub 로그인 화면] -->

---

# Step 3: 가상환경 만들기

## 3-1. 프로젝트 폴더 만들기

1. 바탕화면에 `my_project` 폴더 생성
2. VSCode에서 **File → Open Folder** → 해당 폴더 선택

---

# Step 3: 가상환경 만들기

## 3-2. 터미널 열기 & 가상환경 생성

1. VSCode 상단 메뉴: **Terminal → New Terminal**
2. 아래 명령어 입력:

```bash
conda create -n myenv python=3.11
```

3. `Proceed ([y]/n)?` 나오면 → `y` 입력 → Enter

> `myenv` = 가상환경 이름 (원하는 이름으로 변경 가능)

---

# Step 3: 가상환경 만들기

## 3-3. 가상환경 활성화

```bash
conda activate myenv
```

터미널 맨 앞에 `(myenv)` 표시되면 성공! ✅

```
(myenv) C:\Users\내이름\Desktop\my_project>
```

---

# Step 3: 가상환경 만들기

## 3-4. VSCode에서 인터프리터 선택

1. `Ctrl + Shift + P` 누르기
2. `Python: Select Interpreter` 입력 → Enter
3. 목록에서 `myenv` 포함된 항목 선택

<!-- [스크린샷: 인터프리터 선택 화면] -->

> 이제 VSCode가 우리 가상환경을 사용합니다!

---

# Step 4: 바이브코딩 시작!

## 4-1. 파일 만들기

1. VSCode 왼쪽 탐색기에서 **새 파일** 아이콘 클릭
2. 파일 이름: `main.py`

---

# Step 4: 바이브코딩 시작!

## 4-2. Copilot과 대화하기

`main.py` 파일에 주석으로 원하는 것을 적습니다:

```python
# 1부터 10까지 숫자를 출력하는 코드
```

→ Enter 누르고 잠시 기다리면 Copilot이 코드 제안!

```python
# 1부터 10까지 숫자를 출력하는 코드
for i in range(1, 11):
    print(i)
```

> **Tab** 키로 제안 수락, **Esc** 키로 거절

---

# Step 4: 바이브코딩 시작!

## 4-3. Copilot Chat 사용하기

더 복잡한 요청은 채팅으로!

1. `Ctrl + Shift + I` (Copilot Chat 열기)
2. 대화창에 입력:

```
사용자 이름을 입력받아서 환영 메시지를 출력하는 코드 만들어줘
```

3. Copilot이 전체 코드 제안 → **Insert at Cursor** 클릭

---

# Step 4: 바이브코딩 시작!

## 4-4. 코드 실행하기

1. 터미널에서:

```bash
python main.py
```

2. 또는 VSCode에서 **▶️ 재생 버튼** 클릭 (우측 상단)

```
실행 결과:
1
2
3
...
10
```

---

# 트러블슈팅

## 자주 발생하는 문제

| 증상 | 해결 방법 |
|-----|----------|
| `conda 명령어를 찾을 수 없음` | 컴퓨터 재시작 후 다시 시도 |
| Copilot 제안이 안 나옴 | GitHub 로그인 확인, 구독 상태 확인 |
| `(myenv)`가 안 보임 | `conda activate myenv` 다시 실행 |
| 인터프리터 목록에 myenv 없음 | VSCode 재시작 후 다시 검색 |

---

# 유용한 명령어 모음

## Conda 명령어 치트시트

| 명령어 | 설명 |
|-------|------|
| `conda create -n 이름 python=3.11` | 가상환경 생성 |
| `conda activate 이름` | 가상환경 활성화 |
| `conda deactivate` | 가상환경 비활성화 |
| `conda env list` | 모든 가상환경 목록 |
| `conda install 패키지명` | 패키지 설치 |
| `conda remove -n 이름 --all` | 가상환경 삭제 |

---

# 요약

## 오늘 배운 것

1. ✅ **Miniconda** 설치 → Python 가상환경 관리
2. ✅ **VSCode** 설치 → 코드 편집기
3. ✅ **가상환경** 만들기 → 프로젝트별 독립 환경
4. ✅ **GitHub Copilot** → AI와 함께 코딩

## 다음 단계

- 패키지 설치해보기: `conda install pandas numpy`
- Copilot에게 더 복잡한 것 요청해보기
- 나만의 프로젝트 시작하기!

---

# 감사합니다! 🎉

## 질문 있으시면 편하게 물어보세요

<!-- [연락처 또는 추가 리소스 정보] -->

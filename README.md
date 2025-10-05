AI 기반 기업 분석 포트폴리오
DART(전자공시시스템) API와 Google Gemini API를 연동하여, 취업 준비생의 관점에서 관심 있는 기업의 최신 정보를 바탕으로 심층적인 AI 분석 리포트를 생성해주는 동적 웹 포트폴리오 프로젝트입니다.

🌟 주요 기능
기업 검색: 국내 법인의 고유번호(CORPCODE.xml 기반)를 이용해 빠르고 정확한 기업 검색 기능을 제공합니다.

실시간 기업 정보 조회: DART API를 통해 기업의 최신 개요 및 재무 정보를 실시간으로 조회합니다.

AI 정성 분석 리포트: Google Gemini API를 활용하여 조회된 기업 정보를 바탕으로 아래 항목들을 포함한 종합 분석 리포트를 생성합니다.

기업 비전 및 핵심 가치

주요 제품 및 서비스

재무 실적 요약 및 SWOT 분석

산업 및 경쟁사 분석

지원 직무(프론트엔드 개발자) 맞춤 분석

입사를 위한 자기계발 액션플랜 제안

동적 UI: 분석된 모든 데이터를 웹페이지에 동적으로 렌더링하여 사용자에게 직관적인 경험을 제공합니다.

🛠️ 기술 스택
구분

기술

Frontend

HTML, CSS, JavaScript (Vanilla)

Backend

Python, Flask

APIs

DART Open API, Google Gemini API

📂 프로젝트 구조
.
├── 📄 PortFolio.html       # 프론트엔드 단일 페이지
├── 🐍 app.py               # 백엔드 Flask 서버
├── 🔑 .env                 # API 키 및 환경변수 설정 파일
├── 📦 requirements.txt     # Python 의존성 목록
├── 🗂️ CORPCODE.xml         # DART 기업 고유번호 데이터
└── 📖 README.md            # 프로젝트 설명서

🚀 시작하기
1. 사전 준비
Python 3.8 이상 설치

DART API 키 발급: DART 개발자 사이트에서 인증키를 발급받으세요.

Gemini API 키 발급: Google AI for Developers에서 API 키를 발급받으세요.

2. 백엔드 서버 실행
# 1. 프로젝트 클론
git clone [https://github.com/your-username/your-repository.git](https://github.com/your-username/your-repository.git)
cd your-repository

# 2. 가상환경 생성 및 활성화
python -m venv venv
# Windows
# venv\Scripts\activate
# macOS / Linux
# source venv/bin/activate

# 3. 필요한 라이브러리 설치
pip install -r requirements.txt

# 4. .env 파일 설정
# .env.example 파일을 복사하여 .env 파일을 생성합니다.
# (또는 아래 내용으로 .env 파일을 직접 생성합니다.)
cp .env.example .env

# 5. .env 파일에 발급받은 API 키를 입력합니다.
# DART_API_KEY=your_dart_api_key
# GEMINI_API_KEY=your_gemini_api_key

# 6. Flask 서버 실행
flask run
# 또는 python app.py

# 서버가 [http://127.0.0.1:5000](http://127.0.0.1:5000) 에서 실행됩니다.

3. 프론트엔드 실행
웹 브라우저에서 PortFolio.html 파일을 엽니다.

VS Code의 Live Server와 같은 확장 프로그램을 사용하면 CORS 문제없이 API를 원활하게 테스트할 수 있습니다.

⚙️ 환경변수 설정 (.env)
프로젝트 루트 디렉토리에 .env 파일을 생성하고 아래 내용을 채워주세요.

# DART 오픈 API 키 (금융감독원 DART에서 발급받은 키)
DART_API_KEY="여기에_DART_API_키를_입력하세요"

# Gemini API 키 (Google Cloud Console에서 발급받은 키)
GEMINI_API_KEY="여기에_GEMINI_API_키를_입력하세요"

# 허용할 프론트엔드 오리진 (쉼표로 구분)
# 로컬 개발 (Vite:5173, Live Server:5500) + 실제 배포 도메인 추가
ALLOWED_ORIGINS=http://localhost:5173,[http://127.0.0.1:5173](http://127.0.0.1:5173),http://localhost:5500,[http://127.0.0.1:5500](http://127.0.0.1:5500),[https://your-deploy-domain.com](https://your-deploy-domain.com)

# 서버 포트 (기본값: 5000)
PORT=5000

# 사용할 Gemini 모델 (기본값: gemini-1.5-flash-latest)
GEMINI_MODEL=gemini-1.5-flash-latest

🔗 데이터 흐름
사용자: PortFolio.html에서 분석하고 싶은 기업명을 입력하고 검색 버튼을 클릭합니다.

Frontend (JS): 백엔드 서버(app.py)의 /api/generate-analysis 엔드포인트로 기업명과 산업 분야를 담아 POST 요청을 보냅니다.

Backend (Flask):

요청을 받아 DART API로 기업 개요 및 재무 정보를 조회합니다.

조회된 DART 데이터를 바탕으로 Google Gemini API에 전달할 프롬프트를 구성합니다.

Gemini API를 호출하여 기업에 대한 심층 분석이 담긴 JSON 데이터를 응답받습니다.

Frontend (JS): 백엔드로부터 받은 최종 JSON 데이터를 파싱하여 웹페이지의 각 섹션에 동적으로 내용을 채워넣습니다.

사용자: AI가 생성한 기업 분석 리포트를 확인합니다.

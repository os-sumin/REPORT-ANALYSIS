# 🚀 Streamlit Cloud 배포 가이드

## 📋 준비물
1. GitHub 계정
2. 다운로드한 프로젝트 파일 (commercialization_report_app.zip)

## 🔧 배포 단계

### 1단계: GitHub 저장소 생성
1. https://github.com 접속 및 로그인
2. 우측 상단 **[+]** → **[New repository]** 클릭
3. 저장소 이름: `commercialization-report`
4. Public 선택
5. **[Create repository]** 클릭

### 2단계: 코드 업로드
```bash
# 다운로드한 ZIP 파일 압축 해제
unzip commercialization_report_app.zip -d commercialization-report

# Git 초기화 및 업로드
cd commercialization-report
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/당신의아이디/commercialization-report.git
git push -u origin main
```

**또는 GitHub 웹에서 직접 업로드:**
1. 저장소 페이지에서 **[Add file]** → **[Upload files]**
2. 압축 해제한 모든 파일 드래그 앤 드롭
3. **[Commit changes]** 클릭

### 3단계: Streamlit Cloud 배포
1. https://streamlit.io/cloud 접속
2. **[Sign up]** 또는 **[Sign in with GitHub]**
3. **[New app]** 클릭
4. 설정:
   - **Repository**: `당신의아이디/commercialization-report`
   - **Branch**: `main`
   - **Main file path**: `app.py`
5. **[Deploy!]** 클릭

### 4단계: 배포 완료
- 2~3분 후 배포 완료
- URL 형식: `https://당신의아이디-commercialization-report-app-xxx.streamlit.app`
- 이 URL을 팀원들과 공유!

## 🔐 환경 변수 설정 (선택)

향후 GPT API 연동 시:
1. Streamlit Cloud 앱 설정 페이지
2. **[Settings]** → **[Secrets]**
3. 아래 내용 추가:
```toml
OPENAI_API_KEY = "sk-..."
```

## 💡 로컬 테스트

배포 전 로컬에서 테스트:
```bash
cd commercialization-report
pip install -r requirements.txt
streamlit run app.py
```

브라우저에서 `http://localhost:8501` 자동 오픈

## ⚠️ 주의사항

1. **무료 플랜 제한**:
   - 앱 1개 (추가 앱은 유료)
   - CPU/메모리 제한
   - 활동 없으면 자동 슬립 (재접속 시 재시작)

2. **파일 크기**:
   - 업로드 파일 최대 200MB
   - 큰 PDF는 처리 시간 증가

3. **보안**:
   - Public 저장소 = 코드 공개
   - API 키는 반드시 Secrets에 저장

## 🆘 문제 해결

### 배포 실패 시
1. Streamlit Cloud 로그 확인
2. requirements.txt 버전 확인
3. Python 버전 (기본 3.11 사용)

### 앱이 느릴 때
- 무료 플랜은 리소스 제한
- 슬립 상태에서 깨어나는 중 (10~20초 소요)

## 📞 지원

- Streamlit 문서: https://docs.streamlit.io
- 커뮤니티: https://discuss.streamlit.io

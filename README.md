# 🎬 한국 영화 데이터 분석 프로젝트

## 📌 프로젝트 소개
이 프로젝트는 **TMDB API**를 활용하여 **한국에서 제작 및 개봉한 영화 데이터**를 수집, 전처리, 분석 및 시각화하는 것을 목표로 합니다.  
주요 분석 주제는 **장르별 트렌드, 흥행 요인, 배우·감독 네트워크 분석, 흥행 예측** 등입니다.  

---

## 🛠️ 설치 및 실행 가이드

### 1. TMDB API 키 설정
이 프로젝트에서는 TMDB API를 사용합니다.  
1. [TMDB](https://www.themoviedb.org/) 웹사이트에서 회원가입 및 로그인  
2. **설정 > API** 페이지에서 API 키 발급  
3. 프로젝트 루트 디렉토리에 `.env` 파일 생성 후 아래와 같이 입력
   ```ini
   TMDB_API_KEY=당신의_API_키
   ```

### 2. 가상환경 생성 및 활성화
```
# 가상 환경 생성
python -m venv venv

# 가상 환경 활성화
# Windows
.\venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

### 3. 필요한 패키지 설치
```
pip install -r requirements.txt
```

### 4. 실행 방법
#### 🔹 Jupyter Notebook 실행

데이터 분석 코드를 단계별로 확인하려면 주피터 노트북을 실행하세요:
```
jupyter notebook
```

#### 🔹 Python 스크립트 실행

(선택) 분석을 자동화하거나 특정 기능만 실행하려면 src/ 폴더의 스크립트를 실행할 수 있습니다:
```
# 예시: 데이터 수집 실행
python src/collect_data.py

# 예시: 분석 실행
python src/analyze_movies.py
```

### 5. (선택) 한글 폰트 설정

시각화 시 한글 깨짐 문제가 발생하면 운영체제에 맞게 맑은고딕 폰트를 설치하세요.
```python
import matplotlib.pyplot as plt

plt.rcParams['font.family'] = 'Malgun Gothic'
plt.rcParams['axes.unicode_minus'] = False
```

## 📂 프로젝트 구조
```bash
movie_data_analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── .env (숨김 파일)
├── data/
│   ├── processed/
│   │   ├── merged_movie_data.csv (숨김 파일)
│   │   ├── tmdb_kr_theatrical_clean.csv (숨김 파일)
│   │   ├── tmdb_kr_theatrical_clean_exploded.csv (숨김 파일)
│   │   └── tmdb_with_credits_ko.csv (숨김 파일)
│   └── raw/
│       └── (수집된 원본 데이터)
├── notebooks/
│   ├── assignment_1.ipynb
│   ├── assignment_2.ipynb
│   ├── assignment_3.ipynb
│   ├── assignment_4.ipynb
│   └── collect_data.ipynb
├── src/
│   ├── collect_data.py
│   ├── analyze_movies.py
│   └── utils.py
└── venv/ (숨김 폴더)
```

---

## 📦 필요한 라이브러리

requirements.txt 예시:
```
pandas
requests
tqdm
python-dotenv
scikit-learn
numpy
matplotlib
seaborn
networkx
ipython
```

---

## 📊 데이터 설명

**데이터 출처**: TMDB API

**수집 기간**: 2005-01-01 ~ 2025-06-30

**수집 기준**: 한국 제작 + 한국 극장 개봉 영화

**주요 컬럼**:

- `movie_id`: 영화 고유 식별자

- `title`: 영화 제목

- `release_date`: 개봉일

- `genres`: 장르

- `runtime`: 상영 시간

- `budget`: 제작 예산

- `revenue`: 총 수익

- `vote_average`: 평점

- `popularity`: 인기도

- `director_id/name`: 감독 정보

- `cast_id/name`: 배우 정보

**데이터 크기**: 약 `87행` × `11열`

---

## 🔎 분석 목표

🎭 장르별 영화 트렌드 및 흥행 성공 요인 분석

⭐ 영화 평점과 흥행 수익 간의 상관관계 탐구

👥 배우·감독 네트워크 분석 및 성공 패턴 발견

🔑 영화 키워드 분석을 통한 흥행 예측

---

## 👥 팀원
🍅 **김도민** – 기본 데이터 수집 및 전처리, EDA 및 시각화, 모델링

🥔 **임수인** - 추가 데이터 수집 및 전처리, EDA 및 시각화, 모델링 및 보고서 작성
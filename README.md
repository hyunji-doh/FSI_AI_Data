# 유통기한 보장형 마이데이터 합성데이터 전환 시스템 PoC

마이데이터 규제에 따른 데이터 만료 문제를 합성데이터로 해결하는 시스템의 PoC(Proof of Concept) 구현입니다.

## 🚀 주요 기능

- **마이데이터 규제 시뮬레이션**: 6개월/1년 미접속 데이터 만료 처리
- **SDV CTGAN 합성데이터 생성**: 원본 데이터와 유사한 합성 데이터 생성
- **통계적 유사성 검증**: KS-test를 통한 원본-합성 데이터 비교
- **유통기한 관리**: SQLite를 활용한 데이터 유통기한 관리
- **만료 처리 시뮬레이션**: 시간 경과에 따른 데이터 접근 제어

## 📋 시연 시나리오

1. **원본 MyData 로드**: finance_card.csv 데이터 로드 및 규제 정책 안내
2. **데이터 만료 시뮬레이션**: 6개월/1년 규제 반영 및 삭제 데이터 수량 시각화
3. **합성데이터 전환**: SDV CTGAN으로 합성 데이터 생성
4. **원본 vs 합성 데이터 비교**: 월소득, 월지출, 카드사용률 분포 비교 및 KS-test
5. **합성데이터 유통기한 부여**: 1년 유통기한 설정 및 SQLite 저장
6. **만료 처리 시뮬레이션**: 현재/1년 후 데이터 접근 시뮬레이션

## 🛠️ 설치 및 실행

### 1. 의존성 설치
```bash
pip install -r requirements.txt
```

### 2. 애플리케이션 실행
```bash
streamlit run app.py
```

### 3. 브라우저에서 확인
- 자동으로 브라우저가 열리며 `http://localhost:8501`에서 확인 가능
- "🚀 전체 실행" 버튼을 클릭하여 전체 프로세스 실행

## 📁 프로젝트 구조

```
PoC_System/
├── app.py                 # 메인 Streamlit 애플리케이션
├── finance_card.csv       # 원본 데이터셋
├── requirements.txt       # 의존성 목록
├── README.md             # 프로젝트 설명서
└── output/               # 결과 파일 저장 폴더
    ├── synthetic_data.db # SQLite 데이터베이스
    └── system_log.txt    # 시스템 로그
```

## 📊 데이터 정보

- **원본 데이터**: finance_card.csv (9,965개 행, 15개 컬럼)
- **주요 컬럼**: 
  - `monthly_income`: 월소득
  - `monthly_card_spending`: 월 카드 지출
  - `card_benefit_usage_rate`: 카드 혜택 사용률
  - `age`, `gender`, `residence` 등 개인정보

## 🔧 기술 스택

- **Frontend**: Streamlit
- **Data Processing**: Pandas, NumPy
- **Synthetic Data**: SDV (Synthetic Data Vault)
- **Visualization**: Matplotlib
- **Database**: SQLite3
- **Statistical Analysis**: SciPy

## 📈 주요 결과

- **규제 준수**: 합성데이터는 마이데이터 규제 대상이 아님
- **통계적 유사성**: KS-test를 통한 원본-합성 데이터 유사성 검증
- **유통기한 관리**: 1년 유통기한 설정 및 자동 만료 처리
- **시각화**: 데이터 분포 비교 및 만료 현황 시각화

## ⚠️ 주의사항

- 이 시스템은 PoC(Proof of Concept) 목적으로 구현되었습니다
- 실제 운영 환경에서는 추가적인 보안 및 검증이 필요합니다
- 합성데이터의 품질은 원본 데이터의 특성에 따라 달라질 수 있습니다

## 📞 문의

프로젝트에 대한 문의사항이 있으시면 언제든지 연락주세요.

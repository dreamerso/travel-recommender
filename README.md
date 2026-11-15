### 주제 : 사용자 취향에 따라 국내 여행지, 일정 등을 짜주는 챗봇 형식의 서비스

## 내가 맡은 부분: 사용자 맞춤형 여행지 추천 모델
성별·연령대·인원수·여행 테마를 입력받아 17개 시·도 중 3곳을 추천합니다.<br>
관광 설문 데이터 36,569건으로 학습·검증했고, Random Forest가 Hit Rate@3 95.45%를 기록했습니다.

| 순서 | 파일 | 역할 |
|---|---|---|
| 1 | `model/Data_preprocessing.py` | 설문 데이터 전처리 → `data/region_recommend_data.csv` |
| 2 | `model/study_model.py` | 모델 비교 및 최종 모델 저장 → `data/region_recommender.pkl` |
| 3 | `model/Ruse.py` | 저장된 모델로 지역 3곳 추천 |
| 보조 | `model/code_book.py` | 입력 코드표 |

## 팀원 담당 부분 (참고)
- 예상경비 모델: `model/train_model.py`, `model/estimate_expense.py`
- 방문객 수 예측: `model/estimate_peak.py`
- 음식점·관광지, 날씨·숙소: `destination_info/`
- 교통편: `transport/`
- UI: `app/app.py`

## 실행
requirements.txt 파일에 사용했던 라이브러리들이 있습니다.<br>
가상환경 구축 이후에 다음의 명령어를 터미널에 입력해 라이브러리를 설치합니다.<br>
`pip install -r requirments.txt`<br><br>
추가적인 라이브러리를 설치했다면, 다음의 명령어를 통해 requirements.txt 업데이트해주세요.<br>
`pip freeze > requirments.txt`<br><br>
`.env`에 다음 환경 변수를 직접 넣어야 합니다. (값은 저장소에 포함되어 있지 않습니다.)<br>
`OPENAI_API_KEY`, `KAKAO_REST_API_KEY`, `PUBLIC_DATA_KEY`, `DATA_API_KEY`, `TOUR_API_KEY`, `HOLIDAY_KEY`

`.pkl` 파일은 직접 학습한 모델이며, 출처가 불분명한 pkl은 로드하지 마세요.

## 데이터 출처
- 외래관광객조사: 관광지식정보시스템
- 시군구 코드: 한국관광공사 OpenAPI

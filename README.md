# NBA 플레이오프 우승팀 예측

경기 단위 득점을 XGBoost로 예측하고 몬테카를로 시뮬레이션 1,000회로 시리즈를 확장해 2024-25 플레이오프 브래킷을 예측한 프로젝트.
**우승팀(OKC)·파이널 매치업·시리즈 스코어(4-3)까지 적중**

교내 전공 팀 프로젝트 · 4인 팀

**프로젝트 상세 → [Notion 포트폴리오](https://zany-meeting-aba.notion.site/76083f9aaedb823eb2888171cf3402f2)**
**발표 자료 → [Google Drive](https://drive.google.com/drive/folders/1PgM9VBqXpLkjN94LBYQhoM2fw5kekWwa)**

## 핵심 포인트
- 데이터: NBA API 경기 단위(Team × Game), 학습 2017~2024 · 검증 2024~2025
- 변수: 홈 이점, 시즌 진행률, 상대 득실 차, 최근 5경기 폼
- 모델 선정: 성능과 학습·검증 격차(과적합)를 함께 보고 XGBoost 선택

## 결과
| 모델 | RMSE | MAE | R² |
|---|---|---|---|
| RandomForest | 5.72 | 4.53 | 0.78 |
| **XGBoost (선정)** | 4.66 | 3.68 | 0.85 |
| LightGBM | 4.70 | 3.72 | 0.85 |
| CatBoost | 5.02 | 3.99 | 0.83 |

시뮬레이션 파이널 승리 확률 OKC 63.0% → 실제 OKC 4-3 IND 우승

## 파일 구성
| 파일 | 내용 |
|---|---|
| `01_경기별 dataset.ipynb` | 경기 단위 데이터 수집 |
| `02_8강팀 각 팀 지표 수집.ipynb` | 플레이오프 팀 지표 |
| `03_고급지표 분석.ipynb` | 고급 지표 분석 |
| `04_PER 분석.ipynb` | PER 분석 |
| `05_on off rating 지표.ipynb` | 온·오프 레이팅 |
| `06_홈경기 원정경기 승률.ipynb` | 홈·원정 승률 |
| `07_시각화 7번.ipynb` | 시각화 |
| `08_최근 10경기 주요선수 top3.ipynb` | 최근 폼 분석 |
| `09_최종 모델.ipynb` | 모델 비교 · 튜닝 · 몬테카를로 시뮬레이션 |

## 기술 스택
`Python` `scikit-learn` `XGBoost` `LightGBM` `CatBoost` `nba_api`

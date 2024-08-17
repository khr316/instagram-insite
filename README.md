# 인스타그램 인사이트 분석 : <br> 최적의 게시물 업로드 전략 도출

## 1. 프로젝트 개요

**프로젝트 목표:**  
인스타그램 게시물의 좋아요 수와 도달 수를 분석하여, 어떤 요일과 시간대에 게시물을 업로드하면 가장 높은 성과를 얻을 수 있는지를 파악

**팀원:** 김신희, 김혜림  
**사용도구:** Python (Selenium, pandas, matplotlib, seaborn)  
**협업 도구:** Google Drive

## 2. 데이터 수집

**데이터 출처:** 인스타그램 (개인 계정: "[@k.march.hr](https://www.instagram.com/k.march.hr/)" )

**수집 방법:**
- **웹 크롤링:** Selenium을 사용하여 게시물의 업로드 날짜와 시간을 수집 => 인스타그램의 경고로 인해 크롤링 제한
- **직접 수집:** 좋아요 수와 도달 수는 수동으로 수집하여 엑셀 파일로 저장

**수집된 파일:**
- `instagram_likes.xlsx` (좋아요 수)
- `instagram_dates.xlsx` (업로드 날짜와 시간)
- `instagram_reach.xlsx` (도달 수)

## 3. 데이터 전처리

1. **데이터 불러오기:** 엑셀 파일에서 데이터를 불러와 하나의 데이터프레임으로 병합
2. **데이터 전처리:**
   - 날짜 및 시간을 분리하여 각각의 열로 저장
   - 결측값 처리: 도달 수의 결측값은 평균값으로 대체
   - 요일 열 추가: 날짜에 해당하는 요일을 한글로 변환하여 추가
   - 시간대 수정: 데이터의 시간대는 한국 시간 (UTC+9)으로 조정 (원본 데이터 - 그리니치 평균시(UTC) 기준)

## 4. 데이터 분석

1. **요일별 분석:**  
   - 요일별로 평균 좋아요 수와 도달 수를 계산하고 시각화

2. **시간대별 분석:**  
   - 시간대별로 좋아요 수와 도달 수를 분석하고 시각화

3. **요일 및 시간대별 분석:**  
   - 히트맵을 사용하여 요일과 시간대별로 평균 좋아요 수와 도달 수를 시각화

## 5. 분석 결과

- **요일별 분석:**  
  - 좋아요 수는 일요일에 가장 높았으며, 도달 수는 월요일, 금요일, 토요일에 가장 높음

- **시간대별 분석:**  
  - 좋아요 수는 아침 6시에서 9시와 저녁 9시에서 새벽 3시에 가장 높았으며, 도달 수는 저녁 9시에서 새벽 3시에 가장 높음

- **최적의 게시 시점:**  
  - 금요일에서 토요일 넘어가는 12시에서 새벽 3시가 가장 높은 성과를 보였으며, 이는 토요일 새벽에 게시물을 업로드할 때 성과가 가장 좋다는 것을 의미

## 6. 결론

이 분석을 통해 인스타그램 게시물의 최적 업로드 시점을 파악할 수 있었으며, 
이를 통해 추가 비용 없이 게시물의 성과를 극대화할 수 있는 전략을 도출
인스타그램 활동을 보다 효과적으로 관리하고, 더 나은 결과를 얻기 위한 전략을 세우는 데 도움이 될 것

## 7. 피드백

분석 후 피드백, 개선해야 할 사항:

1. **게시물 사진의 유형에 따른 영향:**
   - 게시물의 사진이 어떤 유형인지(예: 인물 사진, 풍경, 제품 사진 등)에 따라 좋아요 수와 도달 수가 달라질 수 있습니다.<br>
   - 따라서, 분석 시 사진의 콘텐츠 유형을 분류하고, 유형별로 성과를 비교하는 작업 필요.

2. **좋아요 수의 수집 기준과 시점:**
   - 좋아요 수를 수집한 날짜와 시간에 대한 기준을 명확히 해야 합니다. 특히, 예전에 올린 게시물에 좋아요가 다시 달릴 경우 이를 어떻게 처리할지에 대한 계획이 필요합니다. <br>
   - 누적된 좋아요 수를 주기적으로 기록하고, 시간 경과에 따른 변화 추이를 분석하는 것이 중요. <br><br>
   - 게시물의 좋아요 수를 언제 수집해야 정확한 분석이 가능한지에 대한 논의가 필요합니다. <br>
   - 월요일에 올린 게시물과 토요일에 올린 게시물의 경우, 동일한 시간 간격 후에 좋아요 수를 수집하여 비교 분석하는 방법이 제안되었습니다. <br>
   - 예를 들어, 모든 게시물에 대해 게시 후 24시간, 48시간, 72시간 등의 일정한 시점에 좋아요 수를 수집하는 방식이 필요합니다.

4. **팔로워의 연령대, 성별 및 비팔로워의 참여 고려:**
   - 팔로워의 연령대와 성별, 그리고 팔로워가 아닌 사용자들로부터의 좋아요 유입을 고려해야 합니다. <br>
   - 이러한 요소들이 좋아요 수와 도달 수에 영향을 미칠 수 있으므로, 데이터 분석 시 이들 인구통계학적 요소를 포함하는 것이 중요합니다.


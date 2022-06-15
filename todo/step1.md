# 🚀 1단계 - 웹 성능 테스트
## 요구사항
- 웹 성능 테스트
  - 웹 성능 예산을 작성
  - [WebPageTest](https://www.webpagetest.org/), [PageSpeed](https://pagespeed.web.dev/?utm_source=psi&utm_medium=redirect) 등 테스트해보고 개선이 필요한 부분을 파악

## 요구사항 설명
- 저장소를 활용하여 아래 요구사항을 해결합니다.
- README 에 있는 질문에 답을 추가한 후 PR을 보내고 리뷰요청을 합니다.

## 힌트
### 경쟁사 관련 자료
- 아래 자료를 참고하여 웹 성능 예산, 부하테스트 목푯값 등을 설계해보세요.
**경쟁사**
- [서울교통공사](http://www.seoulmetro.co.kr/kr/cyberStation.do) 
- [네이버지도](https://m.map.naver.com/subway/subwayLine.naver?region=1000) 
- [카카오맵](https://m.map.kakao.com/)
**언론보도**
- [데이터로보는 서울시 대중교통 이용](https://www.bigdata-map.kr/datastory/traffic/seoul)
- [카카오 모바일 APP 현황](https://ko.lab.appa.pe/2016-09/kakao-korea.html)
- [길찾기만 하루 1억건](https://news.mt.co.kr/mtview.php?no=2021090916014079809)
- [네이버 지도 MAU](https://blog.naver.com/rkwkrhspm/222515422896)

### 용어 정리
- [FCP(First Contentful Paint)](https://web.dev/first-contentful-paint/?utm_source=lighthouse&utm_medium=lr): 콘텐츠가 포함된 첫 페인트는 첫 번째 텍스트 또는 이미지가 표시되는 시간
- [TTI(Time To Interactive)](https://web.dev/interactive/?utm_source=lighthouse&utm_medium=lr): 사용할 수 있을 때까지 걸리는 시간은 완전히 페이지와 상호작용할 수 있게 될 때까지 걸리는 시간
- [SI(Speed Index)](https://web.dev/speed-index/?utm_source=lighthouse&utm_medium=lr): 속도 색인은 페이지 콘텐츠가 얼마나 빨리 표시되는 시간
- [TBT(Total Blocking Time)](https://web.dev/lighthouse-total-blocking-time/?utm_source=lighthouse&utm_medium=lr): FCP와 상호작용 시간 사이의 모든 시간의 합
- [LCP(Largest Contentful Paint)](https://web.dev/lighthouse-largest-contentful-paint/?utm_source=lighthouse&utm_medium=lr): 콘텐츠가 포함된 최대 페인트는 최대 텍스트 또는 이미지가 표시되는 시간
- [CLS(Cumulative Layout Shift)](https://web.dev/cls/?utm_source=lighthouse&utm_medium=lr): 누적 레이아웃 변경은 표시 영역 안에 보이는 요소의 이동을 측정

### 웹 성능 예산 작성
- https://subway.mond.page

|  | 모바일 | 데스크톱 |
| --- | --- | --- |
| 성능 점수 | 🔴32 | 🔴67 |
| FCP | 🔴14.5s | 🔴2.7s |
| TTI | 🔴15.2s | 🟠2.8s |
| SI | 🔴14.5s | 🔴2.7s |
| TBT | 🟠560ms | 🟢50ms |
| LCP | 🔴15.1s | 🔴2.8s |
| CLS | 🟢0.042 | 🟢0.004 |

- 서울교통공사

|  | 모바일 | 데스크톱 |
| --- | --- | --- |
| 성능 점수 | 🔴43 | 🟠70 |
| FCP | 🔴7.0s | 🟠1.6s |
| TTI | 🔴8.6s | 🟢2.0s |
| SI | 🔴8.2s | 🟠2.3s |
| TBT | 🟠340ms | 🟢60ms |
| LCP | 🔴8.7s | 🔴3.5s |
| CLS | 🟢0 | 🟢0.014 |

- 네이버지도

|  | 모바일 | 데스크톱 |
| --- | --- | --- |
| 성능 점수 | 🟠58 | 🔴45 |
| FCP | 🟠2.1s | 🟢0.4s |
| TTI | 🟠6.7s | 🔴5.6s |
| SI | 🟠4.8s | 🔴4.2s |
| TBT | 🟠370ms | 🔴890ms |
| LCP | 🔴7.6s | 🔴2.5s |
| CLS | 🟢0.03 | 🟢0.014 |

- 카카오맵

|  | 모바일 | 데스크톱 |
| --- | --- | --- |
| 성능 점수 | 🟠67 | 🟠68 |
| FCP | 🟢1.7s | 🟢0.6s |
| TTI | 🟠4.6s | 🟠2.5s |
| SI | 🔴6.9s | 🔴2.4s |
| TBT | 🟢120ms | 🟢100ms |
| LCP | 🔴6.4s | 🔴4.7s |
| CLS | 🟢0.005 | 🟢0.005 |

### 개선이 필요한 부분을 파악
- FCP를 경쟁사와 20% 차이가 넘지 않도록(평균 0.86s) 개선이 필요 
  - **FCP : 1.04s 목표**
- TTI 2.0s로 개선이 필요

- vendor.js, main.js 리소스 압축
- js, image 캐싱 처리

### 📚 Todo List 📚
- [x] 용어 정리
- [x] 웹 성능 예산을 작성
- [x] 개선이 필요한 부분을 파악

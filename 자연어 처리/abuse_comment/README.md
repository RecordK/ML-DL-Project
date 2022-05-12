# Abuse_Comment
<aside>
🪁 Tensorflow와  Keras를 사용하여 고급 순환 신경망 분석인 lstm기법을 사용하여 욕설을 탐지하는 모델을 개발하였고 그 기능을 간단하게 웹 서비스로 구현하였습니다.

</aside>

## 1. 크롤링

---

### **사이트 선정**



- 우리나라 커뮤니티 사이트 중 가장 큰 커뮤니티 사이트인 dcinside 선정하였습니다.

- Selenium과 BeautifulSoup4를 활용하여 hot 갤러리 실시간 베스트 갤러리의 댓글을 7천개씩 총 1만 4천 개의 댓글을 크롤링하였습니다.

- **코드**
    
    [dcinside_댓글.ipynb](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/92a53a40-b3d2-43bd-a49d-b5a01f1a8ea9/dcinside_댓글.ipynb)
    

## 2. 라벨링

---

### **데이터 라벨링**



- 인기 게시물의 댓글을 크롤링하여서 욕설인 것과 아닌 것을 라벨링하였습니다.

## 3. 전처리

---



데이터에 포함되어 있는 특수문자를 re 라이브러리로 제거하고 불필요한 조사를 제거한 뒤 **KONLPY** 라이브러리를 활용하여 의미가 있는 단어로 나누었습니다.



**TensorFlow**를 활용하여 단어를 토큰화 처리 하였습니다.

## 4. MODEL SELECTION

---

- 기존의 순환 신경망 분석(RNN)을 개선한 LSTM으로 두개의 층과 Dense층으로 쌓았고 활성화 함수는 sigmoid를 사용하였습니다.

- **참고 문헌**
    
    오영택, 김민태, and 김우주. "Parallel Stacked Bidirectional LSTM 모델을 이용한 한국어 영화리뷰 감성 분석." *정보과학회논문지*
     46.1 (2019): 45-49.
    
- **전처리 및 모델링 코드**
    
    [딥러닝_욕설_필터링_순서정렬-2.ipynb](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7fe859c3-2ca1-4d09-bbd9-a40a1860a794/딥러닝_욕설_필터링_순서정렬-2.ipynb)
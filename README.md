# VQA
2021 AI 경진대회 '시각장애인을 위한 VQA 모델 개발' 과제

## Description
VQA(Visual Question Answering)모델은 이미지와 질문 텍스트를 입력으로 받아 답변 텍스트를 출력하는 모델
### 예시)
- 입력 : 책상이 찍힌 사진 + '책상위에는 책은 무슨 색입니까?'
- 출력 : "빨간색"

## Description of Data
- Train set
  - 224,464 개의 이미지 파일 (14GB)
  - 702,135 건의 질문-답변 쌍 (81MB)
- Test set
  - 15,121 개의 이미지 파일 (870MB)
  - 22,231 건의 질문 (2.5MB)   

## Environment
- Google Colab Pro

## Libraries
- KoBERT-Transformers : https://github.com/SKTBrain/KoBERT
- sentencepiece : https://github.com/google/sentencepiece
- customized_konlpy : https://github.com/lovit/customized_konlpy

## About Model
* 질문 텍스트 처리에 Transformer encoder layer + Position Embedding 적용
* 이미지 처리에는 VGGNET-16의 CNN 구조 일부 변경하여 사용
* Train set의 input 크기가 커서 한번에 올릴 수가 없었음
  * data_generator 을 활용해 필요할 때마다 읽어오는 방식으로 구현
* 각각의 처리를 거친 이미지-질문 쌍에 추가로 어텐션 메커니즘 적용

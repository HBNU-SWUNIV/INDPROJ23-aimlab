# 한밭대학교 SW중심대학 산학연계프로젝트 - 생성 모델 워터마킹 연구

## **팀 구성**
### 지도교수
 - 장한얼 교수님

### 기업체 
 - 박주한 대표

### 참여학생
 - 30211054 이인수 (석사과정)
 - 20191785 이지상 (학사과정)
 - 20191766 김동수 (학사과정)
 - 20211915 오서연 (학사과정)
 - 20191747 이지준 (학사과정)
 - 20191120 이용빈 (학사과정)
 - 20191780 육정훈 (학사과정)

## Project Background
- ### 필요성
  - 생성 모델이 만든 콘텐츠 저작권 및 구매자 정보를 확인하기 위해 생성 모델 워터마킹 기술을 연구하여 창작자의 정보를 비가시적으로 삽입 및 추출함.
- ### 기존 해결책의 문제점
  - 기존 워터마킹 기술은 생성 모델에 최적화되지 않음.
  - 온라인 유통 시에 발생하는 왜곡에 대해서 강인한 워터마킹 기술 필요.
  
## System Design
  - ### System Requirements
    - 생성 모델 워터마킹 연구 및 성능 평가.
    
## Case Study
  - ### Description
    - 본 과제에서는 생성 모델 zero-bit 워터마킹 연구를 수행하였음.
    - Zero-bit 워터마킹이란 워터마크 존재 시 1, 없으면 0으로 출력하는 이진 분류 과업임.
    - 생성 모델 zero-bit 워터마킹은 생성 모델이 생성한 이미지이면 1, 아니면 0으로 출력하는 과업임. 즉, 생성 이미지 판별 문제로 정의할 수 있음.
    - 온라인 상에서 빈번하게 발생하는 이미지 크기 변환과 절삭에 대해서 강인한 생성 이미지 판별 연구를 수행하였음.
  - ### Method
    - 1) 아래 그림과 같이 이미지 크기 변환과 절삭을 이용하여 데이터 증대를 수행함.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/986817d6-96a8-447a-899d-81a28727582d)
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/87e56c53-0c07-47ef-b11a-f06adf20eaf9)
    - 2) 생성 이미지에서 발생하는 고주파 대역의 비정상적인 특징을 효과적으로 탐지하기 위해 고속 푸리에 변환(FFT)과 이산 코사인 변환(DCT)를 사용하여 데이터 전처리를 수행함.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/52020172-dc4a-43d7-b98c-3ae73150afc7)
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/662ffa4c-cfce-427f-918b-4cb529e5633f)
    - 3) 데이터 증대한 이미지와 주파수 변환한 이미지를 입력값으로 사용하는 생성 이미지 zero-bit 워터마킹 모델(EfficientNet-B0)을 학습함.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/f77211c4-5994-4a5b-b1cc-712b7caedb6a)
  - ### Experimental Results
    - 1) 아래 표는 이미지 크기 변환과 절삭을 이용하여 데이터 증대를 수행한 실험결과임.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/40494d15-7eef-424e-aa6a-b121656b8f19)
    - 2) 아래 표는 고속 푸리에 변환(FFT) 사용 유무에 따른 zero-bit 워터마킹 실험결과임.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/8708a3c4-98d8-4af3-991a-a0977020f3e0)
    - 3) 아래 표는 이산 코사인 변환(DCT) 사용 유무에 따른 zero-bit 워터마킹 실험결과임.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/1f1cc623-9936-456b-836a-fcb0a4056953)
    - 4) 아래 그림은 일반 이미지(왼쪽)와 생성 이미지(오른쪽)의 고속 푸리에 변환(FFT) 비교 결과임.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/d7fe7359-d16d-4fb9-a560-c2cb7396c152)
    - 5) 아래 그림은 일반 이미지(왼쪽)와 생성 이미지(오른쪽)의 이산 코사인 변환(DCT) 비교 결과임.
      - ![image](https://github.com/HBNU-SWUNIV/INDPROJ23-aimlab/assets/14088046/2de15204-4dff-4ed8-88e5-1bab1b339043)
  
## Conclusion
  - 고속 푸리에 변환과 이산 코사인 변환 실험 결과로 주파수 영역에서의 변환을 통해 생성 이미지의 패턴과 특성을 더 잘 감지하고 이를 기반으로 생성 이미지 zero-bit 워터마킹을 수행할 수 있음을 확인하였음.
  
## Project Outcome
- ### 2023년 한국디지털포렌식학회 동계학술대회 발표
- ### 2023년 한국디지털포렌식학회 동계학술대회 학회장상 수상

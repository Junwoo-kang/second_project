## 📣 중앙인재 개발원 2차  기업 프로젝트 (선도소프트) -수자원 종합플렛폼

# 📖 프로젝트 개요
![시스템 프로세스](readme_image/main.PNG)
##  프로젝트 소개 
![시스템 프로세스](readme_image/a.PNG)  

<a href="https://drive.google.com/file/d/1KNCtEVMjgb-_PK2dbBusQsx2LOx4h4aN/view?usp=drive_link">📌 프로젝트 전체 PPT 보기</a>📌 

## 📚 개발환경

- <img src="https://img.shields.io/badge/Framework-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"><img src="https://img.shields.io/badge/2.7.0-515151?style=for-the-badge"><img src="readme_image/egovframe.PNG" width="100px" height="27px"><img src="https://img.shields.io/badge/4.1-515151?style=for-the-badge">
- <img src="https://img.shields.io/badge/Build-%23121011?style=for-the-badge">![Apache Maven](https://img.shields.io/badge/Apache%20Maven-C71A36?style=for-the-badge&logo=Apache%20Maven&logoColor=white)<img src="https://img.shields.io/badge/4.0-515151?style=for-the-badge">
- <img src="https://img.shields.io/badge/Language-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/java-%23ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"><img src="https://img.shields.io/badge/11-515151?style=for-the-badge">
- <img src="https://img.shields.io/badge/DATABASE-%23121011?style=for-the-badge">![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ➕ <img src="readme_image/postgis.PNG" width="100px" height="27px">
- <img src="https://img.shields.io/badge/front-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white"><img src="https://img.shields.io/badge/css-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white"><img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E"><img src="https://img.shields.io/badge/jquery-%230769AD.svg?style=for-the-badge&logo=jquery&logoColor=white"><img src="https://img.shields.io/badge/bootstrap-%238511FA.svg?style=for-the-badge&logo=bootstrap&logoColor=white">

- <img src="https://img.shields.io/badge/Library-%23121011?style=for-the-badge"><img src="readme_image/openlayers.PNG" width="100px" height="27px">
- <img src="https://img.shields.io/badge/software-%23121011?style=for-the-badge"><img src="readme_image/geoserver.PNG" width="100px" height="27px">



## 시스템 구성도

<img src="readme_image/sw.PNG" width="400px"><img src="readme_image/gis.PNG" width="400px" >

##  프로젝트 기간
 🕛2023.12.4 - 2024.1.3




## 프로젝트 구조
![시스템 프로세스](readme_image/systemprocess.PNG)


## 프로젝트 팀원 및 역할
👑🧑 조장 이광현 (LKH) : 프로젝트 총괄/일정관리 , 실시간 수문 정보관리시스템(1.지도구현, 
2.수자원 시설물 관리 게시판)

🧑부조장 강준우 (KJO) : 전자정부프레임워크 환경설정 , 수자원 시설물 관리시스템(1.점검 결과 작성, 2.점검이력조회)

👩팀원 이진희 (LJH) : 수자원 시설물 관리시스템(1.고장/조치 결과보고, 2.점검 이력 통계)


👩팀원 황인정 (HIJ) : 실시간 수문 정보 관리시스템(1. 관측소 관리 게시판, 2.관측소 정보통계)


👩 팀원 조미혜 (JMH) : 관리자 시스템(1.사용자관리,2.운영관리, 3.시스템관리)

## 🔭 나의 구현 기능

## 🔥 실시간 수문 정보 관리시스템-지도  🔥  

:question: Geoserver를 이용하여 웹화면에 지도를 그리는 과정

![mappro1](readme_image/mappro1.PNG)
1. 먼저 제공받은 기업에서 제공받은 shp파일을 QGis로 읽어 지도를 불러옵니다.  
여기서 QGis 오픈 소스 기반의 지리정보시스템 소프트웨어입니다. 이 소프트웨어는 사용자가 지리 공간 데이터를 불러오고 편집, 시각화하고 분석하는데 사용합니다.  
2. 이 qgis로 불러온 shp파일을 PostSQL와 연동시켜 데이터베이스안에 이 지리공간 데이터를 저장합니다. 참고로 PostSQL은 이러한 공간적 데이터베이스에 대해 특화되어있습니다.

![mappro2](readme_image/mappro2.PNG)
3. 그 다음 지리정보가 들어있는 데이터베이스와 GeoServer를 연동시켜서 해당 지리정보의 레이어를 생성합니다.   
4. 그 후에 GeoServer에서 제공되는 기능으로 지도 데이터를 가져와 openlayers로 레이어를 그립니다. 
Openlayers는 javascript 기반의 오픈 소스 라이브러리로 웹 상에서 지도와 지리정보를 표시하고 상호 작용하는데 사용됩니다.
<img src="readme_image/layers1.PNG" width="500px" height="300px">


### 🔥 지역별 Polygon, point형식의 레이어 생성 및 쌓기 🔥  
![layers2](readme_image/layers2.PNG)
체크박스의 체크여부에 따라 해당 레이어가 표시 여부가 결정됩니다.


### 🔥 관측소 클릭 시 해당 좌표로 이동 및 관측소 정보 팝업 표시 🔥 
![layers2](readme_image/layers3.PNG)

관측소 리스트에 잇는 관측소를 클릭하면 해당 좌표로 이동 후 해당 관측소에 정보가 표출됩니다.


## 🔥 시설물 관리 시스템]-게시판 🔥  

### 🔥 상세화면, 등록 ,수정, 삭제 🔥  
![list2](readme_image/list1.PNG)
![list2](readme_image/list2.PNG)




 
 

---
## 📌 프로젝트 회고 
자체 프로젝트를 진행하며 느꼈던 상호 진행상태에 대한 확인이 어려웠던 문제점을 기업 프로젝트를 진행하며 산출물을 작성하는 것으로 해결할 수 있었고, 산출물 기반으로 유지보수를 하는 것이 중요하다는 것을 느꼈습니다.

프로젝트의 성공은 리더와 팀원들 간의 원활한 협력과 시너지에 의해 결정되기 때문에, 부조장으로서 신중한 의사결정과 명확한 의사소통이 중요했습니다. 이러한 경험을 통해 리더십 역할을 더 깊이 이해하고 향상된 의사소통 역량을 갖추게 되었습니다.

프로젝트를 진행하며 아쉬웠던 점은 다양한 데이터들(수량,강수량,수자원시설물)과 환면설계서를 이해하고 산출물 및 개발을 하는 것에 대한 시간이 부족하였습니다. 많은 시간이 있었다면 더 완성도 있는 프로젝트가 됐을거라고 생각합니다.

이번 프로젝트를 통해개발을 하기 위해선 개발능력이 중요하겠지만 하나의 프로젝트에 참여하기 위해선 요구사항과 데이터들의 이해도 중요하다는 것을 알게되었습니다. 개발자로서 단순 개발 능력이 아닌 요구사항 분석의 능력도 중요하다는 것을 알게되었습니다.




## 1.소개

![1_peeps_intro](https://user-images.githubusercontent.com/71624723/110078703-7b930d80-7dcb-11eb-98ab-476979fb197d.png)

## 2.구조 
 * MSA아키텍처  RESRFUL
  ![제목 없는 프레젠테이션 (1)](https://user-images.githubusercontent.com/71998081/110272493-aff60c00-800d-11eb-872f-57b80cd722d8.jpg)

 

      
## 3.개발환경
  
  * 웹 표준 및 프론트앤드 
   
    *  HTML 5
    *  CSS3
    * JavaScript
    * jQuery
    * JSON
    * JSP
    * Bootstrap
    
  * 백앤드
    * Spring FrameWork
    * Java
    *  JSP, EL
    *  EC2
    *  S3
    *  mybatis
    *  junit
  
  * WAS
    * Appache Tomcat
  
  * DBMS
    * mysql
    
  * 구현도구
    * Eclipse 
    * SPRING TOOL SUITE 
    * Maven
    * github
    * putty
    * exerd
  
  * API
    * KAKAO LOGIN API
    * KAKAO MAP API
    * GOOGLE LOGIN API 
    * 공공데이터포털 동네 날씨 예보 API
   
  * AWS배포: 
    
    * EC2
    * RDS
    * S3 
    * FileZila를 이용한 FTP 업로드
    * Putty를 이용한 SSH 접속

  ## 4. 주요기능
  ### - 회원
  + 회원가입
  ![image](https://user-images.githubusercontent.com/71998081/112373759-a9150c00-8d24-11eb-8f21-ddecab093cc4.png)

  
  ### - 타임라인
  ![image](https://user-images.githubusercontent.com/71998081/112374299-453f1300-8d25-11eb-9a2b-23f296ec0cd9.png)


  ### - 마이페이지
  
  + 게시글 작성
  ![image](https://user-images.githubusercontent.com/71998081/112374388-63a50e80-8d25-11eb-9219-a0253d92233d.png)

  + 게시글 리스트 
  ![image](https://user-images.githubusercontent.com/71998081/112374494-846d6400-8d25-11eb-9bf6-a1ed9e9b8398.png)

  
  + 게시글 지도
  ![image](https://user-images.githubusercontent.com/71998081/112374543-94854380-8d25-11eb-8eab-9076e48d9162.png)

  + 방명록 
  ![image](https://user-images.githubusercontent.com/71998081/112374640-b2eb3f00-8d25-11eb-8aa1-1e66d7b29229.png)



  ### - 채팅
  + WebSocket을 이용한 1:1 채팅
  ![image](https://user-images.githubusercontent.com/71998081/112374748-d0b8a400-8d25-11eb-95c4-cbfd22a356bb.png)

  ![리드미용_서아-017](https://user-images.githubusercontent.com/71997900/110497018-6c98bc00-8139-11eb-9f1b-38b4aa57751e.png)
  + 회원 검색
  ![리드미용_서아-018](https://user-images.githubusercontent.com/71997900/110496119-85ed3880-8138-11eb-9f2b-5078a0703ca1.png)
  + 날씨 API
  ![리드미용_서아-019](https://user-images.githubusercontent.com/71997900/110496180-956c8180-8138-11eb-84d7-79d12a67c18b.png)
  + 메세지 전송
  ![리드미용_서아-020](https://user-images.githubusercontent.com/71997900/110496283-ac12d880-8138-11eb-9422-84d3d8082ca2.png)
 
  ### - 알람
  + Alarm
  ![리드미용_서아-021](https://user-images.githubusercontent.com/71997900/110496431-cea4f180-8138-11eb-84b6-ca255465c054.png)
  + 실시간 알람
  ![리드미용_서아-022](https://user-images.githubusercontent.com/71997900/110496482-dbc1e080-8138-11eb-8716-af5253c1fd98.png)
  + 알람 아이콘
  ![리드미용_서아-023](https://user-images.githubusercontent.com/71997900/110496515-e54b4880-8138-11eb-894f-868253107401.png)



## 5. 배포주소
[PEEPS 홈페이지🐥](http://52.79.227.12:8080/peeps/)

[시연영상🎬](https://youtu.be/gkNfDAoEMOA)

## 6. 어려웠던점과 해결방법
  
  * 채팅 배포
        로컬 호스트에서는 잘 돌아가는 채팅 프로젝트가 클라이언트에 연결하자 크로스 오리진이 발생하였다. 따라서 클라이언트와 채팅을 합치기로 하였는데, 합친 후 크로스 오리진은 발생하지 않았지	         만 핸드셰이크 500 에러가 발생하였다.
	확인 해 본 결과 소켓 자체는 열렸는데 서버에서 소켓을 업그레이드 하는 과정에서 오류가 생긴 것 같았다. 로컬호스트의 톰캣의 경우 8.5버전을 사용하였는데 ec2 터미널의 톰캣 서버를 확인해보	   니 7.6 버전이었다. 따라서 ec2의 톰캣 또한 8.5버전으로 업그레이드 하였고 채팅 배포를 성공할 수 있었다.
	
 * REST API
      프로젝트 초반에  모든 데이터들을 controller에서 model으로 전달해 줬었다. 그러나 우리는 서버와 클라이언트 통신을 위해 rest인터페이스를 구현하는 방식으로 개발을 해야했다. 
      그래서 동기통신에서 비동기통신으로 바꿔야 했고 그 과정에서 많은 공부와 프로젝트의 이해가 필요했다.  모든 기능을  ajax로 바꾸고 json으로 파싱해주었고, MSA방식의 구조를 이해하고 순조롭게       프로젝트를 이어갈 수 있었다
 

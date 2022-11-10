# Travled
> Android Studio | Java / Firebase | Google Login

일학습병행제 Off-JT 프로젝트

<img width="1440" alt="Travled" src="https://user-images.githubusercontent.com/59905688/201168144-659786dc-a576-42fa-aa9f-c25a6c2fc55c.png">

## 프로젝트 소개

영단어 학습을 돕는 퀴즈형 Game Application

- 사용 기술 및 라이브러리
    + Java, Android
    + FireBase
    + Google Login    
    
- 참여자 : 김현준(Developer) holden.developer@gmail.com, 최수현(Developer) shChoie@gmail.com (총 2인) 

- 진행 기간 : 2021.03.12 - 2022.06.10 (총 4주) 

<br/>

## 구현 기능

- 포토북 생성
  + 포토북을 생성하기 위해서 필수적으로 입력되어야 하는 정보에는 포토북 명, 여행 일자, 멤버, 지역, 도시가 있습니다.
  + 이러한 정보를 바탕으로 각각의 포토북을 구별 및 분류하게 된다. 기본정보를 입력한 뒤에는 제공되는 8장의 표지 중 한 장을 선택합니다.
  + 페이지 추가 버튼을 통해 갤러리와 연동하여 원하는 사진 혹은 동영상을 선택합니다.
  + 이때 각각의 미디어 정보에 텍스트를 입력하여 더욱 많은 정보를 저장할 수 있습니다.
  + 텍스트를 입력하지 않은 페이지에는 ‘글 작성 x’라는 라벨이 보이게 됩니다.
    
- 지도형 UI를 통한 포토북 검색
  + 생성된 포토북은 사전에 입력한 지역/도시 정보를 바탕으로 Home Layout에서 분류되어 보여진다.
  + 지역은 경기/수원, 인천, 부산, 대전, 대구, 광주 총 6곳으로 지역 버튼을 클릭하고 특정 구역을 선택하면 지역별로 실제 지도를 바탕으로 구성된 버튼 UI가 보여지게 됩니다.
 <img width="1440" alt="Map" src="https://user-images.githubusercontent.com/59905688/201169550-b3e8181d-c11f-42aa-8375-87109ac04bd6.png" width="20%" height="20%">
  + 지역과 특정 도시를 선택하게 되면 조건에 부합하는 포토북 리스트를 Firebase에서 불러오게 됩니다.
  + 사용자는 선택한 표지와 포토북 명, 멤버 등의 정보를 통해 원하는 포토북을 찾아 정보를 열람합니다.
  + 포토북 내의 정보(사진, 영상, 텍스트)들은 그리드 뷰를 통해 보여지며 각각 하단에 라벨을 붙여 유사한 사진과 영상이 구분되도록 하였습니다.
  + 사진, 영상을 선택하면 함께 입력한 텍스트가 함께 보여지고 영상의 경우 소리 또한 함께 재생됩니다.
    
- 커뮤니티
  + 사용자는 커뮤니티 탭에서 하단의 글 작성 버튼을 눌러 게시글을 작성할 수 있습니다.
  + 게시글은 사진(1장), 작성일, 본문으로 구성됩니다.
  + 사용자가 모든 정보를 입력한 뒤 저장 버튼을 누르면 Firebase에 정보가 업로드되어 게시글 리스트에 실시간으로 추가됩니다.
  +  게시글은 사용자가 등록한 사진을 배경으로 하여 글 제목과 생성일이 함께 보이는 형태로 구현했습니다.
    
- FireBase
  + 저장되는 데이터는 크게 텍스트 정보와 이미지 정보로 나누어집니다.
  + 텍스트 정보는 Firestore에 저장되며, 이미지 정보는 Storage에 저장됩니다.
  + 각각의 테이블의 루트 경로는 어플리케이션에 로그인 시 연결한 구글 이메일 주소가 됩니다.
  + 커뮤니티에 등록한 글은 ‘community’라는 이름의 경로 아래에 저장되며. 이미지와 텍스트가 별도로 저장되기 때문에 정보를 불러올때 엇갈리거나 섞이지 않도록 스레드를 제어하는 방식으로 구현했습니다.
  <img width="1440" alt="FireStore" src="https://user-images.githubusercontent.com/59905688/201170880-22d129da-bf8d-403b-b815-4a435a0f8fbe.png" width="40%" height="40%">
  <img width="1440" alt="Storage" src="https://user-images.githubusercontent.com/59905688/201170907-f19d64cc-2f29-40fd-9913-c088cac3bbbd.png" width="40%" height="40%">
  
## 담당 파트
- HomeTap UI
- HomeTap ListView Adapter
- HomeTap ListView Item
- BookTap GridView Adapter
- CommunityTap UI
- CommunityTap RecyclerView Adapter
- CommunityTap RecyclerView Holder
- CommunityTap RecyclerView Decoration
- CommunityTap RecyclerView Item


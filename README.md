# 영화 추천 알고리즘 기반 커뮤니티 서비스

### MOVIETRAP



### 프로젝트 기간 📅

- 2023.05.17(수) ~ 2023.05.26(금)

### 기술 스택 🛠

- Front-end: Django template, Vanilla Javascript
- Back-end: Django

### 설치 가이드 💻

```
$ pip install -r requirements.txt

$ python manage.py migrate
$ python manage.py loaddata genres.json movies.json
$ python manage.py runserver
```

---

## INDEX 📌

1. [팀원 정보 및 업무 분담 내역](#1-팀원-정보-및-업무-분담-내역)
2. [목표 서비스 구현 및 실제 구현 정도](#2-목표-서비스-구현-및-실제-구현-정도)
3. [데이터베이스 모델링 (ERD)](#3-데이터베이스-모델링-erd)
4. [영화 추천 알고리즘에 대한 기술적 설명](#4-영화-추천-알고리즘에-대한-기술적-설명)
5. [서비스 대표 기능에 대한 설명](#5-서비스-대표-기능에-대한-설명)
6. [기타 (느낀 점, 후기 등)](#6-느낀-점-후기)

---

## 1. 팀원 정보 및 업무 분담 내역

| 팀원 | 업무 내용 |
| :----: | --------- |
| 최혜원 | <li>accounts 관련 기능 설계 및 개발 (로그인, 로그아웃, 회원정보수정, 회원탈퇴, 프로필, 팔로잉 기능)</li><li>community 관련 기능 설계 및 개발 (영화 한줄 감상평, 리뷰 작성 / 수정 / 삭제, 리뷰 댓글 작성)</li><li>영화 추천 알고리즘 (영화 OST 재생 및 영화 추천, 사용자가 좋아요 버튼을 누른 영화 기반 추천)</li><li>웹 페이지 디자인</li> |
| 김수민 | <li>TMDB API키를 사용하여 영화 데이터 뽑아오기</li><li>movies 관련 기능 설계 및 개발 (메인 페이지 영화 인덱스, 영화 아이디 / 개봉일 / 평점 / 인기순 영화 조회 기능, 제목 기반 영화 검색 기능)</li><li>영화 추천 알고리즘 (영화 랜덤 추천, 장르별 영화 랜덤 추천)</li><li>웹 페이지 디자인</li> |

## 2. 목표 서비스 구현 및 실제 구현 정도

| 순번 | 기능 | 진행도 |
| -- | -- | -- |
| 1 |  |![](https://geps.dev/progress/0)|    
| 2 |  |![](https://geps.dev/progress/0)|    
| 3 |  |![](https://geps.dev/progress/0)|
| 4 |  |![](https://geps.dev/progress/0)|    
| 5 |  |![](https://geps.dev/progress/0)|

## 3. 데이터베이스 모델링 (ERD)

![](./README_IMG/er%20diagram.png)

## 4. 영화 추천 알고리즘에 대한 기술적 설명



## 5. 서비스 대표 기능에 대한 설명

**로그인**

- 로그인을 한 사용자만이 영화 상세페이지를 조회할 수 있으며, 영화 추천과 커뮤니티 서비스를 이용할 수 있습니다.
- 비밀번호를 잘못 입력한 경우 로그인 폼 상단에 올바른 정보를 입력하라는 경고가 생기면서 로그인을 막아줍니다.

**회원가입**

- 회원가입 유효성 검사를 통해 회원가입을 하려는 사용자가 유효하지 않은 정보를 기입할 경우 해당 정보를 다시 입력할 수 있도록 해줍니다.
- 이메일 주소는 입력하지 않아도 회원가입이 가능합니다. 하지만 이메일 주소를 입력할 경우에도 이메일 주소 형식을 맞춰 입력해야만 가입할 수 있습니다.

**메인 페이지**

- 비디오
    - 비디오의 왼쪽 상단에 영상을 멈추거나 다시 재생할 수 있는 버튼을 구현했습니다.
    - 영상을 멈추거나 다시 재생할 수 있는 버튼 옆에는 영상의 소리를 켜거나 끌 수 있는 버튼을 구현했습니다.

- 개봉 예정 및 최근 개봉 영화 / 인기있는 영화 / 평점 높은 영화
    - 각 테마에 해당하는 영화 데이터를 가져와 포스터를 보여줍니다.
    - 슬라이더 형식으로 구성하여 자동으로 영화 포스터들이 넘어가도록 구현했습니다.
    - 슬라이더의 양 옆과 하단에는 버튼을 만들어 사용자가 원할 때 버튼을 눌러 슬라이더를 넘길 수 있습니다.
    - 영화 포스터에 마우스를 올리면 영화 포스터가 확대되어 보입니다.
    - 영화 포스터를 클릭하면 해당 영화의 상세 페이지로 이동합니다.

**전체 영화 조회**

- 모든 영화 데이터들을 조회할 수 있습니다. 하단의 페이지네이션을 통해서 한 페이지당 18개의 영화목록이 나타납니다.
- 영화 포스터에 마우스를 올리면 영화 포스터가 180도 뒤집어지며 해당 영화의 제목이 나타납니다.
- 영화 포스터를 클릭하면 해당 영화의 상세 페이지로 이동합니다. 로그인을 하지 않은 사용자가 클릭했을 때는 로그인 페이지로 이동합니다.
- 영화 포스터 목록 오른쪽 상단에 드롭다운 버튼을 통해 인기순 / 최신순/ 오래된순/ 평점높은순으로 영화 목록을 조회할 수 있습니다.

**영화 검색**

- 검색어를 입력하면 해당 검색어를 제목에 포함하고있는 영화들이 검색 결과창에 나타납니다.

**영화 상세 조회**

- 해당 영화를 찜할 수 있습니다.
- 영화 정보 하단에 한줄 감상평을 작성하고 별점을 줄 수 있습니다.
- 한줄 감상평은 수정이 불가능하며 삭제만 가능합니다.

**영화 추천**

- OST로 영화추천
- 사용자가 찜한 영화를 기반으로 한 영화추천
- 영화 랜덤 추천
- 장르별 영화 추천

**커뮤니티**

- 커뮤니티
    - 다른 사용자들이 작성한 모든 영화 리뷰들을 조회할 수 있습니다.
    - 리뷰 카드에 마우스를 올리면 리뷰 카드가 조금 확대되어 보입니다.
    - 리뷰 카드를 클릭하면 해당 리뷰 상세 페이지로 이동합니다.
    - 화면 오른쪽 상단에 있는 리뷰 작성 버튼을 누르면 리뷰를 작성할 수 있습니다.

- 리뷰 작성
    - 리뷰 작성 페이지로 이동하면 리뷰의 제목과 내용을 작성하고 영화를 선택하여 

- 리뷰 상세 조회
    - 해당 리뷰에 좋아요를 누를 수 있습니다.
    - 해당 리뷰를 작성한 사용자의 이름을 누르면 해당 사용자의 프로필 페이지로 이동합니다.
    - 리뷰에 댓글을 작성할 수 있습니다. 댓글은 수정할 수 없으며 삭제만 가능합니다.

**프로필**

**회원 정보 수정**


## 6. 느낀 점, 후기

### 최혜원

### 김수민
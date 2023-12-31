
#### 여행지 추천 페이지  
![안녕하세요](https://github.com/gamepro6390/Final_Project/assets/135004060/6af781df-0220-4041-bcc9-a219f6812567)
- **여행지 DB 구축**  
   - 한국관광공사에서 제공되는 국문관광정보 OpenAPI 서비스 이용
   - 지역별 여행지: 강원, 부산, 인천, 광주, 울산, 경기(총 6개) 지역에 해당하는 여행지 정보 DB 저장
     1. 지역코드조회 오퍼레이션을 통해 지역코드 받음
     2. 해당 지역코드를 이용하여 지역기반 관광정보조회 오퍼레이션을 실행하면 여행지 정보를 받음
   - 코스별 여행지: 혼자,힐링,캠핑,가족,먹거리(총 5개) 코스에 해당하는 여행지 정보 DB 저장
     1. 지역코드조회 오퍼레이션을 통해 관광타입id, 여행지 코스 게시글id(=여러 여행지를 모아놓은 게시글) 받아옴
     2. 해당 관광타입id, 여행지 코스 게시글id를 이용해서 반복정보조회 오퍼레이션을 실행하면 하위콘텐츠id(=1개 여행지), 하위콘텐츠명을 받아옴
     3. 하위콘텐츠id를 이용해서 공통정보조회 오퍼레이션을 실행하면 하위콘텐츠에 해당하는 여행지 정보를 받음
     4. 하위콘텐츠id, 하위콘텐츠관광타입id를 이용해 소개정보조회 오퍼레이션을 실행하면 하위콘텐츠에 해당하는 여행지 세부 정보를 받음
  - 스케쥴러 기능: 수정된 내용 업데이트를 위해 하루에 한번 정해진 시간에 자동으로 실행되어 수정 테이블에 db 저장  
     1. 기존 내용을 갖는 테이블, 수정될 내용을 갖는 테이블을 두어 기존 테이블의 내용을 수정 테이블의 내용으로 변경
- **여행지 리스트**  
  - 페이징 기능: 10페이지씩 페이징되어 있으며, 10페이지 단위가 넘어가면 이전/이후 버튼을 통해 이전 10페이지, 이후 10페이지가 나오고,
    마지막 페이지수가 10페이지 단위가 아니면 이후 버튼이 나오지 않고 마지막 페이지수에서 페이지수 노출이 끝나게 구현
  - 검색 기능: 장소명, 주소 카테고리를 이용해서 검색 가능
  - 이전 버튼을 통한 이전 페이지 돌아가기 기능
- **여행지 상세 조회**  
  - 여행지 대표사진: 여행지 대표 사진 제공
  - 여행지 상세정보
    - 여행지 지도 제공: 카카오 지도 api를 활용 - 여행지 기반 지도 확대/축소, 여행지 큰지도보기, 길찾기 기능 제공
    - 여행지 날씨 제공
    - 여행지 상세정보 제공
      - 지역별 여행지: 여행지 설명, 대표 홈페이지 링크 연결
      - 테마별 여행지: 문의 및 안내, 유모차 대여여부, 신용카드 사용가능여부, 애완동물 동반가능여부, 쉬는날, 이용시간, 대표메뉴, 할인여부, 포장가능여부 등
  - 여행지 한줄평 남기기
    - 댓글 CRUD 기능: 로그인한 회원만 사용 가능, 수정/삭제 버튼은 해당 글 작성자에게만 노출됨
    - 댓글 신고 기능: 로그인한 회원만 사용 가능
  - 여행지 상세페이지 클릭시 조회수 증가 기능
  - 여행지 상세페이지 링크 공유 기능: 링크가 자동으로 복사
  - 여행지 상세페이지 좋아요 기능
    - 같은 사용자가 중복해서 좋아요를 누를 경우 좋아요 기능 사용 불가(alert창 이용-좋아요 이용 불가 사유 알림)
    - 로그인한 사용자만 이용 가능
    - 좋아요 취소 가능


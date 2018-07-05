# Watcha - 3일

* 댓글을 입력받을 폼을 작성

* form(요소)이 제출(이벤트)될 때(이벤트리스너) 

* form에 input(요소)안에 있는 내용물(요소)을 받아서

* ajax요청으로 서버에 `/create/comment`로 요청을 보낸다.

* 보낼 때에는 내용물, 현재 보고있는 movie의 id값도 같이 보낸다.

* 서버에서 저장하고, response 로 보내줄 `js.erb`파일을 작성한다.

* `js.erb` 파일에서는 댓글이 표시될 영역에 등록된 댓글의 내용을 추가해준다.

* comment model 만들기

* 다대다 관계에서 through가 없으면 느슨한 다대다 관계가 된다.

* Adding colleciton routes

  ```ruby
    resources :movies do
      member do
        get '/test' => 'movies#test_member'
      end
      
      collection do
        get '/test' => 'movies#test_collection'
      end
    end
  ```

  `rake routes`

  ```ruby
      test_movie GET    /movies/:id/test(.:format)     movies#test_member
      test_movies GET    /movies/test(.:format)         movies#test_collection
  ```

### 삭제

* 댓글에 있는 삭제 버튼(요소)을 누르면(이벤트 리스너)
* 해당 댓글이 눈에 안보이게 되고(이벤트 핸들러),
* 실제 DB에서도 삭제가 된다(ajax)

### 수정

* 수정 버튼을 클릭하면
* 댓글이 있던 부분이 입력창으로 바뀌면서 원래 있던 댓글의 내용이 입력창에 들어간다.
* 수정버튼은 확인버튼으로 바뀐다.
* 내용 수정 후 확인 버튼을 클릭하면
* 입력창에 있던 내용물이 댓글의 원래 형태로 바뀌고 
* 확인버튼은 다시 수정버튼으로 바뀐다.
* 입력창에 있던 내용물을 ajax로 서버에 요청을 보낸다.
* 서버에서는 해당 댓글을 찾아 내용을 업데이트 한다.



### 과제

------



* 수정 버튼을 누르면

* 전체 문서 중에서 `update-comment`클래스를 가진 버튼이 있는 경우에

* 더이상 진행하지 않고 이벤트 핸들러를 끝냄 return false;

* $('.class').length() : 요소 갯수 구하기

  ```ruby
  .update-comment		: 속성값
  update-comment		: 태그값
  ```

  

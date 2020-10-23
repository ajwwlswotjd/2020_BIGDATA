# 2020년 10월 19일 (월)

+ 이론내용
    + 기본 이론
        + Jupyter 사용 ( 8888번 포트사용, localhost 접속시 root 로그인 )
        + 파이썬 변수 및 type 등등, 변수명 지정 (camel 표기법), 변수명 사이에 공백이 존재하면 안됨
        + 예약어 사용불가 Ex) import , True , False 
        + 식별자 ( 세미콜론 [;] 사용하지 않음 )


+ 변수
    + 여러개의 변수에 여러개의 값 저장

    ```
    변수1, 변수2, 변수3, 변수4 ... = 값1, 값2, 값3, 값4 ...
    Ex) a, b, c = 10, 20, 30
    ```

    + 여러개의 변수에 한개의 값 저장

    ```
    변수1 = 변수2 = 변수3 = 값
    Ex) a = b = c = 30
    ```

    + 두 변수값 교환 ( a 와 b 교환 )
 
    ``` C
    a = 20
    b = 30
    a,b = b,a
    ```

    + 변수 삭제

    ``` C
    a = 10
    print(a)
    del a
    print(a)
    # is not defined 에러가 뜬다.
    ```

+ 문자열


    + 기본적으로 큰따옴표 "" 를 사용한다

    ``` C
    name = "정재성"
    age = 23
    print( name , age )
    ```

    + 작은따옴표 '' 또한 사용 가능하다

    ``` C
    address = '경기도 광주시'
    print(address)
    ```
    

    + 문자열 결합

    ``` C
    name = "정재성"
    age = 23
    print( "제 이름은 " + name + " 입니다" )
    # int type 의 변수는 문자열끼리 결합이 되지 않으므로 str 함수로 감싸준다.
    print( "저의 나이는" + age + "살 입니다" )      X
    print( "저의 나이는" + str(age) + "살 입니다" ) O
    ```

+ 연습문제

    + 변수 연습문제

    ``` C
    name = "홍길동"
    no = 2016001
    year = 4
    grade = "A"
    average = 93.5

    print( "성명 : " + name         )
    print( "학번 : " + str(no)      )
    print( "학년 : " + str(year)    )
    print( "학점 : " + grade        )
    print( "평균 : " + str(average) )

    # 위아래 모두 가능하다.

    print( "성명 : " , name    )
    print( "학번 : " , no      )
    print( "학년 : " , year    )
    print( "학점 : " , grade   )
    print( "평균 : " , average )
    ```


    + 포맷코드 사용 

    ``` C
    age = 30
    name = "홍길동"
    print("제 이름은 %s 이고, 나이는 %d살 입니다" % ( name, age ) )
    ```
    
    + 포맷코드 종류
        + %d : int type 의 변수에 사용
        + %s : string type 의 변수에 사용
        + %f : flat type 의 변수에 사용
        + %c : char type 의 변수에 사용 
        + %.nf : f 앞의 숫자 n은 소수이하자리를 말한다. Ex) %.2f === 소수이하 2째자리

    ``` C
    print( "성명 : %s" , name    )
    print( "학번 : %d" , no      )
    print( "학년 : %d" , year    )
    print( "학점 : %c" , grade   )
    print( "평균 : %f" , average )
    ```

***

# 2020년 10월 20일 (화)

+ if문
    + 기본 이론
        + ~~근데 이건 다 아는건데 굳이 필기를 해야하나 싶다.~~
        + 조건식이 참이면 if문 수행
        + 조건식이 거짓이면 else문 수행
        + python 에서 if 는 중괄호가 아닌 탭으로 구성된다.

    + 비밀번호 검사

    ``` C
    password = 1234
    if password == 1234 :
        print("비밀번호가 맞습니다.")
    else :
        pass # 아무것도 수행하지 않을경우
    ```

    + 로그인 프로그램 작성

    ``` C
    id = 'flower'
    password = '1234'
    #사용자로 부터 키보드 입력 값 받기
    input_id =   input("아이디 입력 : ") # 입력받은 데이터는 문자열로 처리된다.
    input_pass = input("비밀번호 입력 : ")
    # 두 값이 모두 일치하면 로그인 성공
    if ( id == input_id ) and ( password == input_pass ) :
    print("로그인 성공")
    else :
    print("로그인 실패")
    ```

    + 사용자로부터 두 수를 입력받아 더한 결과를 출력하는 코드 작성

    ``` C
    su1 = int( input('첫번쨰 수 입력 : ') )
    su2 = int( input('두번쨰 수 입력 : ') )
    print( su1 + su2 )
    ```

    + if elif else 사용
    ``` C
    # 정수 3개를 입력 받아서 제일 큰 수 출력
    su1 = int(input("수 입력 : "))
    su2 = int(input("수 입력 : "))
    su3 = int(input("수 입력 : "))
    if (su1 >= su2) and (su1 >= su3) :
        print(su1)
    elif (su2 >= su1) and (su2 >= su3) :
        print(su2)
    else :
        print(su3)
    ```

+ 반복문

    + 기본 이론 
        + 출력시 print문은 줄바꿈을 표현한다. 줄바꿈 없이 출력 end = ''
        + 예를 들면 print(name, end=' ')

    + for 변수 in 리스트 또는 범위

    ``` C
    for name in ['홍길동' , '이몽룡' , '성춘향', '변학도'] :
        print(name)
    for x in range(0,10) :
        print(x)
    ```

    + range 사용

    ``` C
    for x in range(0,10,2) :
        print(x)
    # 결과 : 0,2,4,6,8
    ```

    ``` C
    # 숫자 11부터 21까지 한칸씩 띄어서 출력할 것
    for x in range( 11 , 22 ) :
        print(x , end=" ")
    ```

    ``` C
    # 1부터 10까지 합 출력
    sumx = 0
    for num in range(1,11) :
        sumx = sumx + num
    print(sumx)
    ```
+ 문자열 ~~이걸 왜 또해?~~

    + 문자열 곱하기 *

    ``` C
    # 문자열이 곱한 수 만큼 반복되어 생성됨
    string = 'python'
    result = string * 3
    print(result)
    # 결과 : pythonpythonpython
    ```
    + 문자열 인덱싱
        + string[n]    인덱스 n번째 문자
        + string[-1]   마지막 문자
        + string[0:n]  0부터 n-1 번쨰 까지의 문자열
        + string[n:]   n부터 끝까지
        + string[:n]   0부터 n-1 까지
        + string[-1:]  마지막 문자 (마지막에서 끝까지)
        + string[:-1]  처음부터 마지막-1 까지
        + string[:]    처음부터 끝까지 (문자열 전체)
    
    + 문자열 슬라이싱 예제

        ``` C
        crawling = "Data crawling is fuxking"
        parsing = "data parsing is also fuxking"

        print(crawling)
        print(crawling[0:4])      # 0-3
        print(crawling[5:16])     # 5-15
        print(crawling[17:])      # 17-끝
        print(crawling[19])       # 19 (20번쨰 문자) - 인덱스가 0부터 시작해서
        print(crawling[-1:])      # 마지막에서 끝까지 (마지막 문자)
        print(crawling[:-1])      # 처음부터 마지막 -1 까지
        print(crawling[16:16+4])  # 16-19

        # 문자열 인덱싱에는 대입 연산자 사용이 불가능하다.
        # Ex) crawling[5] = 'h' (X)
        ```

    + 문자열 in 문자열

    ``` C
    string = 'python programming'
    print('python' in string) # 결과 : True
    print('Python' in string) # 결과 : False

    if 'python' in string :
        print('있음')
    else :
        print('없음')
    ```

    + 문자열 기본 내장 함수들
        + len() : 문자열의 길이 변환

        ``` C
        str = "hello"
        print(len(str))
        # 결과 : 5
        ```
            
        + count() : 무자열 내에 들어있는 특정 문자의 개수 변환

        ``` C
        str = 'programming'
        print(string.count('m'))
        # 결과 : 2

        ```

        + split() : 구분자를 기준으로 문자열을 나누고, 리스트 형태로 반환한다.

        ``` C
        # 구분자 : 기본 공백, 옵션으로 구분자를 지정할 수 있음.

        str = '2003-11-14'
        splited_str = str.split('-')
        print(splited_str)
        # 결과 : ['2003','11','14'] - 결과는 리스트 형태로 반환된다.

        names = '박현진,이석,정효민,김민규,김헌주'
        name_arr = names.split(',')
        print(name_arr)
        # 결과 : ['박현진', '이석', '정효민', '김민규', '김헌주']

        colors = 'red:orange:yellow:green:blue'
        color_arr = colors.split(":")
        print(color_arr)
        # 결과 : ['red', 'orange', 'yellow', 'green', 'blue']

        ```

        + replace() : 전체 문자열에서 특정 문자열을 찾아 다른 문자열로 변경 후 반환

        ``` C
        # 문자열.replace( {찾는 문자열} , {변경할 문자열} )
        # replace() 는 새로운 문자를 반환하며, 원본 문자열을 변경하지 않는다.

        course = "Java programming"
        course_replaced = course.replace("java" , "Python")
        print( course_replaced )
        # 결과 : Python programming

        str = "hello 이석, hello 현진, hello 헌주, hello 효민, hello 민규"
        course_replaced = course.replace("hello" , "안녕")
        print( course_replaced )
        # 결과 : 안녕 이석, 안녕 현진, 안녕 헌주, 안녕 효민, 안녕 민규

        ```

        + join() : 각 문자 사이에 특정 문자 삽입

        ``` C
        # 문자열 사이에 구분자 삽입 허용
        # 리스트에 있는 모든 문자를 하나로 구성할때 사용 (리스트 함수)

        a = 'aa'
        b = a.join('bbb') # a 변수의 값을 bbb 사이에 삽입
        print(b)
        # 결과 : baabaabaa

        a = '-'
        print(a.join('abce'))
        # 결과 : a-b-c-e

        sep = '=='
        names = ['김민규', '정효민', '박현진']
        print(sep.join(names))
        # 결과 : 김민규==정효민==박현진

        ```

        + 영어 대소문자 전환 함수
            + upper() : 전부 대문자로  
            + lower() : 전부 소문자로
            + capitalize() : 문장의 첫번째 문자를 대문자로
            + title() : 각 단어의 첫글자를 대문자로 변경
        
        ```C
        str = "my name is Hong Gil Dong"
        str.upper() # MY NAME IS HONG GIL DONG
        str.lower() # my name is hong gil dong
        str.capitalize() # My name is Hong Gil Dong
        str.title() # My Name Is Hong Gil Dong
        ```

        + 타입 여부 확인 함수
            + isalpha() : 문자여부 결과 반환 ( True/False )
            + isdigit() : 숫자여부 결과 반환 ( True/False )
            + isspace() : 공백여부 결과 반환 ( True/False )
            + isalnum() : 문자 또는 숫자여부 결과 반환 ( True/False )
            + 문제 예제

            ```C
            # 알파뱃, 숫자, 스페이스, 기타의 갯수를 계산 후 출력한다.

            str = input('문자열 : ')

            alCnt = 0
            numCnt = 0
            spaceCnt = 0
            etcCnt = 0

            for s in str :
                if s.isalpha() :
                    alCnt+=1
                elif s.isdigit() :
                    numCnt+=1
                elif s.isspace() :
                    spaceCnt+=1
                else :
                    etcCnt+=1

            print("문자 갯수 : %d개" % alCnt)
            print("숫자 갯수 : %d개" % numCnt)
            print("공백 갯수 : %d개" % spaceCnt)
            print("기타 갯수 : %d개" % etcCnt)
            ```

+ 리스트
    + 기본 이론
        + 동일한 이름을 갖는 원소들의 연속 저장 영역
        + 여러 개의 데이터가 저장되어 있는 장소 (집합적 자료형)
        + 각 원소는 인덱스(index) 로 구분 (인덱스는 0부터 시작)
        + 배열의 원소(값) 변경 가능
        + 크기가 가변적임
        + 다양한 종류의 데이터를 한번에 넣을 수 있음

        ``` C
        ints = [10, 64, 52, 78, 97]
        floats = [1.65, 3.66, 1.5, 88.75, 23.46]
        names = ["고헌준", "신준하", "정효민", "이석", "박현진", "김민규"]

        # 리스트 안에 리스트 포함 가능
        numbers = [ 100, 200, 300, 600, [ 1,10,100,1000 ] ]
        ```

        + for 에서 리스트 사용
        
        ``` C
        for name in names :
            print(name , end=' ')
        # 결과 : 고헌준 신준하 정효민 이석 박현진 김민규
        ```

    + 리스트 출력
        
    ``` C
    numbers = [ 100, 200, 300, [ 10, 20, 30 ] ]
    numbers[3][1]

    for n in range(0 , len(numbers)) :
        print(numbers[n])

    # 결과
    # 100
    # 200
    # 300
    # [10, 20, 30]
    ```

    + 리스트 변수 지정
    
    ``` C
    nums = [1, 2, 3]
    a,b,c = nums
    print(a, b, c)
    # 결과 : 1 2 3
    ```

    + 리스트 인덱싱

    ``` C
    a = [ 1, 2, 3, 4, 5 ]
    print( a[0]  ) # 결과 : 1 - a의 0번째
    print( a[-1] ) # 결과 : 5 - a의 마지막 번째
    print( a[-2] ) # 결과 : 4 - a의 마지막-1 번째

    b = [1, 2, 3, [ 10, 20 ] ]
    c = [ 1, 2, 3, [ 10, 20 ], 4, 5 ]
    all_list = [ a, b, c ]    
    
    print(all_list)
    # 결과 : [ [ 1, 2, 3, 4, 5 ], [ 1, 2, 3, [ 10, 20 ] ], [ 1, 2, 3, [ 10, 20 ], 4, 5 ] ]

    print(all_list[-1][3][0])
    # 결과 : 10
    ```

    + 리스트 슬라이싱
        + ~~문자열 슬라이싱과 동일하니까 그만 알아보자.~~

***

# 2020년 10월 21일 (수)

+ 튜플
    + 기본 이론
        + 리스트와 유사한 집합적 자료형이지만, 리스트와 달리 원소 변경 불가
        + 추가 / 수정/ 삭제 불가능
        + 소괄호를 사용해서 만든다.

        ``` C
        # 튜플 = (값1, 값2, 값3)

        t1 = ( 1, 2, 3 )
        t2 = 4, 5, 6 # 소괄호 없이도 튜플 생성 가능
        t3 = t1, ( 7, 8, 9 ) # 튜플 내에 또다른 튜플 사용가능
        t4 = [1,2] , [4,5] # 리스트로 튜플 가능
        t5 = tuple( [1,2,3,4,5] ) # tuple 함수 사용 
        t6 = ([5, 6, 7, 8]) # 리스트 하나를 원소로 갖는 튜플

        print(t4)
        # 결과 : ([1, 2], [4, 5])

        print(t4[0])
        # 결과 : [1, 2]

        print(t5)
        # 결과 : (5, 6, 7, 8) - 튜플 함수를 사용하면 기존 리스트를 튜플로 변환시킨다.
        
        print(t6)
        # 결과 : [5, 6, 7, 8]
        ```
    
    + 튜플 리스트 변환

    ``` C
    t1 = ( 1, 2, 3 )
    t2 = t1, ( 7, 8, 9 )

    to_list1 = list(t1)
    to_list2 = list(t2)

    print(to_list1)
    # 결과 : [1, 2, 3]

    print(to_list2)
    # 결과 : [(1, 2, 3), (7, 8, 9)]
    # 튜플 내 튜플 원소는 변환 후에도 그대로 튜플로 유지된다.
    ```

    + 튜플 주의할 점
    ``` C
    t = ( 1, 2, 3 )
    t[0] = 5 # 튜플은 변경이 불가능하다.
    # 에러 발생 : 변경 불가

    t7 = ( 1 )
    print(t7)
    # 결과 : 1

    # 소괄호 없이 튜플을 생성할때 원소가 1개인 튜플을 생성하는 방법
    t8 = 2,
    print(t8)
    # 결과 : (2,)
    ```

+ 딕셔너리 
    + 기본 이론
        + 키(key) 와 값(value) 의 한 쌍을 요소로 갖는 자료형
        + 구성 : 딕셔너리 = { 키1 : 값1 , 키2 : 값2 }

        ``` C
        human = { "name" : "정재성" , "birth" : "2003-11-14", "hair" : "풍성" }

        d = { 1 : 'a' }
        print(d)
        # 결과 : {1 : 'a'}

        # 딕셔너리에 item 추가
        # 딕셔너리 변수[새로 추가될 key] = 대응 value 값
        d[2] = 'b'
        d['name'] = '홍길동'
        print(d)
        # 결과 : {1 : 'a', 2 : 'b', 'name' : '홍길동'}

        # 딕셔너리 접근
        print( d['name'] )
        # 결과 : 홍길동
        ```
    
    + 딕셔너리 관련 함수
        + 딕셔너리.keys()   : key 만 추출해서 리스트로 반환
        + 딕셔너리.values() : value 만 추출해서 리스트로 반환
        + 딕셔너리.items()  : (key , value) 형태의 튜플로 감싸진 리스트로 반환
        + 함수 예제
        ``` C
        naver = {
            "name" : "naver",
            "url" : "https://naver.com",
            "userId" : "nv",
            "password" : "1234"
        }

        print(naver.keys()) # key 들을 리스트 형태로 반환
        # 결과 : [ 'name' , 'url' , 'userId', 'password' ]

        print(naver.values()) # value 들을 리스트 형태로 반환
        # 결과 : [ 'naver' , 'https://naver.com' , 'nv', '1234' ]

        print(naver.items()) # (key , value) 형태로 모든 item 을 리스트로 반환
        # 결과 : [ 'name' , 'url' , 'userId', 'password' ]

        print( naver.keys()[0] )
        # 결과 : 에러가 발생한다. - 반환 객체가 list를 포함하는 dict_keys 형태로 반환되기 때문
        # 이를 사용하려면 list() 함수를 사용해 list 형태로 변환 시켜야 한다.
        print(list( naver.keys() )[0]) 
        # 결과 : 'name'
        ```
    + 반복문 사용
        + 예제

        ``` C
        naver = {
            "name" : "naver",
            "url" : "https://naver.com",
            "userId" : "nv",
            "password" : "1234"
        }

        for key in naver.keys() :
            print(key)

        # 결과 
        # name
        # url
        # userId
        # password
        ```

        + 문제

        ``` C
        # naver 딕셔너리의 values 를 모두 출력
        # 단, 반복문과 딕셔너리 관련 함수를 사용 할 것
        naver = {
            "name" : "naver",
            "url" : "https://naver.com",
            "userId" : "nv",
            "password" : "1234"
        }

        for value in naver.values() :
            pirnt(value)
        ```

    + key 로 value 찾기

    ``` C
    naver = {
        "name" : "naver",
        "url" : "https://naver.com",
        "userId" : "nv",
        "password" : "1234"
    }
    print( naver['name']     ) # 결과 : naver 
    print( naver.get('name') ) # 결과 : naver 동일

    print( naver['link'] )
    # 키가 없으므로 에러가 발생

    print( naver.get('link') ) # None 출력
    print( naver.get('link' , '없지롱') ) # 없지롱 출력
    # 딕셔너리의 get 함수는 키값이 없을때 None 이나 다른 값으로 대체 할 수 있다.

    print('link' in naver) # 결과 : False
    print('link' not in naver) # 결과 : True
    ```

+ csv 파일
    + 서울시 구별 CCTV 현황 분석
        1. 서울시 각 구별 cctv 수를 파악하고 인구대비 cctv 비율을 구해 순위 비교
        2. 인구대비 cctv 평균치를 확인하고 cctv가 과하게 부족한 구를 확인
        3. 고령자 대비 cctv 수 확인 
        4. 외국인 대비 cctv 수 확인
        + 필요한 데이터
            1. 서울시 지자체별 cctv 현황 data
            2. 서울시 지자체별 인구 현황 data
            + 교재 23쪽
        
        + 데이터 분석 
            + CCTV 현황 csv 읽기

            ``` C   
            # 데이터 분석을 위해서는 반드시 페키지를 import 해야 함
            # pandas (데이터 분석) , numpy (수치 분석) 패키지
            # 패키지는 관련 함수들의 모임
            # import 패키지명 
            # 패키지 명이 너무 길면 별명을 생성 할 수 있다.
            # import 패키지명 as 별명 

            import pandas as pd
            import numpy as np

            # 데이터 파일 읽어오기
            # 01. CCTV_in_Seoul.csv ( 파일명이 다르면 읽지 못한다. 띄어쓰기에 주의할 것 )
            # 한글 포함 여부에 따라 옵션이 달라진다.
            # 한글 포함시 encoding 방식 지정 필요
            # UTF-8 방식이 있고, - utf-8 (보통 이걸 많이 씀)
            # euc-kr 방식이 있다. - ansi 
            # 외부 파일 읽을때는 경로에 주의해야하고 상대경로를 사용하는것이 원칙이다.
            # 사용 data 는 내문서\data\
            # 코드파일은 내문서\파이썬_1021\
            # '../data/01. CCTV_in_Seoul.csv' 

            CCTV_seoul = pd.read_csv( '../data/01. CCTV_in_Seoul.csv' , encoding='utf-8' )
            # read_csv() 함수는 csv  파일을 일겅와서 데이터프레임 형태로 저장
            # 데이터 프레임은 세로 데이터의 제목인 컬럼명이 있고
            # 가로 데이터를 구분하는 인덱스를 갖고 있다.  

            CCTV_seoul.head()
            CCTV_seoul.head(10)
            # head 함수() :  데이터프레임의 데이터를 위에서부터 지정된 숫자만큼 출력
            # 인자값이 비어있으면 5줄을 출력한다 (필드제목 제외)

            CCTV_seoul.tail()
            CCTV_seoul.tail(10)
            # tail 함수() : head 함수랑 반대로 생각하면 됨

            # 데이터 프레임은 컬럼명으로 컬럼을 접근하기 때문에 의미있는 컬럼명으로 사용해야한다.
            # 컬럼명만 출력
            print( CCTV_seoul.columns )

            # 컬럼명 변경
            # rename 함수 사용 : df.rename( coulmns = { 바꿀위치 : 새로운이름값 } ) - 원본을 변경하지않고, 변경된 값을 return 하게 되어있다.
            # inplace 옵션을 True 로 주면 원본값이 변경되게 되어있다. 
            CCTV_seoul.rename( columns = { CCTV_seoul.columns[0] : '구별' } )
            CCTV_seoul.rename( columns = { CCTV_seoul.columns[0] : '구별' } , inplace = True )
            ```

            + 서울시 인구 현황 가져오기 - 엑셀파일 읽기

            ``` C 
            import pandas as pd
            import numpy as np

            pop_Seoul = pd.read_excel('../data/01.population_in_Seoul.xls' , header = 2 , usecols = 'B,D,G,J,N' , encoding='utf-8')
            pop_Seoul.head()

            # 컬럼명 변경 => 0 : 구별, 1 : 인구수, 2 : 한국인, 3 : 외국인, 4 : 고령자
            pop_Seoul.rename( columns = { pop_Seoul.columns[0] : '구별', pop_Seoul.columns[1] : '인구수', pop_Seoul.columns[2] : '한국인', pop_Seoul.columns[3] : '와국인', pop_Seoul.columns[4] : '고령자' } , inplace = True )
            pop_Seoul.head()
            ```

            + cctv 데이터 파악하기

            ``` C
            # 설치대 대수가 작은 5개 구는 어디인가? - 소계가 총 설치대수 이므로 소계를 기준으로 sort 한다.

            import pandas as pd
            import numpy as np            

            CCTV_seoul = pd.read_csv( '../data/01. CCTV_in_Seoul.csv' , encoding='utf-8' )
            CCTV_seoul.rename( columns = { CCTV_seoul.columns[0] : '구별' } , inplace = True )

            pop_Seoul = pd.read_excel('../data/01.population_in_Seoul.xls' , header = 2 , usecols = 'B,D,G,J,N' , encoding='utf-8')            
            pop_Seoul.rename( columns = { pop_Seoul.columns[0] : '구별', pop_Seoul.columns[1] : '인구수', pop_Seoul.columns[2] : '한국인', pop_Seoul.columns[3] : '와국인', pop_Seoul.columns[4] : '고령자' } , inplace = True )

            # 정렬함수 sort_values( by = '기준열 이름' , ascending = True ) : 오름차순 정렬
            CCTV_seoul.sort_values( by = '소계' , ascending = True ).head()

            # CCTV 대수가 많은 5개 구는 어디인가?
            # 소계를 기준으로 내림차순 정렬
            CCTV_seoul.sort_values( by = '소계' , ascending = False ).head()
            ```

***

# 2020년 10월 22일 (목)

+ 어제 하던거 마저 하기
    + cctv 데이터
    
    ``` C
    # CCTV 최근 증가율 계산해서 '최근 증가율' 컬럼 추가
    # 데이터프레임에 컬럼을 추가할 때는 -  df명['새로 추가될 컬럼명'] = 값

    import pandas as pd
    import numpy as np            

    CCTV_seoul = pd.read_csv( '../data/01. CCTV_in_Seoul.csv' , encoding='utf-8' )
    CCTV_seoul.rename( columns = { CCTV_seoul.columns[0] : '구별' } , inplace = True )
    CCTV_seoul['최근증가율'] = ( CCTV_seoul['2014년'] + CCTV_seoul['2015년'] + CCTV_seoul['2016년'] ) / CCTV_seoul['2013년도 이전'] * 100
    CCTV_seoul.head()

    # 3개년간 CCTV 설치 증가율이 높은 5개 구를 출력
    CCTV_seoul.sort_values( by='최근증가율' , ascending = False ).head(5)
    ```

    + 서울시 인구 데이터 파악하기

    ``` C

    import pandas as pd
    import numpy as np

    pop_Seoul = pd.read_excel('../data/01.population_in_Seoul.xls' , header = 2 , usecols = 'B,D,G,J,N' , encoding='utf-8')            
    pop_Seoul.rename( columns = { pop_Seoul.columns[0] : '구별', pop_Seoul.columns[1] : '인구수', pop_Seoul.columns[2] : '한국인', pop_Seoul.columns[3] : '와국인', pop_Seoul.columns[4] : '고령자' } , inplace = True )
    
    # 첫 행 합계는 계산 행 이므로 삭제
    # 삭제 함수 : del 명령어, drop() 함수
    # 행 삭제 : drop 함수
    # 열 삭제 : del 명령어

    pop_Seoul.drop(0).head()
    pop_Seoul.drop(0 , inplace = True)
    pop_Seoul.head()
    ```

    + 각 구가 모두 데이터로 있는지 확인하는 작업

    ``` C
    # 1. 각 구별 데이터가 있어야함
    # 2. 중복된 데이터가 없어야함

    import pandas as pd
    import numpy as np
    
    CCTV_seoul = pd.read_csv( '../data/01. CCTV_in_Seoul.csv' , encoding='utf-8' )
    CCTV_seoul.rename( columns = { CCTV_seoul.columns[0] : '구별' } , inplace = True )
    CCTV_seoul['최근증가율'] = ( CCTV_seoul['2014년'] + CCTV_seoul['2015년'] + CCTV_seoul['2016년'] ) / CCTV_seoul['2013년도 이전'] * 100

    pop_Seoul = pd.read_excel('../data/01.population_in_Seoul.xls' , header = 2 , usecols = 'B,D,G,J,N' , encoding='utf-8')            
    pop_Seoul.rename( columns = { pop_Seoul.columns[0] : '구별', pop_Seoul.columns[1] : '인구수', pop_Seoul.columns[2] : '한국인', pop_Seoul.columns[3] : '와국인', pop_Seoul.columns[4] : '고령자' } , inplace = True )

    
    
    pop_Seoul['구별'].unique()
    #  구별 데이터에 nan 데이터가 들어있음 : nan = null => 삭제필요
    # nan에 해당하는 행 전체 삭제 : 구별값이 nan인 행의 인덱스 확인
    # nan을 확인하는 함수 -  df명['필드명'].isnull()
    # 해당 행을 출력해서 확인

    # 데이터프레임명[필드명 또는 조건식] : 데이터 행에 접근
    pop_Seoul[ pop_Seoul['구별'].isnull() ]
    # 결과 : 26

    pop_Seoul.drop( [26] , inplace = True ) # 한번 실행하면 다시 실행되지 않도록 하기

    # 제거 확인
    pop_Seoul.tail()
    len( pop_Seoul )


    ```
    
    + 문제 풀기 1

    ``` C
    # 1. 어느 구의 인구가 가장 많은가? 
    # 2. 외국인이 많은 5개 구 를 출력
    # 3. 인구수 대비 외국인 많은 5개 구를 출력
    # 4. 고령자가 많은 5개 구를 출력

    print("=======1번=======")
    print( pop_Seoul.sort_values( by='인구수' , ascending = False ).head(1) )
    print("=======1번=======")
    print("")
    print("=======2번=======")
    print( pop_Seoul.sort_values( by='외국인' , ascending = False ).head(5) )
    print("=======2번=======")
    print("")
    print("=======3번=======")
    print( pop_Seoul.sort_values( by='외국인비율' , ascending = False ).head(5) )
    print("=======3번=======")
    print("")
    print("=======4번=======")
    print( pop_Seoul.sort_values( by='고령자비율' , ascending = False ).head(5) )
    print("=======4번=======")
    ```

    + 데이터 병합
    
    ``` C
    # CCTV_Seoul과 pop_Seoul 병합코드
    # 공통컬럼인 '구별' 컬럼으로 조인
    # 양쪽 모두 25개의 구로 이루어져있음
    # merge 함수
    # pd.merge( 조인할df1, 조인할 df2, on='공통필드' )

    data_result = pd.merge( CCTV_seoul, pop_Seoul , on='구별' )
    data_result.head()

    # 사용하지 않을 컬럼 삭제
    # CCTV의 소계, 최근 증가율을 제외한 년도관련 data 는 삭제

    del data_result['2013년도 이전']
    del data_result['2014년']
    del data_result['2015년']
    del data_result['2016년']

    data_result.head()

    # 그래프 그릴때 축데이터를 쉽게 지정하기 위해서 행 인덱스를 구별로 변경
    # 행인덱스 지정 함수 : set_index('지정렬 이름' , inplace=True )

    data_result.set_index( '구별' , inplace = True )
    data_result.head()

    # 다수의 데이터 중 상관관계가 가장 큰 데이터를 비교
    # 인구와 관련된 각 필드와 CCTV 소계와의 상관 계수를 파악한 후 의미있는 그래프 표현

    # 상관계수 : 두 변수의 관련성을 확인하는 방법
    # 절대값이 클수록 두 데이터는 관련이 있다고 판단
    # 절대값을 기준으로 0.1 이하 무시
    # 0.3 이하 약한 상관 관계
    # 0.7 이상 강한 상관 관계

    # 상관관계 파악 변수 (컬럼)
    # CCTV총대수와 인구수
    # CCTV총대수와 고령자 비율
    # CCTV총대수와 외국인 비율

    # 계산 함수 numpy 패키지 corrcoef( data1, data2 )

    np.corrcoef( data_result['소계'] , data_result['인구수'] ) # CCTV총대수와 인구수 : 약한 상관관계 - 그래프 표현
    np.corrcoef( data_result['소계'] , data_result['고령자비율'] ) # CCTV총대수와 고령자비율 : 약한 음의 상관관계 - 그래프 표현
    np.corrcoef( data_result['소계'] , data_result['외국인비율'] ) # CCTV총대수와 외국인비율 : 약한 음의 상관관계 - 그래프 표현
    ```

    + 그래프 표현
        + 라이브러리 import 

        ``` C 
        # 파이썬의 그래프 그리는 모듈(패키지) : matplotlib.pyplot
        # 서브 패키지 pyplot 이용

        import matplotlib.pyplot as plt

        # 그래프는 새창이 뜨면서 드로잉을 하는데 
        # 새창 띄우지 말고 소스코드 안에서 드로잉 하라는 명령 입력 
        %matplotlib inline

        #한글문제 발생
        #matplotlib의 기본폰트에서 한글지원 폰트가 없음
        #패키지의 폰트를 추가하고 사용
        #윈도우 용
        import platform

        from matplotlib import font_manager, rc
        plt.rcParams['axes.unicode_minus'] = False

        if platform.system() == 'Darwin':  # 맥OS 
            rc('font', family='AppleGothic')
        elif platform.system() == 'Windows':  # 윈도우
            path = "c:/Windows/Fonts/malgun.ttf"
            font_name = font_manager.FontProperties(fname=path).get_name()
            rc('font', family=font_name)
        else:
            print('Unknown system...  sorry~~~')
        ```

        + 그리는 코드

        ``` C
        # 구별 CCTV 설치대수를 그래프로 표현
        # 수평 막대 그래프 
        # 전체 그림 크기( 그림 영역 설정 plt.figure(figsize=(10,10)) )
        
        plt.figure( figsize=( 10 , 10 ) )
        # 그래프 그리기 plot(kind=그래프종류값, grid = T/F (격자무늬) )
        
        data_result['소계'].plot( kind='barh' , grid = True )
        
        # 구별 CCTV 설치대수 그래프
        # 수평막대 그래프 - 정렬해서 그래프 출력 
        s = data_result['소계'].sort_values()
        plt.figure( figsize = (10 , 10) )
        plt.barh( s.index, s )
        plt.grid()
        plt.show()
        ```

***

# 2020년 10월 23일 (금)

+ 하던거 마저 하기
    + 어제 하던거 코드 데이트

    ``` C
    # 1. 각 구별 데이터가 있어야함
    # 2. 중복된 데이터가 없어야함

    import pandas as pd
    import numpy as np

    CCTV_seoul = pd.read_csv( '../data/01. CCTV_in_Seoul.csv' , encoding='utf-8' )
    CCTV_seoul.rename( columns = { CCTV_seoul.columns[0] : '구별' } , inplace = True )
    CCTV_seoul['최근증가율'] = ( CCTV_seoul['2014년'] + CCTV_seoul['2015년'] + CCTV_seoul['2016년'] ) / CCTV_seoul['2013년도 이전'] * 100

    pop_Seoul = pd.read_excel('../data/01.population_in_Seoul.xls' , header = 2 , usecols = 'B,D,G,J,N' , encoding='utf-8')            
    pop_Seoul.rename( columns = { pop_Seoul.columns[0] : '구별', pop_Seoul.columns[1] : '인구수', pop_Seoul.columns[2] : '한국인', pop_Seoul.columns[3] : '외국인', pop_Seoul.columns[4] : '고령자' } , inplace = True )



    pop_Seoul['구별'].unique()
    #  구별 데이터에 nan 데이터가 들어있음 : nan = null => 삭제필요
    # nan에 해당하는 행 전체 삭제 : 구별값이 nan인 행의 인덱스 확인
    # nan을 확인하는 함수 -  df명['필드명'].isnull()
    # 해당 행을 출력해서 확인

    # 데이터프레임명[필드명 또는 조건식] : 데이터 행에 접근
    pop_Seoul[ pop_Seoul['구별'].isnull() ]
    # 결과 : 26

    pop_Seoul.drop(0 , inplace = True )
    pop_Seoul.drop( [26] , inplace = True ) # 한번 실행하면 다시 실행되지 않도록 하기
    pop_Seoul.head(10)


    # CCTV_Seoul과 pop_Seoul 병합코드
    # 공통컬럼인 '구별' 컬럼으로 조인
    # 양쪽 모두 25개의 구로 이루어져있음
    # merge 함수
    # pd.merge( 조인할df1, 조인할 df2, on='공통필드' )

    data_result = pd.merge( CCTV_seoul, pop_Seoul , on='구별' )
    data_result.head()

    # 사용하지 않을 컬럼 삭제
    # CCTV의 소계, 최근 증가율을 제외한 년도관련 data 는 삭제

    del data_result['2013년도 이전']
    del data_result['2014년']
    del data_result['2015년']
    del data_result['2016년']

    data_result.head()

    # 그래프 그릴때 축데이터를 쉽게 지정하기 위해서 행 인덱스를 구별로 변경
    # 행인덱스 지정 함수 : set_index('지정렬 이름' , inplace=True )

    data_result.set_index( '구별' , inplace = True )

    data_result['고령자비율'] = data_result['고령자'] / data_result['인구수'] * 100
    data_result['외국인비율'] = data_result['외국인'] / data_result['인구수'] * 100

    # 다수의 데이터 중 상관관계가 가장 큰 데이터를 비교
    # 인구와 관련된 각 필드와 CCTV 소계와의 상관 계수를 파악한 후 의미있는 그래프 표현

    # 상관계수 : 두 변수의 관련성을 확인하는 방법
    # 절대값이 클수록 두 데이터는 관련이 있다고 판단
    # 절대값을 기준으로 0.1 이하 무시
    # 0.3 이하 약한 상관 관계
    # 0.7 이상 강한 상관 관계

    # 상관관계 파악 변수 (컬럼)
    # CCTV총대수와 인구수
    # CCTV총대수와 고령자 비율
    # CCTV총대수와 외국인 비율

    # 계산 함수 numpy 패키지 corrcoef( data1, data2 )

    np.corrcoef( data_result['소계'] , data_result['인구수'] ) # CCTV총대수와 인구수 : 약한 상관관계 - 그래프 표현
    np.corrcoef( data_result['소계'] , data_result['고령자비율'] ) # CCTV총대수와 고령자비율 : 약한 음의 상관관계 - 그래프 표현
    np.corrcoef( data_result['소계'] , data_result['외국인비율'] ) # CCTV총대수와 외국인비율 : 약한 음의 상관관계 - 그래프 표현
    # 파이썬의 그래프 그리는 모듈(패키지) : matplotlib.pyplot
    # 서브 패키지 pyplot 이용

    import matplotlib.pyplot as plt

    # 그래프는 새창이 뜨면서 드로잉을 하는데 
    # 새창 띄우지 말고 소스코드 안에서 드로잉 하라는 명령 입력 
    %matplotlib inline

    #한글문제 발생
    #matplotlib의 기본폰트에서 한글지원 폰트가 없음
    #패키지의 폰트를 추가하고 사용
    #윈도우 용
    import platform

    from matplotlib import font_manager, rc
    plt.rcParams['axes.unicode_minus'] = False

    if platform.system() == 'Darwin':  # 맥OS 
        rc('font', family='AppleGothic')
    elif platform.system() == 'Windows':  # 윈도우
        path = "c:/Windows/Fonts/malgun.ttf"
        font_name = font_manager.FontProperties(fname=path).get_name()
        rc('font', family=font_name)
    else:
        print('Unknown system...  sorry~~~')
    # 구별 CCTV 설치대수를 그래프로 표현
    # 수평 막대 그래프 
    # 전체 그림 크기( 그림 영역 설정 plt.figure(figsize=(10,10)) )

    plt.figure( figsize=( 10 , 10 ) )
    # 그래프 그리기 plot(kind=그래프종류값, grid = T/F (격자무늬) )

    data_result['소계'].plot( kind='barh' , grid = True )

    # 구별 CCTV 설치대수 그래프
    # 수평막대 그래프 - 정렬해서 그래프 출력 
    s = data_result['소계'].sort_values()
    plt.figure( figsize = (10 , 10) )
    plt.barh( s.index, s )
    plt.grid()
    plt.show()
    ```

    + 새로 추가 되는 코드
        + CCTV 절대수와 인구수간의 상관관계를 확인 했을 때 가장 상관이 높게 나타난 변수는 소계와 인구수 간의 관계였음
        + 인구수 대비 cctv 가 많이 설치되어있는 지역을 찾아볼 것

        ``` C
        # 데이터 확인 : data_result => cctv 데이터와 인구수 데이터를 병합해놓은 df
        # 인구수 대비 cctv 설치비율 변수 생성
        data_result['cctv비율'] = data_result['소계'] / data_result['인구수'] * 100
        ```
        + CCTV 비율이 높은 지역순으로 그래프 작성

        ``` C 
        data_result['cctv비율'].sort_values().plot( kind='barh' , grid = True, figsize = (10,10) )
        plt.show()
        ```

        + 인구수 대비 cctv 대수는 용산구와 종로구가 강남, 양천에 비해서 월등히 높다.
        + 용산구와 종로구의 특징 : 주거지역이 적고, 유동인구가 많은 대표적인 지역
        + 주거지역보다 상업지역에 cctv 설치 빈도가 높다는것을 알 수 있음.

        ``` C
        # 인구수와 cctv 절대 설치대수를 이용해서 분산그래프 그리기
        # 분산그래프 함수 : scatter() 사용
        # 문법 : scatter( x축데이터 , y축데이터 , 마커크기 n )

        plt.figure( figsize=(6,6) )
        plt.scatter( data_result['인구수'] , data_result['소계'] , s = 50 )
        plt.xlabel( '인구수' )
        plt.ylabel( 'CCTV' )
        plt.grid()
        plt.show()
        ``` 

        + 데이터(cctv대수와 인구수)를 대표하는 직선을 하나 그려서
        + 대표값보다 높은 곳에 위치하는 구와 낮은곳에 위치하는 구 표시
        + 인구수와 cctv는 양의 상관 관계를 갖는다. 1차 함수 방정식을 이용해서 직선을 그려봄

        ``` C
        # 최소오차 직선식
        # polyfit( x,y,n ) : y 에 대한 x 의 그래프에서 오차가 가장 적은 n차 방정식의 계수 반환
        # cctv 대수에 대한 인구수의 그래프를 그릴때 필요한 1차 방정식 계수를 구해보자.

        fp1 = np.polyfit( data_result['인구수'] , data_result['소계'] , 1 )
        # 결과 : array( [ 1.30916415e-03 , 6.45066497e+02  ] )
        # 지수 표현 
        ```

        + 인구가 10만일 때, 적절한 CCTV 대수는 얼마인가?
        
        ``` C
        # y = 0.001309146415 * 100000 + 645.066497
        # 인구별 적절한 cctv 대수 값을 계산하기 위한 인구 데이터 생성
        # 각 구별 인구수를 확인 했을 떄 최소값과 최대값은 얼마인가?
        data_result['인구수']
        
        # 10만부터 70만 사이에 동리 간격 100개의 수를 생성
        # linspace( 최소값 , 최대값 , 발생할 수의 계수 )
        fx = np.linspace( 100000 , 700000 , 100 )
        
        # fp1 : 방정식 계수
        # fx : 방정식에 사용할  x값
        # 방정식 함수 생성 - poly1d( 방정시계수 ) y = 0.0013 ...
        f1 = np.poly1d( fp1 )
        # f1 은 함수로 생성됨 : f1(x값) 으로 사용 y 값이 나옴
        f1(fx)
        ```

        + 인구수 대비 cctv 대수 분산그래프를 그리고 대표직선 그리기
        + 대표직선을 위한 data 는 x값(인구수)  : fx 변수 값(cctv) : f1(fx)

        ``` C
        plt.figure( figsize = (6 , 6) )
        plt.scatter( data_result['인구수'] , data_result['소계'] , s = 50 )
        # 대표직선 그래프 그리기
        plt.plot( fx , f1(fx) , ls = 'dashed' , lw = 3 , color = 'g' )
        # ls : 선스타일 , lw : 선 두께, color : 선 색상

        plt.xlabel('인구수')
        plt.ylabel('CCTV')
        pl t.grid()
        plt.show()
        ```

        + 직선의 의미는 인구수가 40000일때 적정 cctv 대수는 1200대 정도여야
        + 직선보다 위쪽은 일반보다 많은 지역
        + 직선보다 아래은 일반보다 적게 설치된 지역
        + 조금 더 설득력 있는 자료 만들기
        + 직선과 멀어 질수록 마커의 색상을 다르게 표현
        + 직선과 멀리 있는 상위 10를 선택해서 구 이름을 표시

        ``` C
        # 구별 인구수 배디 cctv 오차 계산
        # 있어야 할 대수보다 얼마나 많고 지를 계산
        data_result['소계'] - f1( data_result['인구수'] )
        
        # 위에서 계산한 오차를 절대값으로 변환 후 상위 10개 구 확인
        # abs(값) : 절대값을 반환

        data_result['오차'] = np.abs( data_result['소계'] - f1(data_result['인구수']) )
        data_result.head()

        # 오차가 큰 상위 10개 구만 추출 - 그래프에 구 이름을 표시하기 위해서
        df_sort = data_result.sort_values( by='오차' , ascending = False )
        df_sort.head(10)
        ```

        + 오차가 큰 상위 10개 도시에 구 이름 표시
        + 그래프에 글자 출력하는 함수
        + plt.text( x , y , txt , fontsize )
        + 마커보다 약간 오른쪽 아래에 출력되도록 좌표 변경 후 출력

        ``` C
        # for n in range(10) :
        #     plt.text(
        #     df_sort['인구수'][n] * 1.02,
        #     df_sort['소계'][n] * 0.98,
        #     df_sort.index[n],
        #     fontsize = 15
        #     )

        plt.figure( figsize = (10,10) )
        plt.scatter( data_result['인구수'] , data_result['소계'] , s = 50 , c = data_result['오차'] )
        plt.plot( fx , f1(fx) , ls='dashed' , lw = 3 , color = 'g' )

        # text 표현
        for n in range(10) :
            plt.text( df_sort['인구수'][n] * 1.02 , df_sort['소계'][n] * 0.98 , df_sort.index[n] , fontsize = 15 )

        plt.xlabel('인구수')
        plt.ylabel('CCTV')
        plt.colorbar( label='오차' )
        plt.grid()

        plt.show()
        ```
    + csv 파일로 데이터프레임 저장하기
    ``` C
    # df.to_csv( path_filename , encoding = 'utf-8' )
    data_result.to_csv( './01_cctv_result.csv' , encoding='utf-8' ) 
    ```

+ 교재2. 서울시 범죄 데이터 분석
    + 강남 3구는 체감만큼 안전한가?
        + 사용데이터 : 서울시 관서별 범죄 발생 검거율 현황
        + 서울시 공공데이터 수집이 가능 (매년 형식이 약간씩 변경됨)
        + 범죄(5대 범죄) - 살인, 강도, 강간, 절도, 폭력
        + 관서별 : 경찰서별
        + 구글 지도 데이터를 이용해서 경찰서 주소 얻어오는 방법
        
        ``` C 

        # 필수 패키지 import 및 data 가져오기
        import pandas as pd
        import numpy as np

        # 주피터 노트북에서 출력 모두를 표시하는 코드
        from IPython.core.interactiveshell import InteractiveShell
        InteractiveShell.ast_node_interactivity="all"

        # data 가져오기
        crime_anal_police = pd.read_csv( '../data/02. crime_in_Seoul.csv' , thousand = ',' , encoding = 'euc-kr' )
        crime_anal_police.head()
        type( crime_anal_police['폭력 검거'][0] ) # 천단위 구분기호가 있어서 문자열로 읽어옴
        # read_csv 할때 thousand = ',' 옵션 추가
        ```

        + 데이터가 경찰서별로 되어있음 -> 구별로 데이터 변경
        + 경찰서 명을 이용해서 경찰서 주소를 구글로 부터 얻어오는 작업을 진행
        + 구글 맵을 사용하기 위한 패키지를 설치
        + 아나콘다 명령어를 이용해서 아래 명령 실행

        ``` C
        pip install googlemaps
        ```

        + 구글 임포트 코드

        ``` C
        import googlemaps

        gmapsKey = 'AIzaSyB-xZ-IKxYvd7GrvISS0M2GHZFkvukiSrI';
        gmaps = googlemaps.Client( key = gmapskey )
        ```

        + 서울 중부 경찰서의 정보 구글로부터 얻어오기

        ``` C
        tmp = gmaps.geocode( '서울중부경찰서' , language='ko' )
        type(tmp[0])
        tmp[0]
        ```
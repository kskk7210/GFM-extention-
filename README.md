# GFM 확장 구문에 관한 가장 기초적인 가이드  
## GFM 이란  
GFM은 GitHub Flavored Markdown의 약자로 GitHub에 지원되는 Markdown을 뜻한다. 

## GFM Extention 목록
1. Table (표)  
2. Task list items (작업 목록 항목)  
3. Strikethrough (취소선)  
4. Autolinks (자동 링크)  
5. Disallowed Raw HTML (허용되지 않는 원래의 HTML)  


### 1. Table (표)
- 표는 행과 열이 있는 데이터 배열로 헤더를 분리해야한다. 헤더는 \- (하이픈)으로 분리되며 표를 이루는 각 셀은 \| (파이프)로 구분된다.
- \: (콜론)을 통해 각 셀의 텍스트를 좌, 우, 가운데로 정렬할 수 있다.

        | Header | Title | Subject |
        |--------|-------|---------|
        | story  | Book  | This    |
        | text1  | text2 | text3   |
    
    
        | Header | Title | Subject |
        | :---   | :---: |    ---: |
        | left   | center| right   |
        
        위의 표는 단순히 헤더와 셀을 분리한 것이고 아래표는 콜론을 이용하여 정렬을 표현한 것이다.
아래는 위의 코드를 구현하여 나타낸 표이다.

| Header | Title | Subject |
|--------|-------|---------|
| story  | Book  | This    |
| text1  | text2 | text3   |
    
    
| Header | Title | Subject |
| :---   | :---: |    ---: |
| left   | center| right   |

- 텍스트가 없는 셀이 존재하는 표를 만들어낼 수도 있다.

        | Header | Title | Subject |
        |--------|-------|---------|
        | story  | Book  | 
        | text1  | text2 | text3   |
        
 구현 결과는 아래와 같다.
        
| Header | Title | Subject |
|--------|-------|---------|
| story  | Book  | 
| text1  | text2 | text3   |

- 표를 만들 때는 주의해야할 점이 있다.
        - 꼭 헤더의 수에 맞춰 \|(파이프)와 \- (하이픈)을 이용하여 헤더의 셀을 생성해줘야 한다.
        - 파이프 안에 텍스트를 쓰지 않아도 그 전에 있는 (바로 위에 있는) 텍스트가 셀 내부에 쓰여있다면 밑에 오는 텍스트도 위의 셀 자리에 맞춰 정렬된다.
                
        
___
### 2. Task list items (작업 목록 항목)
- 작업 목록을 만들어 Check list로 사용할 수 있도록 확인란을 만들 수도 있다. 
- 대괄호 \[\]와 하이픈 \-을 사용하여 생성 가능하다.

        - [X] code  
        - [X] rendering  
            - [ ] simulation  
        - [ ] upload  
        확인란 선택은 대괄호에 공백 대신 가위표 [X]를 추가하면 된다.
        작업목록 또한 탭이나 공백을 통해 중첩하여 표현하는 것이 가능하다.
아래는 작업목록에 대한 구현 결과이다.

- [X] code  
- [X] rendering  
    - [ ] simulation  
- [ ] upload  


___
### 3. Strikethrough (취소선) 
- 취소선은 \~ (물결표시)를 이용하여 나타낼 수 있다.

        취소하고 싶은 구나 절 앞뒤로 두개의 물결표시를 사용하여 취소선을 표현할 수 있다.
        I think I need ~~more~~ practice.
아래에 취소선의 실행결과를 볼 수 있다.

I think I need ~~more~~ practice.


___
### 4. Autolinks (자동 링크)
- 링크의 경우 \<\> 꺾쇠 괄호를 통해 표시할 수 있지만 www\. 다음에 오는 도메인을 자동으로 인식할 수 있으며 이때는 도메인이 유효한 도메인이어야 한다.

|               code block | consequnce    |
|--------------------------|---------------|
|       <www.naver.com>    |<www.naver.com>|
|        www.never.com     | www.naver.com |
        
- 링크에 관하여 살펴야할 점이 있다.  
        - 유효한 메인 뒤에 공백이 아닌 0이상의 문자가 올 수 있다.  
        - 링크 뒤에 \., \?, \! 등의 문자가 올 수 있으며 이 문자들이 링크 내부에 포함되더라도 자동 링크의 일부로 보지는 않는다.   
        - \> 가 링크 뒤에 오면 그 즉시 자동링크가 종료된다.  
        
        
___
### 5. Disallowed Raw HTML (허용되지 않는 원래의 HTML)  
- GFM이 HTML 출력을 렌더링 할 때 다음과 같은 태그가 필터링 된다.

        <title>
        <textarea>
        <style>
        <xmp>
        <iframe>
        <noembed>
        <noframes>
        <script>
        <plaintext>
        
        
___

#### 참고한 문서 
<https://github.github.com/gfm/#disallowed-raw-html-extension->  
<https://www.markdownguide.org/>  
<https://guides.github.com/features/mastering-markdown/>  

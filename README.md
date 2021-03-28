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
    | text1  | text2 | tect3   |
    
    
    | Header | Title | Subject |
    | :---   | :---: |    ---: |
    | left   | center| right   |

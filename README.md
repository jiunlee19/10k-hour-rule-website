# 1만 시간의 법칙

1만 시간의 법칙 웹사이트 제작  
https://paullab.co.kr/10000hours.html 클론 코딩

### 1. 프로젝트 초기 설정

-   [x] 작업 폴더 구조 생성 (HTML, CSS 등)
    .   
    |-- css   
    | |-- reset.css   
    | `-- index.css   
    |-- img   
    `-- index.html   
    
-   [x] 피그마 파일 검토 및 디자인 요소 다운로드
-   [x] 필요한 이미지, 아이콘, 폰트 등의 자산 추출/준비
-   [x] 기본 HTML 파일 생성
-   [x] 기본 CSS 파일 생성 (Reset CSS 포함)

### 2. 시멘틱 마크업 계획

-   [x] 페이지 구조 분석 및 적절한 시멘틱 태그 선정 (header, nav, main, section, article, footer 등)
-   [x] 접근성을 고려한 태그 사용 계획

### 3. 반응형 웹 구현 계획

-   [ ] 브레이크포인트 설정 (모바일, 데스크톱)
    - 0-599dp : 모바일
    - 600dp~ : 데스크톱 
-   [x] 모바일 퍼스트 vs 데스크톱 퍼스트 접근 방식 결정
    결정. 모바일 퍼스트
    이유. 모바일 사용자수가 데스크탑 사용자수를 넘어섰다.   
         <1만시간의법칙> 웹페이지는 다량의 정보제공이나 복잡한 기능을 제공하지 않고,   
         그 내용 또한 빠르게 소비되기에 적합한 소재이기 때문에 모바일 퍼스트 방식으로 개발하기로 결정함.
-   [x] 이미지 요소의 반응형 처리 방법 계획
    - 픽셀(px) 대신 상대적인 단위(%, em, rem 등)를 사용하여 레이아웃을 구성
    - CSS `width:100%`와 `height:atuo;`사용하여,
    이미지를 포함하는 부모 요소의 너비에 맞춰 이미지가 늘어나도록 설정
    - `<picture>` - `source` 요소를 사용하여 조건에 맞는 이미지를 지정하고, `img` 요소에 기본 이미지를 설정합니다.
        
        ```html
        <picture>
            <source media="(max-width: 767px)" srcset="small-image.jpg">
            <source media="(max-width: 1023px)" srcset="medium-image.jpg">
            <img src="large-image.jpg" alt="">
        </picture>
        ```
        
    - <img> object-fit 속성을 사용하여 이미지 영역에 꽉 차도록 채우거나, 잘리지 않도록 조절할 수 있다.
    - <img> srcset 속성을 사용하여 브라우저가 네트워크, 메모리, 성능, 시간 등을 고려하여 최적의 이미지를 선택하도록 한다.
        ```html
        <img srcset="
            /images/html-css/chapter16/05.png,
            /images/html-css/chapter16/06.png 2x,
            /images/html-css/chapter16/07.png 4x
            "
        src="/images/html-css/chapter16/05.png"
        alt="다람쥐 캐릭터 칠리"
        />
        ```

### 4. 구현 시작

-   [ ] HTML 기본 구조 마크업 작성
-   [ ] 기본 스타일 및 레이아웃 CSS 작성
-   [ ] 데스크톱 버전 스타일링

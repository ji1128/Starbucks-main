# starbucks-main

## Favicon(파비콘, favorites icon)
웹페이지를 나타내는 아이콘, 웹페이지의 로고를 설정합니다. <br>
대부분의 경우 루트 경로에 favicon.ico 파일을 위치하면 자동으로<br>
로딩하기 때문에 <link /> 를 작성할 필요가 없습니다.<br>
favicon.png 파일을 사용하려면 다음과 같이 <link />를 작성하세요.
>html
```html
<link rel="icon" href="favicon.png">
<link rel="shortcut icon" href="favicon.ico"> 
```

## Reset.css
각 브라우저의 기본 스타일을 초기화합니다. <br>
[jsdelivr 이동](https://www.jsdelivr.com/package/npm/the-new-css-reset)
>html
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/the-new-css-reset@1.5.1/css/reset.min.css">
```

## Fonts
페이지에서 사용할 '나눔바른고딕' 폰트를 지정합니다
>css
```css
@font-face {
    font-family: 'NanumBarunGothic';
    font-style: normal;
    font-weight: 400;
    src: url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWeb.eot');
    src: url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWeb.eot?#iefix') format('embedded-opentype'), url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWeb.woff') format('woff'), url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWeb.ttf') format('truetype');
}

@font-face {
    font-family: 'NanumBarunGothic';
    font-style: normal;
    font-weight: 700;
    src: url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebBold.eot');
    src: url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebBold.eot?#iefix') format('embedded-opentype'), url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebBold.woff') format('woff'), url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebBold.ttf') format('truetype')
}

@font-face {
    font-family: 'NanumBarunGothic';
    font-style: normal;
    font-weight: 300;
    src: url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebLight.eot');
    src: url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebLight.eot?#iefix') format('embedded-opentype'), url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebLight.woff') format('woff'), url('//cdn.jsdelivr.net/font-nanumlight/1.0/NanumBarunGothicWebLight.ttf') format('truetype');
}

body{font-family: 'NanumBarunGothic', sans-serif;}
```
main.css보다 먼저 읽혀 들어갈 수 있도록 위에다가 선언한다.

## Google Material Icons
main.css보다 먼저 읽혀 들어갈 수 있도록 위에다가 선언한다.
>html
```html
<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons" />
```

사용할 부분에는 다음과 같이 사용한다.
```html
<span class="material-icons">search</span>
```

## lodash를 활용하여 scroll함수 제어하기
scroll이벤트가 무한대로 실행돼서 사이트가 무거워지는 것 방지 할 수 있는 플러그인인 lodash를 설치 <br>
[lodash 이동](https://cdnjs.com/libraries/lodash.js)
>html
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.21/lodash.min.js"
        integrity="sha512-WFN04846sdKMIP5LKNphMaWzU7YpMyCU245etK3g/2ARYbPK9Ub18eG+ljU96qKRCWh+quCY7yefSmlkQw1ANQ=="
        crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```
lodash는 main.js 위에 선언한다.

## gsap을 이용해 애니메이션 효과주기
GSAP(The GreenSock Animation Platform)은 자바스크립트로 제어하는 타임라인 기반의 애니메이션 라이브러리입니다. ScrollToPlugin은 스크롤 애니메이션을 지원하는 GSAP 플러그인입니다. <br>
[gsap 이동](https://cdnjs.com/libraries/gsap)
>html
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/gsap.min.js" integrity="sha512-IQLehpLoVS4fNzl7IfH8Iowfm5+RiMGtHykgZJl9AWMgqx0AmJ6cRWcB+GaGVtIsnC4voMfm8f2vwtY+6oPjpQ==" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/ScrollToPlugin.min.js" integrity="sha512-nTHzMQK7lwWt8nL4KF6DhwLHluv6dVq/hNnj2PBN0xMl2KaMm1PM02csx57mmToPAodHmPsipoERRNn4pG7f+Q==" crossorigin="anonymous"></script>
```

## ScrollMagic
ScrollMagic은 스크롤과 요소의 상호 작용을 위한 자바스크립트 라이브러리입니다. <br>
대표적으로 어떤 요소가 현재 화면에 보이는 상태인지를 확인할 때 사용합니다.
>html
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/ScrollMagic.min.js"></script>
```
>js
```js
spyEls.forEach(function (spyEl) {
    new ScrollMagic.Scene({ // 감시할 장면(Scene)을 추가
            triggerElement: spyEl, //보여질 부분 감지할 요소 지정
            triggerHook: 0.8, //화면의 80% 지점에서 보여짐 여부 감시
        })
        //토글 할 요소 생성 및 제거
        //.setClassToggle(토글 할 요소, "넣었다 뺐다 할 class 이름 생성")
        .setClassToggle(spyEl, "show") // 요소가 화면에 보이면 show 클래스 추가
        .addTo(new ScrollMagic.Controller()); // 컨트롤러에 장면을 할당(필수!)
});
```

## Swiper Slider
[Swiper Slider 이동](https://swiperjs.com/)

>css
```css
<link rel="stylesheet" href="https://unpkg.com/swiper@8/swiper-bundle.min.css" />
<script src="https://unpkg.com/swiper@8/swiper-bundle.min.js"></script>
```
>html
```html
<!-- Slider main container -->
<div class="swiper">
  <!-- Additional required wrapper -->
  <div class="swiper-wrapper">
    <!-- Slides -->
    <div class="swiper-slide">Slide 1</div>
    <div class="swiper-slide">Slide 2</div>
    <div class="swiper-slide">Slide 3</div>
    ...
  </div>
  <!-- If we need pagination -->
  <div class="swiper-pagination"></div>

  <!-- If we need navigation buttons -->
  <div class="swiper-button-prev"></div>
  <div class="swiper-button-next"></div>

  <!-- If we need scrollbar -->
  <div class="swiper-scrollbar"></div>
</div>
```
>swiper option
>>js
```js
new Swiper('변경 .swiper', {
    direction: 'horizontal', //방향
    loop: true, //무한반복
    autoplay : true, //자동시작
    slidesPerView: 4, //한 번에 보여지는 슬라이드 개수
    spaceBetween: 30, //슬라이드와 슬라이드 간격
    navigation : {
        prevEl : "변경 .swiper-prev",
        nextEl : "변경 .swiper-next"
    },
    breakpoints: { //반응형 조건 속성
    320: { //320 이상일 경우
      slidesPerView: 1, //레이아웃 1열
    },
    768: {
      slidesPerView: 3, //레이아웃 3열
    },
    1024: {
      slidesPerView: 4, //레이아웃 4열
    },
  }
});
```








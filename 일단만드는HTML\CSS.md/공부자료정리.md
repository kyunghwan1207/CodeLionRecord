# 일단만드는 HTML/CSS

### HTML파일 기본구조
![](https://imagedelivery.net/v7-TZByhOiJbNM9RaUdzSA/a533f8b5-0c70-4add-36d2-8066554ef100/public)

### 박스 구조 및 명칭
![](https://imagedelivery.net/v7-TZByhOiJbNM9RaUdzSA/ff0541de-37df-4aa9-8639-17146aad1000/public)

# CSS

### font 스타일 모든문서에 적용하기
```css
@import url('https://fonts.googleapis.com/css?family=Montserrat:100,200,300,400,500,600,700,800&display=swap');

* {
    font-family: 'Montserrat';
}
```

### css적용시:
tag(그대로), class(.)

### **border: <두께> <방법> <색깔>;**

ex. 20px solid black

### **box-shadow: <x축> <y축> <그림자 흐림정도(blur)> <그림자 퍼짐정도(spread)>**

ex. 0px 1px 20px 0px rgba(0, 0, 0, 0, 0.1); // 0: black ~ 255: white / 0: 탁한색 ~ 1: 투명한 색

### p태그 한 줄로 정렬하기 in codelion.css

```css
.float-wrap {
    overflow: hidden;
}

.title-text {
    float: left;
}
.year-text{
    float: right;
}
```

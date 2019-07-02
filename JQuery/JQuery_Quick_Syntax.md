# JQuery Cú pháp cơ bản

- [JQuery Cú pháp cơ bản](#JQuery-C%C3%BA-ph%C3%A1p-c%C6%A1-b%E1%BA%A3n)
  - [Chạy sau khi tải xong trang](#Ch%E1%BA%A1y-sau-khi-t%E1%BA%A3i-xong-trang)
  - [Selector - chọn tag](#Selector---ch%E1%BB%8Dn-tag)
    - [Selector with index](#Selector-with-index)
    - [Selector with child](#Selector-with-child)
    - [Selector with Content](#Selector-with-Content)
    - [Selector with form](#Selector-with-form)
    - [Đối với selector truyền Index:](#%C4%90%E1%BB%91i-v%E1%BB%9Bi-selector-truy%E1%BB%81n-Index)
  - [JQUERY ATTRIBUTES](#JQUERY-ATTRIBUTES)
    - [_Style - Class](#Style---Class)
    - [_Element](#Element)
  - [DOM TRAVERSING](#DOM-TRAVERSING)
  - [CSS SELECTOR METHOD](#CSS-SELECTOR-METHOD)
  - [EVEN HANDLING](#EVEN-HANDLING)
    - [_Add event](#Add-event)
    - [_Remove Event](#Remove-Event)
    - [_Evens Method](#Evens-Method)
  - [AJAX - REQUEST Data NOT LOAD Page](#AJAX---REQUEST-Data-NOT-LOAD-Page)

## Chạy sau khi tải xong trang

```js
// Js thuần
window.onload = function(){
    //nội dung bên trong
};

// JQuery
$(document).ready(function(){
    //nội dung bên trong
});
```

## Selector - chọn tag

```js
// JS thuần
var h1 = document.getElementById('title');

// JQuery
var h1 = $('#title'); //select id
$(".class") //select class
$('h1') //select all tag name h1
$('*') //select all tag
$("p ul") //select all ul is child of p
$('div#id1') //select div tag has id1
$('div.class1.class2') //select div has class1 AND class2
$('h1,h2,h3') //select multiple tag
$('div > h1') //select h1 is a child div, con ngay phía sau.
$("p+ul") //select ul under p
$("p~ul") //select all ul under p
//Cú pháp
$('selector:filter[attribute]')
$( "selector:animated" ) //tag đang chạy animation
```

### Selector with index

```js
$( "selector:eq( 2 )" ) //chọn tag thứ 2
$( "selector:even") //chọn tag lẻ
:odd //tag chẵn
:first //tag đầu
:last
:root //cấp cao nhất
:gt(2) //tag có stt >2
:lt(2) //tag có stt <2
:focus //tag chuột ở trên
:lang(vi-vn) //tag có Thuộc tính ngôn ngữ vn
:not(.active) //tag ko có filter, ko có class active
```

### Selector with child

```js
:first-child //lấy Thẻ con đầu tiên
:last-child
:nth-child(2) //lấy thẻ con thứ 2
:nth-last-child(2) //lấy thẻ con thứ 2 ,từ dưới lên
:only-child //lấy thẻ con duy nhất
```

### Selector with Content

```js
selector:contains('nghia') //tag nội dung có chứa 'nghia'
:emty //tag ko có nội dung
:has(element) //tag nội dung bên trong chứa element
:parent //thẻ cha đầu tiên của selector
```

### Selector with form

```js
:button //type là button
:checkbox :file :image :input :password :radio :reset :submit :text
:checked //trạng thái checked, selected
:disabled :enabled :selected :hidden :visible
:focus //đang chứa con trỏ
```

### Đối với selector truyền Index:

```js
even: Tìm theo số lẻ*.
odd: Tìm theo số chẵn*.
2n+1: Các số 1, 3, 5, 7, ...*.
3n + 1: Các số 1, 4, 7, ...*.
3n: Các số 3, 6, 9, ...
```

## JQUERY ATTRIBUTES

```js
<img id="myImage" src="image.gif" alt="An image" class="someClass" title="This is an image"/>

//_Get Attrubite
var title = $('#myImage').attr('title');

//_Set Attribute
.attr("src", "/images/jquery.jpg");
.attr({
	src: "/images/jquery.jpg",
	title: "jQuery"
});
.removeAttr("src");
.prop('name') //kt có attribute
```

### _Style - Class

```js
.addClass("red");
.hasClass("red");
.removeClass("red");
.toggleClass("red"); //ko->có, có->ko
```

### _Element

```js
.html() //get tag's content, get tag inside
.html('content') //set content
.text() //like html, nót tag inside
.text('content') //set content, not tag inside
.val(); //get Value in Input,  Select, Option tag
.val("text")
```

## DOM TRAVERSING

```js
.eq(2) //get element 2nd
$("li").filter(".middle") //get li has middle class
$("li").filter(function (index) {...}) //Lọc thành phần trong các thành phần giống nhau
$("p").find("span") //get span inside p
.is(":first-child") //check selector is a first child
.map(function (element, index) {
return replace_element;
}); //Do for all element, return replace Element
.each(function(index){ ... }); //Do forEach all element, get element = $(this)
.not('selector') //select element not selector
.slice(fromIndex, toIndex) //select form Index to Index element
$(".top").add(".middle") //select Top & Middle
.childen("selector") //get children has selector
.contents() //get all childen node
.find("selector") //find selector
.parent() //select parent tag
...
```

## CSS SELECTOR METHOD

```js
$("li").eq(2).css({"color":"red", "background-color":"green"}); //set css
```

## EVEN HANDLING

### _Add event

```js
$('div').bind('click', function( event ){
	alert('Hi there!');
});
selector.bind( eventType[, eventData], handler)
```

### _Remove Event

```js
selector.unbind('eventType')
```

### _Evens Method

```js
bind() // Bổ sung sự kiện vào đối tượng
blur() // Xảy ra khi ra khỏi đối tượng
change() // Xảy ra khi giá trị bị thay đổi
click() // Xảy ra khi click vào đối tượng
contextmenu() // Xảy ra khi click chuột phải
dbcclick() // Xảy ra click double chuột
delegate() // Bổ sung sự kiện vào đối tượng cả trước và sau khi thêm bằng Javascript
die() // Xóa bỏ sự kiện ra khỏi đối tượng
error() // Xay ra khi xuất hiện lỗi trên đối tượng
focus() // Xảy ra khi focus vào đốit tượng (con trỏ chuột đang xử lý tại đối tượng)
focusin() // Giống focus nhưng bổ sung thêm điều kiện là sự kiện đang ở trạng thái mớivào
focusout() // Giống focus nhưn bổ sung thêm điều kiện là sự kiện đang ở trạng tháidừng
hover() // Xảy ra khi hover chuột vào đối tượng
keydown() // Xảy ra khi bàn phím nhấn xuống
keypress() // Xảy ra khi bàn phím nhấn xuống
keyup() // Xảy ra khi nhả bàn phím
on() // Bổ sung sự kiện vào đối tượng
load() // Xảy ra khi đối tượng bắt đầu load
mousedown() // Xảy ra khi nhấn chuột trái xuống
mouseup() // Xảy ra khi nhả chuột trái
ramouseenter() // Xảy ra khi con trỏ chuột đi vào phạm vi của đối tượng
mouseleave() // Xảy ra khi con trỏ chuột đi ra ngoài phạm vi của đối tượng
mousemove() // Xảy ra khi con trỏ chuột đang di chuyểnbên trong đối tượng
mouseover() // Xảy ra một lần duy nhất khi con trỏ chuột bắt đầu đi vào phạm vi đối tượng
mouseout() // Xảy ra một lần duy nhấtkhi con trỏ chuột đi ra ngoài phạm vi đối tượng
ready() // Xảy ra khi browser đã load xong
resize() //  Xảy ra khi resize 
browserscroll() // Xảy ra khi kéo thanh cuộn
submit() // Xảy ra khi form được 
submittoggle() // Xảy ra khi click vào đối tượng
```

## AJAX - REQUEST Data NOT LOAD Page

```js
$(document).ready(function() {
    $('#load-du-lieu').click(function(e) {
        e.preventDefault();
        
        //GET
        $.get('vidu1.html', 
            function(ketqua) {
                $('#noidung').html(ketqua);
                $('#noidung').html(
                    $('#chuoi-can-lay').html()
                );
            });
        });
        
        //POST
        $.post('vidu2.php', {
            a: "content abc",                
            b: "content bcd"           
        },function(ketqua) {
            $('#noidung').html(ketqua); 
        });
        
        //Ajax Custom
        $.ajax({
            url: 'vidu2.php',         
            type: 'POST',                
            dataType: 'html',                
            data: {
                a: "content abc",            
                b: "content bcd"       
            }            
        }).done(function(ketqua) {
            $('#noidung').html(ketqua);    
        });
    });
});
```

---
**END**
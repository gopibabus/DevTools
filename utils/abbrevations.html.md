```
<!-- BASIC TAGS, CLASSES & IDS -->

<!-- div -->
<div></div>

<!-- h1 -->
<h1></h1>

<!-- Common Shortcuts bq hdr ftr btn -->
<blockquote></blockquote>
<header></header>
<footer></footer>

<!-- h1.myheading -->
<h1 class="myheading"></h1>

<!-- div.myclass OR .myclass -->
<div class="myclass"></div>
<div class="myclass"></div>

<!-- .class1.class2 -->
<div class="class class2"></div>

<!-- div#myid or #myid -->
<div id="myid"></div>
<div id="myid"></div>

<!-- #myid.myclass -->
<div id="myid" class="myclass"></div>

<!-- ADDING CONTENT {} -->
<!-- h1{My Title} -->
<h1>This is heading</h1>

<!-- h1.red{My Red Title} -->
<h1 class="red">This is red title</h1>

<!-- NESTING -->

<!-- div>ul>li -->
<div>
    <ul>
        <li></li>
    </ul>
</div>

<!-- div>ul>li{List Item 1} -->
<div>
    <ul>
        <li>This is list item</li>
    </ul>
</div>

<!-- MULTIPLICATION * -->

<!-- ul#navigation>li*5>{List Item $} -->
<ul id="navigation">
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
    <li>List item 4</li>
    <li>List item 5</li>
</ul>

<!-- SIBLINGS + -->

<!-- div+ul+li -->
<div></div>
<ul></ul>
<li></li>

<!-- h1.title+p.body -->
<h1 class="title"></h1>
<p class="body"></p>

<!-- div>h1.title+p.body -->
<div>
    <h1 class="title"></h1>
    <p class="body"></p>
</div>

<!-- GROUPIONG () -->

<!-- div>(header>ul>li*2>a>{link $})+footer>p{Copyright 2018} -->
<div>
    <header>
        <ul>
            <li><a href="">link 1</a></li>
            <li><a href="">link 2</a></li>
        </ul>
    </header>
    <footer>
        <p>Copyright 2018</p>
    </footer>
</div>

<!-- ATTRIBUTES -->

<!-- a[href="http://google.com" target="_blank" title="Google"] -->
<a href="https://google.com" target="_blank" title="Google"></a>

<!-- FORMS & INPUT -->

<!-- form -->
<form action=""></form>

<!-- form:get -->
<form action="" method="get"></form>

<!-- form:post -->
<form action="" method="post"></form>

<!-- label -->
<label for=""></label>

<!-- input -->
<input type="text">

<!-- inp -->
<input type="text" name="" id="">

<!-- input:email -->
<input type="email" name="" id="">

<!-- input:s -->
<input type="submit" value="">

<!-- select -->
<select name="" id=""></select>



<!-- EXTENDED STRUCTURE + -->

<!-- select+ -->
<!--It is not working from visula studio code 2.0 version-->
<select name="" id="">
    <option value=""></option>
</select>

<!-- table+ -->
<!--It is not working from visula studio code 2.0 version-->
<!--But we can add them as your custom snippets-->
<table>
    <tr>
        <td></td>
    </tr>
</table>

<!-- ol+ -->
<ol>
    <li></li>
</ol>
<!-- ul+ -->
<ul>
    <li></li>
</ul>

<!-- CUSTOM ALIASES edit snippets.json file -->
<!--We have to create a file snippets.json and
    should give that folder path to "emmet.extensionsPath" in VScode -->
<!--https://code.visualstudio.com/docs/editor/emmet#_using-custom-emmet-snippets-->

<!-- post -->
<div id="post">
    <h1 class="title"></h1>
    <p class="body"></p>
</div>

<!-- DOCTYPE AND STRUCTURE -->

<!-- ! -->

<!--    -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>

</body>
</html>

<!-- html:5 -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>

</body>
</html>

<!-- LOREM IPSUM GENERATOR -->

<!-- lorem -->
Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti repellendus temporibus quidem amet aperiam nisi libero consequuntur hic harum iste tempore quo pariatur quasi officia, sapiente quas fugiat illum quaerat?

<!-- lorem10 -->
Lorem ipsum dolor sit, amet consectetur adipisicing elit. Harum, quo!

<!-- ul.mylist>lorem10.item*4 -->
<!-- ul.mylist>li.item*4>lorem10 -->
<ul class="mylist">
    <li class="item">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Odio, sequi!</li>
    <li class="item">Fugiat, atque sunt voluptas doloribus vero placeat possimus qui eveniet!</li>
    <li class="item">Doloremque et libero beatae recusandae maiores quasi quae. Eos, alias!</li>
    <li class="item">Doloremque cupiditate aut atque quae voluptates odio modi quos iusto!</li>
</ul>

<!-- p>{Click }+a{here}+{ to continue} -->
```

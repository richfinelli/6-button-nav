6-button-nav
============

On wide screens its 6 tab-like menus, on smaller screens its a key-pad like 2 rows of 3 buttons.

It doesn't scale with odd numbers. So 7 menu items won't really do much for you. But it does scale to some extent with 
even numbers with a few tweaks of the HTML and CSS. 

I mainly wanted to demonstrate how a horizontal menu of tabs can go from 1 row to two rows with a little effort 
in the CSS department.


Here's how you can get started:

Step 1: Copy in the HTML

```html
  <nav>
          <ul class="transition">
                  <a href="#"><li class="nav column1 first">Nav 1</li></a>
                  <a href="#"><li class="nav column2">Nav 2</li></a>                
                  <a href="#"><li class="nav column3">Nav 3</li></a>
                  <a href="#"><li class="nav column1">Nav 4</li></a>                
                  <a href="#"><li class="nav column2">Nav 5</li></a>                
                  <a href="#"><li class="nav column3">Nav 6</li></a>                
          </ul>
  </nav>
```

Note on the placement of anchor tags: The HTML is a little unconventional in that the anchor tags are wrapped around the list items, which makes them 
direct decendents of the unordered list. I like doing it this way however. If you don't of course you can shift things
around in your HTML and CSS with only a little effort to get it to work. 

Step 2: Copy this CSS in to your style sheet

```css
/*********************
Initial Styles
*********************/

html, body, ul, li {
        margin: 0;
        padding: 0;
        vertical-align: baseline;
}
body {
        background-color: #2e363d;
        font-size: 100%;
        line-height: 1;
}
ul {
        list-style: none;
}
h1 {
        font-family: 'Marcellus SC', serif;
        font-size: 4em;
        text-align: center;
        margin-top: 50px;
        color: #3E62D6;
}
p {
        font-family: 'Marcellus SC', serif;
        font-size: 1.4em;
        text-align: center;
        margin: 25px auto 0 auto;
        color: #fff;
        max-width: 75%;
}
/*********************
Navigation Styles
*********************/
nav {
        display: block;
        width: 66.666666666666666666666666666667%;
        height: 60px;
        margin: 0 auto;
}
.nav {
        height: 30px; 
        width: 15.625%; 
        margin: 0px 0px 0px 01.25%;
        float: left;
        background-color: #e5e5e5;
        -webkit-border-radius: 0px 0px 15px 15px; 
        -moz-border-radius: 0px 0px 15px 15px; 
        -o-border-radius: 0px 0px 15px 15px; 
        border-radius: 0px 0px 15px 15px; 
        text-align: center;
        padding-top: 8px;
        border-bottom: 1px solid #ddd;
        color: #2e363d;
        text-decoration: none;
        font-size: 1em; 
        font-family: 'Marcellus SC', serif;
}

.nav.first {
        margin-left: 0px;
}

.nav:hover {
        text-decoration: none;
        border-bottom: none;
        background-color: #ccc;
        border-top: 3px solid #3E62D6;
}
.nav:visited {
        color: #2e363d;
}
.transition li {
        -webkit-transition: background-color 0.5s linear;
        -moz-transition: background-color 0.5s linear;
        -ms-transition: background-color 0.5s linear;
        -o-transition: background-color 0.5s linear;
        transition: background-color 0.5s linear;
}

/********************************************************
Media Query for Screens and Devices 850px or less
********************************************************/
@media all and (max-width: 850px) {

        nav {
                width: 100%;
                height: 82px;
                margin: 0px;
        }
        .nav {
                height: 30px; 
                margin: 0px; 
                width: 33.125%;
                float: none;
                border-bottom: none;
                -webkit-border-radius: 0px; 
                -moz-border-radius: 0px; 
                -o-border-radius: 0px; 
                border-radius: 0px; 
                text-align: center;
                padding-top: 8px;
                display: block;
        }

        .column1 {
                float: left;
                margin-right: 1px;
                margin-bottom: 1px;
        }
        .column2 {
                float: left;
                margin-right: 1px;
                margin-bottom: 1px;
        }
        .column3 {
                float: left;
                margin-bottom: 1px;
                margin-right: 0px;
        }

        .nav {
                font-size: 1.1em;
                margin-left: 0px;
        }
        .nav:hover {
                border-top: none;
        }        
}
```

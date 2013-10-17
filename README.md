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

body {
        margin: 0;
}


/*********************
Navigation Styles
*********************/

nav ul, nav li {
        margin: 0;
        padding: 0;
        list-style: none;
}
nav {
        display: block;
        width: 66.666666666666666666666666666667%;
        height: 60px;
        margin: 0 auto;
        min-width: 850px;
}
.nav {
        height: 30px; 
        width: 15.625%;
        min-width: 120px;
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
}

.nav.first {
        margin-left: 0px;
}
.nav:hover {
        text-decoration: none;
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
```

Step 3: 
And then copy the CSS for the media query. I have it set to any screen width 850px or less.
You can change the max width to be less or more depending on your preferences. 

```css

/********************************************************
Media Query for Screens and Devices 850px or less
********************************************************/
@media all and (max-width: 850px) {

        nav {
                width: 100%;
                height: 82px;
                margin: 0px;
                min-width: 250px;
        }
        .nav {
                height: 30px; 
                margin: 0px; 
                width: 33.125%;
                min-width: 50px;
                float: none;
                border-bottom: none;
                -webkit-border-radius: 0px; 
                -moz-border-radius: 0px; 
                -o-border-radius: 0px; 
                border-radius: 0px; 
                display: block;
                font-size: 1.1em;
        }

        .column1, .column2 {
                float: left;
                margin-right: 1px;
                margin-bottom: 1px;
        }
        .column3 {
                float: left;
                margin-bottom: 1px;
                margin-right: 0px;
        }
        .nav:hover {
                border-top: none;
        }        
}
```

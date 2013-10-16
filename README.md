6-button-nav
============

On wide screens its 6 tab-like menus, on smaller screens its a key-pad like 2 rows of 3 buttons.

It doesn't scale with odd numbers. So 7 menu items won't really do much for you. But it does scale to some extent with 
even numbers with a few tweaks of the HTML and CSS. 

I mainly wanted to demonstrate how a horizontal menu of tabs can go from 1 row to two rows with a little effort 
in the CSS department.


Here's how you can get started:

Step 1: Copy in the HTML

<code>
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
</code>

Note on the placement of anchor tags: The HTML is a little unconventional in that the anchor tags are wrapped around the list items, which makes them 
direct decendents of the unordered list. I like doing it this way however. If you don't of course you can shift things
around in your HTML and CSS with only a little effort to get it to work. 

Step 2: Copy this CSS in to your style sheet




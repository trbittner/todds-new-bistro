[This is my original site design](https://toddbittner.gitlab.io/).  I like it, but I also like the card format as well.
I'll have to see if there's some compromise design that satisfies both of my design cravings.

# Tasks
## Set up the environment
* Install [jekyll](http://jekyllrb.com/) as per the site instructions (I'm surprised the site isn't https).
* I'm using Amazon's Cloud9 for development.  The GUI doesn't permit up-to-date authentication with 
    GitHub, but the command line does permit the appropriate access.  So, when in doubt, use the CLI.
* I'm using [skeleton css](http://getskeleton.com/) for the basic formatting (also not secure - WTH!!).
## Create a basic card
* I used [this template](https://www.w3schools.com/howto/howto_css_profile_card.asp) for creating a card.
* I had to remind myself of the difference between [margins and padding](https://www.w3schools.com/css/css_padding.asp)
    to make the card look less crowded.
    - [ ] Still need to align the text within the lists a bit better.
    - [ ] Still need to verify that I'm creating checklists correctly for GitHub.
## Create a site header
* [Basic CSS](https://www.w3schools.com/howto/howto_css_style_header.asp)
* A basic article on [color schemes](https://www.wordstream.com/blog/ws/2019/10/03/website-color-scheme).
* [colors.co](https://coolors.co/), a color scheme generator site.
* My chosen color scheme:
```
/* CSS HEX */
--white: #ffffffff;
--turquoise-blue: #81f4e1ff;
--vivid-sky-blue: #56cbf9ff;
--french-pink: #ff729fff;
--languid-lavender: #d3c4d1ff;

/* CSS HSL */
--white: hsla(0, 0%, 100%, 1);
--turquoise-blue: hsla(170, 84%, 73%, 1);
--vivid-sky-blue: hsla(197, 93%, 66%, 1);
--french-pink: hsla(341, 100%, 72%, 1);
--languid-lavender: hsla(308, 15%, 80%, 1);

/* SCSS HEX */
$white: #ffffffff;
$turquoise-blue: #81f4e1ff;
$vivid-sky-blue: #56cbf9ff;
$french-pink: #ff729fff;
$languid-lavender: #d3c4d1ff;

/* SCSS HSL */
$white: hsla(0, 0%, 100%, 1);
$turquoise-blue: hsla(170, 84%, 73%, 1);
$vivid-sky-blue: hsla(197, 93%, 66%, 1);
$french-pink: hsla(341, 100%, 72%, 1);
$languid-lavender: hsla(308, 15%, 80%, 1);

/* SCSS RGB */
$white: rgba(255, 255, 255, 1);
$turquoise-blue: rgba(129, 244, 225, 1);
$vivid-sky-blue: rgba(86, 203, 249, 1);
$french-pink: rgba(255, 114, 159, 1);
$languid-lavender: rgba(211, 196, 209, 1);

/* SCSS Gradient */
$gradient-top: linear-gradient(0deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-right: linear-gradient(90deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-bottom: linear-gradient(180deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-left: linear-gradient(270deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-top-right: linear-gradient(45deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-bottom-right: linear-gradient(135deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-top-left: linear-gradient(225deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-bottom-left: linear-gradient(315deg, #ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
$gradient-radial: radial-gradient(#ffffffff, #81f4e1ff, #56cbf9ff, #ff729fff, #d3c4d1ff);
```
## Add photo attribution
* [Rumman Amin from Unsplash](https://unsplash.com/photos/nKs-oXRGGEg)
* ~~[Footer CSS](https://www.w3schools.com/howto/howto_css_fixed_footer.asp)~~
* Added the attribution to the image itself using [this tutorial](https://www.w3schools.com/css/tryit.asp?filename=trycss_position_absolute).
 
## Clean CSS to match Skeleton, not Jekyll
* This was easy enough.  I just needed to point the css links in the header to `href` not `src`.

## List 3 recipes
* Done.  I also added top and bottom margins to the cards to create a better sense of space.
 
## Templatize Jekyll to allow for recipe publication
* This took a bit longer than I expected due to some markdown quirks, but I got it going.
* ~~[This site helped with css classes.](https://digitaldrummerj.me/styling-jekyll-markdown/)~~
* I'm handling the content with front matter in the individual recipe pages via YAML.
It provides more consistency in the layout.
* [This site](https://yaml-multiline.info/) and [this one](https://www.cloudbees.com/blog/yaml-tutorial-everything-you-need-get-started)
helped me with YAML oddities.

## Add tags for recipes
* ~~This is going to [take](https://www.w3schools.com/howto/howto_js_filter_elements.asp) some javascript if we want to keep the site static.~~
* We need to make sure we [join tags](https://shopify.github.io/liquid/filters/join/) appropriately in the div class property.
* [This cheatsheet](https://michaelcurrin.github.io/dev-cheatsheets/cheatsheets/jekyll/liquid/filters.html) may also come in handy.
* [Another shopify API reference](https://shopify.dev/api/liquid/).
* Ultimately, I went with a custom function as written.  When hiding elements, it's important to keep in mind the difference between
element.style.display` and `element.style.visibility`.  The former removes the element from the flow.  The latter just hides it.
* Writing the javascript, as usual, taught me something new.  I was unaware of the `sticky` element in CSS.  I also learned about JS use
sets.
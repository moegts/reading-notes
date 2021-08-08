# Audio, Video, Images

## Chapter 16: “Images”

### Controlling sizes of images in css

```bash
img.large {
width: 500px;
height: 500px;}
img.medium {
width: 250px;
height: 250px;}
img.small {
width: 100px;
height: 100px;}
```

### by images name

```bash
<p><img src="images/magnolia-medium.jpg"
    alt="Magnolia" class="align-left medium" />
// CSS
img.medium {
width: 250px;
height: 250px;}

img.align-center {
display: block;
margin: 0px auto;}
img.medium {
width: 250px;
height: 250px;}
```

### Background Images

```bash
body {
background-image: url("images/pattern.gif");}

# Repeat

body {
background-image: url("images/header.gif");
background-repeat: repeat-x;}

# no repeat

body {
background-image: url("images/tulip.gif");
background-repeat: no-repeat;
background-attachment: fixed;}

# repeat-x

# repeat-y

# no-repeat

# background-position
body {
background-image: url("images/tulip.gif");
background-repeat: no-repeat;
background-position: center top;}
                    left top
                    left center
                    left bottom
                    center top
                    center center
                    center bottom
                    right top
                    right center
                    right bottom

# Image Rollovers & Sprites

text-indent: -9999px;
display: inline-block;}

# BACKGROUND GRADIENT

background-image: -o-linear-gradient(#336666,
 #66cccc);
height: 150px;
width: 300px;}

```

### IMAGES SUMMARY
- You can specify the dimensions of images using CSS.
This is very helpful when you use the same sized
images on several pages of your site.

- Images can be aligned both horizontally and vertically using CSS.

- You can use a background image behind the box created by any element on a page.

- Background images can appear just once or be repeated across the background of the box.

- You can create image rollover effects by moving the background position of an image.

- To reduce the number of images your browser has to load, you can create image sprites.

## Chapter 19: “Practical Information”

### In every page of your website there are seven key places where keywords (the words people might search on to find your site) can appear in order to improve its findability

1. Page Title: The page title appears at the top of the browser window or on the tab of a browser. It is specified in the `<title>` element which lives inside the `<head>` element.

2. URL / Web Address The name of the file is part of the URL. Where possible, use keywords in the file name

3. Headings If the keywords are in a heading `<hn>` element then a search engine will know that this page is all about that subject and give it greater weight than other text.

4. TEXT: Where possible, it helps to repeat the keywords in the main body of the text at least 2-3 times. Do not, however, over-use these terms, because the text must be easy for a human to read.

5. Link Text Use keywords in the text that create links between pages (rather than using generic expressions such as "click here")

6. Image Alt Text Search engines rely on you providing accurate descriptions of images in the alt text. This will also help your images show up in the results of image-based searches

7. Page Descriptions The description also lives inside the `<head>` element and is specified using a `<meta>` tag. It should be a sentence that describes the content of the page. (These are not shown in the browser window but they may be displayed in the results pages of search engines.)

### How to Identify Keywords and Phrases

1. Brainstorm List down the words that someone might type into Google to find your site. Be sure to include the various topics, products or services your site is about.

2. Organize Group the keywords into separate lists for the different sections or categories of your website.

3. Research There are several tools that letyou enter your keywords and then they will suggest additional keywords you might like to consider, such as: adwords.google.co.uk/ select/KeywordToolExternal (When using this tool, select the "exact match" option rather than "broad match.")
www.wordtracker.com
www.keyworddiscovery.com

4. Compare It is very unlikely that your site will appear at the top of the search results for every keyword. This is especially true for topics where there is a lot of competition. The more sites out there that have already been optimized for a given keyword, the harder it will be for you to rise up the search results when people search on that term.

5. Refine Now you need to pick which keywords you will focus on. These should always be the ones that are most relevant to each section of your site.

6. Map Now that you have a refined list of keywords, you know which have the most competition, and which ones are most relevant, it is time to start picking which keywords you will use for eachpage.

#### NOT DONE YET 483
# HTML:heart:

[TOC]

## 1 Introduction

### 1. What is HTML?

**It only provides structures, CSS provides style.**

- It provides **structure** to the content appearing on a website, such as images, texts or videos.
- It stands for **HyperText Markup Language**

### 2. Structure

#### (1) one row in the body ```<p> </p>```

![the structure of one element](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200715021012152.png)

#### (2) `<body> </body>`

The contents inside body is what displayed to screen.

#### (3)`<div> </div>`

`<div> </div>` is short for "division" or a container that divides the page into sections, which is great for **grouping elements** in HTML together. 

* can contain any contents

### 3. headings

```html
<body>
  <h1>The Brown Bear</h1>
  <h2>About Brown Bears</h2>
  <h3>Species</h3>
  <h3>Features</h3>
  <h2>Habitat</h2>
  <h3>Countries with Large Brown Bear Populations</h3>
  <h3>Countries with Small Brown Bear Populations</h3>
  <h2>Media</h2>
</body>
```

![image-20200715215914995](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200715215914995.png)

Smallest tag: h6

### 4. Attributes

Help identify content on the page.

```html
<div id="intro">
  <h1>Introduction</h1>
</div>
```

### 5. Displaying text

`<p>`: 

- stand for **paragraph**; 
- contain short pieces of text
- not inline, only used for displaying text

`<span>`: 

- separate small pieces of content

- helpful in CSS so that I can **style** one part of a paragraph differently than the rest

  ![What is a Span Tag](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200715225843514.png)

- **Inline elements**

### 6. built-in style

- `<em>`: *italic*
- `<strong>`: **bold**

### 7. line break elements: `<br>`

It is special because it only composed of a **starting tag**.

```html
<p>The Nile River is the longest river <br> in the world, measuring over 6,850 <br> kilometers long (approximately 4,260 <br> miles).</p>
```

which will look like this:

![image-20200715231041141](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200715231041141.png)

### 8. Unordered List

* To create a list, use `<ul>` tag

* Add elements with **`</li>`** tag

  ```html
  <ul>
    <li>Limes</li>
    <li>Tortillas</li>
    <li>Chicken</li>
  </ul>
  ```

### 9. Ordered List

Use `<ol>`, and everything else is just like the unordered list.

### 10. Images

1. Use `<img>`, **a self closing tag**.
2. The tag has a retuired attribute called `src`-- be set to the image's source.

```html
<img src="image-location.jpg" />
```

3. `<alt>` attribute is used to descripe what the image is.

   ```html
   <img src="#" alt="A field of yellow sunflowers" />
   ```

### 11. Videos

1. Use the `<video>` tag and `src` attribute
2. **Unlike `<image>`, it requires an opening and a closing tag.**
3. `controls` attributes instructs the browser to include basic video controls: pause, play and skip.

```html
<video src="myVideo.mp4" width="320" height="240" controls>
  <!--Only display "Video not supported" when the browser is unable to load the video.-->
<p>This will be shown in the browser.</p>
  Video not supported
</video>
```

### 12. Adding Comments

```html
<!-- This is a comment that the browser will not display. -->
```

## * How to create great html?

- **Accessibility**: the practice to make the website **usable** for as many users as possible

  - eg: Visually imparied users may not see the contents, so we should develop the function to help them read.

  - **solution: `<alt>`**

- **Structure**: A structured content is helpful for readability and maintanence to html.
  - A heading is a heading, and the content is the content.
  - indentation
  - Use semantically meaningful tags and avoid using meaningless tags like `<div>`

## 2 HTML Document Standards

### 1. Preparing for HTML

#### (1) Document Type Declaration

We need to declare what type of document it is to the web browser, which is called a *document type declaration*. The following lines tell the browser this is *HTML5* version:

```html
<!DOCTYPE html>
```

#### (2) Add HTML structure

Use `<html>` tag. Anything between the opening `<html>` and closing `</html>` tags will be interpreted as HTML code. 

```html
<!DOCTYPE html>
<html>

</html>
```

#### (3) the Head

The head element contains *metadata* of a webpage, which is **NOT** displayed directly on the web page. It is before `<body>` tag, which is directly the contents we can see on the webpage.

```html
<head>
</head>
```

1. Contain the title of the page, using `<title>'.

   ```html
   <!DOCTYPE html>
   <html>
     <head>
       <title>My Coding Journal</title>
     </head>
   </html>
   ```

### 2. Linking: anther `<a>`

#### (1) Linking to external website

Use the **ancher** tag `<a>`.herf stands for *hyperlink reference*.

```html
<a>href="https://www.wikipedia.org/">This Is A Link To Wikipedia</a>
```

#### (2) Open Link in Different Ways: target attribute

The following code will open a new tab.

```html
<a href="https://en.wikipedia.org/wiki/Brown_bear" target="_blank">The Brown Bear</a>
```

#### (3) Open internal pages

1. **How it works**: Developers store HTML files in the same directory when making the multi-page static website:

   ```pseudocode
   project-folder/
   |—— about.html
   |—— contact.html
   |—— index.html
   ```

2. **How to link**: using a *relative path*

   Suppose contact and about are in the same folder:`./` means the same directory.

   ```html
   <a href="./contact.html">Contact</a>
   ```

#### (4) Other forms as a Link

Previously, the code is like this:

```html
<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank">Prickly Pear</a>
```

Just **replace** the text `Prickly Pear` with picture element `<img src="https://www.Prickly_Pear_Closeup.jpg" alt="A red prickly pear fruit"/>`, and we can access a new website from this picture:

```html
<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank"><img src="https://www.Prickly_Pear_Closeup.jpg" alt="A red prickly pear fruit"/></a>
```

The meanings of these two links are different:

1. first link: the link that will access once clink on the image
2. second link: the url of the image

#### (5) Linking to Different Portions on the Same Page

Create unique attribute`id` for elements, then use `# + id` to access.

```html
<!-- Attribute id can be added to almost every tag: -->
<p id="top">This is the top of the page!</p>
<h1 id="bottom">This is the bottom! </h1>

<!-- The target link is a string containing # and the target id:-->
<ol>
  <li><a href="#top">Top</a></li>
  <li><a href="#bottom">Bottom</a></li>
</ol>
```



## 3. Tables

### 1. elements

#### (1) in headings

Headings stand for both the name for the column and the name for the row.

In the following table, both `Grocery` and `Monday` are headings:

| Cost      | Grocery | Clothes | Food |
| --------- | ------- | ------- | ---- |
| Monday    |         |         |      |
| Tuesday   |         |         |      |
| Wednesday |         |         |      |
| Thursday  |         |         |      |

The difference is the attribute `scope`. For the vertical one like `Grocery`, `scope = "col"`, and for the horizontal one like `Monday`, `scope = "row"`.

```html
  <tr>
    <th></th>
    <th scope="col">Saturday</th>
    <th scope="col">Sunday</th>
  </tr>
```

Use `<thead>` to include all heading elements.

#### (2) in body

- `<table>` : create a table
- `<tr>`: stand for **table rows**, to create table rows
- `<td>`: stand for **table data**, to add values to the table

```html
<table>
  <tr>
    <td>73</td>
    <td>81</td>
  </tr>
</table>
```

Use `<tbody>` to include all body elements

#### (3) in foot

Foot is used to contain sums, differences and other data **results**.

Use `<tfoot>` to contain all summaries.

### 2. format

#### (1) span columns and rows:`rowspan` and `colspan`

```html
    <td rowspan="2">Work</td>
    <td colspan="3">Relax</td>
```

## 4. Forms

### 1.What is forms?

The area when we are typing intro a **text field** or **providing an inpit** is a form.

Example: This search bar is a form.

![An example of a form](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200720204014646.png)

### 2. How a Form Works -> HTTP protocol

![how HTTP works](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200720212255835.png)

### 3.How to create a form: `<form>`

#### (1) basic

Two attributes are required:

- `action`: where the inputted text should be sent to
- `method`: what request/action

Example:

```html
<form action="/example.html" method="POST">
  <h1>Creating a form</h1>
  <p>Looks like you want to learn how to create an HTML form. Well, the best way to learn is to play around with it.</p>
</form>
```

#### (2) Text Input: `<input>` element

**The `for` attribute in *label* should be matched with `id` attribute in *input*.**

1. `type` : determine how it renders on the web page and what kind of data it can accept

   - Password: `password`

   - Number input: `number`

     - The `step` attribute( *optional*) is uesd to increase or decrease by the value of this attribute

   - Limited Options: `range`

     ```html
     <form>
       <label for="volume"> Volume Control</label>
       <input id="volume" name="volume" type="range" min="0" max="100" step="1">
     </form>
     ```

   - Check Box: `checkbox`

     ```html
     <input id="cheese" name="topping" type="checkbox" value="cheese">
     <label for="cheese">Extra cheese</label>
     ```

     - `name`: the column name we can see in the output sheet
     - `id`: match the `for` in lable, what the following input is used for
     - `value`: the value in label, the content of this checkbox

   - Only one option: `radio`

     ```html
       <input type="radio" id="two" name="answer" value="2">
       <label for="two">2</label>
     ```

   - Dropdown List: `<select>` element

     Use `<option>` element to create each option in a dropdown list.

     ```html
     <form>
       <label for="lunch">What's for lunch?</label>
       <select id="lunch" name="lunch">
         <option value="pizza">Pizza</option>
         <option value="curry">Curry</option>
         <option value="salad">Salad</option>
         <option value="ramen">Ramen</option>
         <option value="tacos">Tacos</option>
       </select>
     </form>
     ```

   - A lot of options: `datalist`

     Use a `list` attribute in `<input>` to match with `id` in `<datalist>`

     ```html
     <form>
       <label for="city">Ideal city to visit?</label>
       <input type="text" list="cities" id="city" name="city">
     
       <datalist id="cities">
         <option value="New York City"></option>
         <option value="Tokyo"></option>
         <option value="Barcelona"></option>
         <option value="Mexico City"></option>
         <option value="Melbourne"></option>
         <option value="Other"></option>  
       </datalist>
     </form>
     ```

   - A big area to put sentences: `<textarea>`:

     ```html
     <form>
       <label for="blog">New Blog Post: </label>
       <br>
       <textarea id="blog" name="blog" rows="5" cols="30">
       </textarea>
     </form>
     ```

     

2. Submit a form

   `value`is the default value on that button

   ```html
   <form>
     <input type="submit" value="Send">
   </form>
   ```

### 4. An example for burger ordering form

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
    <title>Forms Review</title>
  </head>
  <body>
    <section id="overlay">
      <img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg" alt="Davie's Burgers Logo" id="logo">
      <hr>
      <form action="submission.html" method="POST">
				<h1>Create a burger!</h1>
        <section class="protein">
          <label for="patty">What type of protein would you like?</label>
    			<input type="text" name="patty" id="patty">
        </section>
        <hr>
        
        <section class="patties">
          <label for="amount">How many patties would you like?</label>
          <input type="number" name="amount" id="amount">
        </section>
        <hr>
        
        <section class="cooked">
          <label for="doneness">How do you want your patty cooked</label>
          <br>
          <span>Rare</span>
          <input type="range" name="doneness" id="doneness" value="3" min="1" max="5">
          <span>Well-Done</span>
        </section>
        <hr>
        
        <section class="toppings">
          <span>What toppings would you like?</span>
          <br>
          <input type="checkbox" name="topping" id="lettuce" value="lettuce">
          <label for="lettuce">Lettuce</label>
          <input type="checkbox" name="topping" id="tomato" value="tomato">
          <label for="tomato">Tomato</label>
          <input type="checkbox" name="topping" id="onion" value="onion">
          <label for="onion">Onion</label>
        </section>
        <hr>
        
        <section class="cheesy">
          <span>Would you like to add cheese?</span>
          <br>
          <input type="radio" name="cheese" id="yes" value="yes">
          <label for="yes">Yes</label>
          <input type="radio" name="cheese" id="no" value="yes">
          <label for="no">No</label>
        </section>
        <hr>
       
        <section class="bun-type">
          <label for="bun">What type of bun would you like?</label>
          <select name="bun" id="bun">
            <option value="sesame">Sesame</option>
            <option value="potatoe">Potato</option>
            <option value="pretzel">Pretzel</option>
          </select>
        </section>
        <hr>
        
        <section class="sauce-selection">
          <label for="sauce">What type of sauce would you like?</label>
          <input list="sauces" id="sauce" name="sauce">
          <datalist id="sauces">
            <option value="ketchup"></option>
            <option value="mayo"></option>
            <option value="mustard"></option>
          </datalist>
        </section>
        <hr>
        <section class="extra-info">
          <label for="extra">Anything else you want to add?</label>
          <br>
          <textarea id="extra" name="extra" rows="3" cols="40"></textarea>
        </section>
        <hr>

        <section class="submission">
          <input type="submit" value="Submit">
        </section>
      </form>
    </section>
  </body>
</html>

```

Output:

![output of form example](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200721194600863.png)



### 5.Validation of Forms

#### (1) Requiring an input

Add `required` attribute in `<input>` so that this input must be filled to submit the form.

```html
 <input id="allergies" name="allergies" type="text" required>
```

#### (2) `minlength` and `maxlength`

#### (3) Match a Pattern: `pattern` attribute

The following example means the valid pattern is number, and the number of digits is 14-16:

```html
 <input id="payment" name="payment" type="text" required pattern="[0-9]{14,16}">
```



## Semantic HTML

### 1. Header and Nav

- `<header>`: introductory content
- `<nav>`: define a block of navigation, such as menu

### 2.Main and Footer

- `<main>`: dominant contents

  contains `<article>`, `<header>` and the most important information

- `<footer>`: contain additional information such as:

  - Contact information 
  - Copyright information
  - Terms of use 
  - Site Map
  - Reference to top of page links

### 3. Article and Section

- `<section>`: elements with same theme, such as chapters, headings
- `<article>`: the article content

### 4. aside

Not main content, supplementary materials.

### 5. figure and figcaption

```html
<figure>
  <img src="overwatch.jpg">
  <figcaption>This picture shows characters from Overwatch.</figcaption>
</figure>
```

### 6. audio

```html
<audio>
  <source src="iAmAnAudioFile.mp3" type="audio/mp3">
</audio>
```



## Extra Notes

### 1. terminology

#### (1)inline-level elements

- It means the element starts a new line. For example, `<p>`is not an inline tag because it is only used for displaying the text.
- example: `<span>`

#### (2)block-level elements

- It means new elements will push sibling elements to a new line or section of the page.
- example: `<p>`, `<div>`

#### (3) element

The content with the tag.

Example:

```html
<h1> The Origin of Philosophy </h1>
```

This whole line is called a content.

### 2. concepts

#### (1) difference between `<setion>` and `<div>`

**Section** is like a chapter. *It has meanings*. And it has the function of thematic grouping of content; Other meaningful tags include `<main>`, `<header>`, `<footer>` and `<nav>`.

**Division** has *no special meaning at all*, it should be viewed as an element of last resort.

#### (2) How does HTTP works

1. Public key cryptography & signature works
   - Any message encrypted with Bob's public key can only be decrypted with Bob's private key.(Only bob can edit contents in this webpage because Bob hold a private key which can decrypt the public key. The website is view-only to other users. Thought they have the public key, they don't have the private key to have access to editing.)
   - Anyone with access to Ace's public key can verify that a message(signature) could only have been created by someone with access to Alice's private key.(Everyone can recognize who sent the message though they don't know the private key.)

2. ![dialogue explanation of HTTP](C:\Users\dsj\AppData\Roaming\Typora\typora-user-images\image-20200720213850390.png)



## Resources

1.[cheat sheets of HTML](https://www.codecademy.com/learn/learn-html/modules/learn-html-elements/cheatsheet)

2.[video: how http works ](https://www.youtube.com/watch?v=T4Df5_cojAs)

3.[Regex: valid pattern of an input](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
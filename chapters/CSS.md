# CSS

CSS stands for __Cascading Style Sheets__. In the last chapter, we saw how boring HTML looks in its raw form. CSS is how we style our web pages to be visually engaging.

## Linking your CSS file to your HTML document
Your CSS should live in a seperate file from your HTML. In order for your CSS to take effect, you have to link it to your HTML document. The following code goes in the `<head>` element of your HTML:
```html
<link rel="stylesheet" href="your-stylesheet-name-here.css">
```

## CSS Selectors
You can select HTML elements in several different ways. 
Let's start with the first two:

### By Element
This would select __all__ the paragraph tags in an HTML document and give them a background color of red.
```css
p{
  background-color: red;
}
```
### By Class
This would select all the elements with a class of `bio` and give them a font-size of 18 pixels.
```css
.bio{
  font-size: 18px;

}
```

## CSS Declarations
Once you've selected something, it's time to apply some styles. Each individual style is called a declaration. Declarations are made up of properties and values. In the following example, `font-color` is the property and `rgb(155, 244, 66)` is the value.
```css
li{
  font-color: rgb(155, 244, 66);
}
```
You can write as many declarations as you want for any given selector. Your browser will apply those styles from top to bottom. In the example below, I accidentally wrote two declarations for text-aligment. The last `text-alignment` declaration will override the first one.
```css
h3{
  text-align: left;
  font-color: #9bf442;
  font-weight: bold;
  border-radius: 10px;
  text-align: center;
}
```

## Font
Here are some font properties to take for a spin:
- `font-family`
- `font-size`
- `font-weight`

[Here's a more detailed write-up of CSS fonts.](https://www.w3schools.com/css/css_font.asp)

[Google Fonts](https://fonts.google.com/) is also an excellent resource. When you select a font, it gives you readymade HTML and CSS.

## Colors
Here are a few different ways of specifying colors with CSS:
```css

h1{
  color: blue; /* blue text */
}

p{
 
  background-color: #ff0000;  /* red background*/
  color: rgb(0, 255, 0);   /* green text */
  border-color: rgba(0, 0, 255, 0.8);  /* blue, slightly transparent border */
}

```

[You can read more about CSS Colors here.](https://www.w3schools.com/cssref/css_colors_legal.asp)

[Here's a helpful color picker for your bookmarks bar!](https://htmlcolorcodes.com/color-picker/)

## Sizing Units
- Pixels- the most commonly seen absolute unit. They're great for very small, exact measurements but should generally be avoided because they don't scale to different screen sizes. (A pixel on a laptop is the same a a pixel on your smart phone, which makes it really difficult to design responsive websites.)

- `em`- 	Relative to the font-size of the element (2em means 2 times the size of the current font)
- `rem` - Relative to font-size of the entire web page, not the current element
- `vh` and `vw`- relative to screen size. One `vw` is 1% of the width of the screen; one `vh` is 1% of the height of the screen.
- Percentages - relative to the parent container

Example:

```html
<div class="bio">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam blandit ut velit non rhoncus. 
  <img class="headshot" src="../img/headshot.jpg">
</div>
```

```css
/*The div will take up 50% the screen's height and 20% of it's width. Its fontsize will be slightly larger than the default size. It will have a 1px black border*/
.bio{
  border: 1px solid black;
  width: 50vw;
  height: 20vh;
  font-size: 1.2em;
}

/* The image will take up 30% of the div's width and 100% of it's height. */
.headshot{
  width: 30%;
  height: 100%;
}


```



## Understanding the Cascade 

The CSS Cascade is the algorithm that your browser uses to decide which CSS styles to apply to an element—a lot of people like to think of this as the style that “wins”.

The cascade applies the following styles in order:

1. Styles with an `!important` declaration after this (this is the nuclear option- if you're using it, you're probably doing something wrong)
1. Inline styles in your HTML document (anything inside a style tag)
1. ID selectors
1. Classes / pseudo-selectors
1. Type selectors (for example, h1) & pseudo-elements (::before)

As a rule of thumb, you should default to using class selectors for your custom styles and element selectors for your default styles. If your CSS declarations have very high specificity and you find yourself resorting to `!important`, you're making it harder than it needs to be.

As we mentioned briefly above, the cascade also takes into account order. When two selectors have the same specificity, the declaration that comes last wins.

# Practice
Revisit your superhero website from the previous chapter. 

1. In the superhero website directory, create a new file: 
```
touch style.css
```
1. Link your new CSS file to the HTML file you made last time.

1. Give your elements appropriate classnames and apply the following styles:
    - Turn your `header` element into a splash page that takes up `100vw` and `100vh`. (Users should be able to scroll down to see the rest of your content.)
    - Give your `header` splash page a [background image](http://www.htmldog.com/guides/css/intermediate/backgroundimages/) of your choice.
    - All headings should be centered.
    - Pick two fonts from [Google Fonts](https://fonts.google.com/). Apply one of them to all the heading elements and the other  to all non-heading text.
    - Your name should have a font size of `2em`.
    - The `<aside>` should be `35vw` wide.
    - The entire page should have a background color of `#494949`
    - All text should be `#f4c20c`.
    - The text in your `footer` should be centered.
  
Commit your changes and then feel free to mess around with any other styles you like! 
  



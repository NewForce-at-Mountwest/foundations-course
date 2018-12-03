# Laying Out a Web Page with CSS
In the last chapter, we talked about how to style elements. Now let's talk about how to position elements on the page.

## The Box Model
Here's a secret: every web page you've ever seen is made up of boxes. We create layouts with CSS by specifying how big these boxes should be, how far apart, where they should sit in relation to each other, etc.

Every box is made up of four things:
1. **Content** - the amount of space that the actual element takes up. Content is determined by setting the `height` and `width`. 
1. **Padding** - the amount of space between the content and the border. Padding can be set on each individual side (`padding-left`, `padding-right`, etc) or all at once with the shorthand property `padding`. 
1. **Border** - You can read about all the cool things you can do with borders [here](https://www.w3schools.com/css/css_border.asp).
1. **Margin** - the amount of space between this box and the next box. Margin can be set on each individual side (`margin-left`, `margin-right`, etc) or all at once with the shorthand property `margin`. 
![The box model](../images/css-box-model.png)


## Layout

#### Inline, Block, and Inline-Block
We can also control whether elements appear side-by-side in a row or on their own line. 
```css
/* Headings are block level elements by default, which means they get their own line. We can ovverride that default style by giving all h3s a display property of "inline". You cannot set height or top or bottom margin/padding on inline elements*/
h3 {
  display: inline;
}

/* Buttons are inline elements by default. Let's say we want a submit button on it's own line, so we set its display property to "block".*/
.submit-btn{
  display: block;
}

/*Okay, what if we want things to appear side by side but we also want to be able to control their height, margin, and padding? "Inline-block" is the best of both worlds. */
.nav-link{
  display: inline-block;
}

```


#### Flexbox 
Flexbox is a very efficient tool for building responsive layouts that look great on any screen size. Start by giving the parent container a rule of `display: flex`. All of the children will line up inside it. You have complete control over how they line up and in what order. [Here's a great resource for working with flexbox.](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


# Practice
Continue to build your personal website, this time focusing on layout. [Here's an example of the finished product.](https://jordan-castelloe.github.io/onboarding-personal-website-demo/) Yours doesn't have to look exactly like this- it's just to give you a starting point. 

1. In your HTML, add a new `div` around your name and job title. This new `div` should be `30vw` wide with `4rem` of padding and should be centered both vertically and horizontally inside the `header` element. *(Hint: flexbox is great for centering!)*
1. Use flexbox to create a two-column layout for the page content: 
    - The left-hand column should be your bio `aside` element.
    - The right-hand column should contain your tech stack section and your work experience section. These sections should be stacked on top of each other.
    - Each column should have a padding of `1rem`.
    - You will need to add new elements to your HTML to make flexbox work correctly.
1. Each `article` element in your work experience section should have a top margin of `2em`.
1. Your `footer` element should have a top padding of `15vh` and a height of `20vh`. 



Once you've followed the steps above, feel free to change anything! 




## Supplemental Material
[How to center anything with CSS](http://howtocenterincss.com/)
[Master list of CSS Properties](http://overapi.com/css)
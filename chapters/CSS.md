# CSS

CSS stands for __Cascading Style Sheets__. In the last chapter, we saw how boring HTML looks in its raw form. CSS is how we style our web pages to be visually engaging.

## Linking your CSS file to your HTML document
Your CSS should live in a seperate file from your HTML. In order for your CSS to take effect, you have to link it to your HTML document. The following code goes in the `<head>` element of your HTML:
```
<link rel="stylesheet" href="your-stylesheet-name-here.css">
```

## CSS Selectors
You can select HTML elements in several different ways. 
Let's start with the first two:

### By Element
This would select __all__ the paragraph tags in an HTML document and give them a background color of red.
```
p{
  background-color: red;
}
```
### By Class
This would select all the elements with a class of `bio` and give them a font-size of 18 pixels.
```
.bio{
  font-size: 18px;

}
```

## CSS Declarations
Once you've selected something, it's time to apply some styles. Each individual style is called a declaration. Declarations are made up of properties and values. In the following example, `font-color` is the property and `rgb(155, 244, 66)` is the value.
```
li{
  font-color: rgb(155, 244, 66);
}
```
You can write as many declarations as you want for any given selector. Your browser will apply those styles from top to bottom. In the example below, I accidentally wrote two declarations for text-aligment. The last `text-alignment` declaration will override the first one.
```
h3{
  text-align: left;
  font-color: #9bf442;
  font-weight: bold;
  border-radius: 10px;
  text-align: center;
}
```

## Font

## Colors

## Sizing Units
#### Pixels

#### Ems and Rems

#### Percentages

## Understanding the Cascade 

# Practice
get exercises from Jumpstart




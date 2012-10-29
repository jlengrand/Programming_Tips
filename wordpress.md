# WordPress

Some very simple tips and hints for wordpress.

## Insert an horizontal line in a post :

Simply insert the <hr/> tag while in html edition mode .

## Insert anchors/links in a section of a page:

This is done in two different steps :

### Define the anchor.

You should place the following code where you want the user to be redirected.

```html
your article <a name= "name_of_the_anchor"></a> here.
```

### Create a link to the anchor.

Depending on what you want, you should insert :

#### If the anchor is placed in the same page :
```html
<a href= »#name_of_the_anchor »>my highlighted text</a>
```

#### If the anchor is in another page :
```html
<a href= »http://www.website.fr/#name_of_the_anchor »>my highlighted text</a>
<a href= »#name_of_the_anchor »>my highlighted text</a>
```
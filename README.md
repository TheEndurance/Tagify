# blog-tag-it

## Description
jQuery plugin for creating blog tags.  The plugin creates an input field and an area where the tags will accumulate as they are typed in, and 'enter' key is pressed.

[Example 1](http://i.imgur.com/spZ8jLa.png)

[Example 2](http://i.imgur.com/6EfZxOc.png)

## Installation
Download both tagify.css and tagify.js and place them in your project folder.  Place tagify.js in a script tag below jQuery script tag.

This plugin requires font-awesome.

## Usage
HTML:
Create a container, and give it an id.

```html
    <div id="my-container">
    </div>
```

Javacript:
To initialize the plugin use jQuery selector on the container created above and call .tagify()

```javascript
    $("#my-container").tagify();
```

The plugin has the the function InsertJsonArrayToForm that will take all of the tags created and turn it into a serialized JSON array.  Then it will create a hidden input field with the serialized JSON array values and append it to the form. ** ONLY upon submitting the form will this occur.

The function takes in 2 parameters: (1) The Id of the Form html element, (2) The 'name' attribute of the hidden input field. 

Example:
```javascript
    $("#my-container").tagify('InsertJsonArrayToForm','my-form','tags');
```

HTML before form is submitted
```html
    <form id="my-form" action="" method="POST">
        <button type="submit">submit</submit>
    </form>
```

HTML after form is submitted (with the tags 'Entertainment' and 'Technology' created)
```html
    <form id="my-form" action="" method="POST">
        <input type="hidden" name="tags" id="tags" values="['Entertainment','Technology']">
        <button type="submit">submit</submit>
    </form>
```



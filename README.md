# Tagify - jQuery blog tag plugin

## Description
jQuery plugin for creating blog tags.  The plugin creates an input field and an area where the tags will accumulate as they are typed in, and 'enter' key is pressed.

[Example 1](http://i.imgur.com/spZ8jLa.png)

[Example 2](http://i.imgur.com/6EfZxOc.png)

## Installation
Download both tagify.css and tagify.js and place them in your project folder.  Place tagify.js in a script tag below jQuery script tag.

This plugin requires font-awesome css and bootstrap 3.3.7 css.

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

Default options:

hiddenInputName : "Tags" (string)  (The hidden input field the plugin creates will have a name/id of Tags)
allowInput : true (boolean) (If true, turns on the input area where you can enter in new tags and the ability to delete tags)

Override defaults options using,

```javascript
    $("#my-container").tagify({
        hiddenInputName: "SomeOtherValue"
    })
```

The plugin provides the function InsertJsonArrayToForm that will take all of the tags created and turn it into a serialized JSON array.  Then it will create a hidden input field with the serialized JSON array values and append it to the form. ** ONLY upon submitting the form will this occur.

The function takes in 2 parameters: (1) The Id of the Form html element, (2) The 'name' attribute of the hidden input field. 

Example:
```javascript
    $("#my-container").tagify('InsertJsonArrayToForm','my-form');
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
        <input type="hidden" name="Tags" id="Tags" values="['Entertainment','Technology']">
        <button type="submit">submit</submit>
    </form>
```
*Note that the name/id of the hidden input field by Default is "Tags" unless overridden

## Contributing
Rawa Jalal

## License

MIT License

Copyright (c) [2017] [Rawa Jalal]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

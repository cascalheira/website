## Problem
You have a section of a template that is based on a data but you don't need the template to update

## Solution
Use the `{{unbound}}` Handlebars helper.

```handlebars
{{unbound firstName}}
{{lastName}}
```

### Discussion
By default all uses of Handlebars helpers in Ember.js will use data bound values that will automatically update
the section of the template where a property changes after initial rendering.  Ember.Handlebars does this by
applying the `{{bind}}` helper automatically for you.

For example, the two following uses of Handlebars are identical in an Ember.js application:

```handlebars
{{lastName}}
{{bind lastName}}
```

If you know that a property accessed in Handlebars will not change for the duration of the application's
life, you can specifiy that the property is not bound by applying the ``{{unbound}}` helper. A property
that is not bound will avoid adding unncessary observers on a property.


#### Example

<a class="jsbin-embed" href="http://jsbin.com/UDAnuLu/2/embed?js,output">JS Bin</a><script src="http://static.jsbin.com/js/embed.js"></script>

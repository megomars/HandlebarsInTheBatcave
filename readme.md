#Handlebars in the batcave

##Here are 100 things that you need to know about handlebars:

### Beginner commands
1. It's a popular templating engine based on mustache.js
2. With handlebars you can separate the generation of your HTML from the rest of your js and thus write cleaner code
3. Add handlebars to your project
```
<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/2.0.0/handlebars.js"></script>
```

4. Add templates to your page by writing these special script tags with type equal to text/x-handlebars-template
```
<!--This is our template. -->
<!--Data will be inserted in its according place, replacing the brackets.-->
<script id="address-template" type="text/x-handlebars-template">
  <p>You can find me in {{city}}. My address is {{number}} {{street}}.</p>
</script>

<!--Your new content will be displayed in here-->
<div class="content-placeholder"></div>
```


5. Templates need to be compiled to a javascript function before they can be used.
```
  // Grab the template script
  var theTemplateScript = $("#address-template").html();

  // Compile the template
  var theTemplate = Handlebars.compile(theTemplateScript);

  // Define our data object
  var context={
    "city": "London",
    "street": "Baker Street",
    "number": "221B"
  };

  // Pass our data to the template
  var theCompiledHtml = theTemplate(context);

  // Add the compiled html to the page
  $('.content-placeholder').html(theCompiledHtml);

```
6. Helpers also exist to help you write js in your templates
[https://github.com/assemble/handlebars-helpers](https://github.com/assemble/handlebars-helpers)

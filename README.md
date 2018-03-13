# Stencil
A handbook for those working in Big Commerce Stencil.

## Intro
Stencil is a platform, written in javascript, for selling things. The asynchronous nature of Node.js is what makes 
Stencil so quick. Instead of serving requests one at a time like the PHP backed Blueprint did, Stencil is able to serve requests in a parallistic manner. Stencil uses Handlebars.js to bring data to the DOM. Why this is great is that handlebars can be broken up into components which can be reused.

### Handlebars
Take this example:

```javascript
<div class="main full">

    {{> components/common/search-reveal }}
    {{> components/common/top-ctas }}
    {{> components/common/store-info }}
    {{> components/common/brands }}
    {{> components/common/top-categories }}
    
</div>
```

This is an example of a **layout** file. In it we see there are 5 different components being pulled in. 

Let's look at `{{> components/common/top-ctas }}`.

What Handlebars is doing here is pulling the file contents of "top-ctas" for use anywhere the script is placed. 

This powerful feature allows us to create reusable content that can be placed anywhere in our site. Write once, reuse.

The way this feature should be used is to create a modular set of components (header, footer, ctas, bannders, etc.) which can then be shared and used over multiple projects. As time and use of Stencil continues, the library of components will increase, creating a library of quickly implemented code. 


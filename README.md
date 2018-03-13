# Stencil
A handbook for those working in Big Commerce Stencil.

## Intro
Stencil is a platform, written in javascript, for selling things. The asynchronous nature of Node.js is what makes 
Stencil so quick. Instead of serving requests one at a time like the PHP backed Blueprint did, Stencil is able to serve requests in a parallistic manner. Stencil uses Handlebars.js to bring data to the DOM. Why this is great is that handlebars can be broken up into components which can be reused.

### Handlebars
Take this example:

```javascript
<div class="main full">

    {{> components/common/banner }}
    {{> components/common/top-ctas }}
    {{> components/common/store-info }}
    {{> components/common/brands }}
    {{> components/common/category }}
    
</div>
```

This is an example of a **pages** file. Page files are where we combine components to build the sections of a page. In it we see there are 5 different components being pulled in. 

Let's look at `{{> components/common/top-ctas }}`.

What Handlebars is doing here is pulling the file contents of "top-ctas" for use anywhere the script is placed. Another way to look at this is to understand the path of the file that is being pulled:

```
├── templates
│   ├── components
│   │   ├── common
│   │   |── banner.html
│   │   ├── brands.html
│   │   ├── category.html
│   │   ├── store-info.html
│   │   └── top-ctas.html
│   ├── layout
│   │   ├── base.html
│   └── pages
│       └── home.html

```
This powerful feature allows us to create reusable content that can be placed anywhere on our site. Write once, reuse.

The way this feature should be used is to create a modular set of components (header, footer, ctas, bannders, etc.) which can then be shared and used over multiple projects. As time and use of Stencil continues, the library of components will increase, creating a library of quickly implemented code. 

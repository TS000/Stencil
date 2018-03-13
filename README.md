# Stencil
A handbook for those working in Big Commerce Stencil.

## Intro
Stencil is a platform, written in javascript, for selling things. The asynchronous nature of Node.js is what makes 
Stencil so quick. Instead of serving requests one at a time like the PHP backed Blueprint did, Stencil is able to serve requests in a parallistic manner. Stencil uses Handlebars.js to bring data to the DOM. Handlebars is great because our code can be broken up into components which can be reused.

### Handlebars
Take this example:

*/templates/components/pages/home.html*

```javascript
<div class="main full">

    {{> components/common/banner }}
    {{> components/common/top-ctas }}
    {{> components/common/store-info }}
    {{> components/common/brands }}
    {{> components/common/category }}
    
</div>
```

This is an example of a **pages** file. **Pages** files are where we combine components to build the sections of a page. In it we see there are 5 different components being pulled in. 

Let's look at `{{> components/common/top-ctas }}`.

What Handlebars is doing here is pulling the file contents of "top-ctas" for use anywhere the script  
`{{> components/common/top-ctas }}` is placed. Here's a little file tree to help you understand the path of the file that is being pulled:

```
└─── templates
    ├── components
    │   └── common
    │   	|── banner.html
    │   	├── brands.html
    │   	├── category.html
    │   	├── store-info.html
    │   	└── top-ctas.html
    ├── layout
    │   ├── base.html
    └── pages
        └── home.html

```
This powerful feature allows us to create reusable content that can be placed anywhere on our site. Write once, reuse.

The way Handlebars should be used in Stencil is to create a modular set of components (header, footer, ctas, banners, etc.) which can then be shared and used over multiple projects. As the use of Stencil continues, the library of components will increase, thus creating a library of quickly implemented code.

### Styles

Styling in Stencil is through the use of Foundation 5 variables.  

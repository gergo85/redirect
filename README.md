# Adrenth.Redirect

## The #1 Redirect plugin for OctoberCMS

This is the best Redirect-plugin for OctoberCMS. With this plugin installed you can manage redirects directly from OctoberCMS' beautiful interface. Many webmasters use redirects to optimize their website for search engines. This plugin allows you to manage such redirects with a nice and user-friendly interface.

## What does this plugin offer?

This plugin adds a 'Redirects' settings section to OctoberCMS. Here you can manage your redirects. After setting up your redirects you can publish them directly to activate them.

After publishing your redirect this plugin is trying to match your redirect very efficiently before your website is rendered.

## Testing your redirects

This plugin has an easy to use test tool to extensively test your redirects before you publish them.

## Features

* **Quick** matching algorithm
* **Test** redirects before publishing
* Matching using **placeholders** (dynamic paths)
* Match placeholders using **regular expressions**
* **Exact** path matching
* **Importing** and **exporting** redirect rules
* **Schedule** redirects
* Redirect to **external** URLs
* Redirect to **internal** CMS pages

## Redirection

It is important for SEO create redirects of non-existent pages on your website. This plugin allows you to manage such redirects with a nice and user friendly user interface.

## Redirect types

This plugins ships with two types of redirects:

* **Exact**; performs an exact match on the Source path
* **Placeholders**; matches placeholders like {id} or {category} (like the defined routes in Symfony or Laravel framework)

My plan is to add more redirection types in the future.

## Redirect target types

This plugin allows you to redirect to the following types:

* An internal path
* An internal CMS Page
* An external URL

## Placeholders

A placeholder is a dynamic piece in a URL surrounded with curly braces. 
For example:

````
/my-blog/{category}/{id}
````

A placeholder can be replaced by a matched value:

````
/my-blog/hobbies/123
````

Any placeholder can be attached to a **requirement**. A **requirement** consists of a `placeholder`, `requirement` and an optional `replacement` value.

Example:

````
Request path:
/blog.php?category=cat&id=145

Redirect Rule: Source path
/blog.php?category={category}&id={id}

Redirect Rule: Target path
/blog/{category}/{id}

Result:
/blog/cat/145
````

* The requirement for `{category}` would be: `[a-zA-Z]` or could be more specific like `(dog|cat|mouse)`.
* The requirement for `{id}` would be: `[0-9]+`.

**Replacement value**

A requirement can also contain a replacement value. Provide this replacement value if you need to rewrite a certain placeholder to a static value.

Example:

The requirement for `{category}` is `(dog|cat|mouse)`, with replacement value `animals`.

````
Request path:
/blog.php?category=mouse&id=1337

Redirect Rule: Source path 
/blog.php?category={category}&id={id}

Redirect Rule: Target path
/blog/{category}/{id}

Result:
/blog/animals/1337
````

## Redirect Target

As of version 1.1.0 you can select a CMS Page as a Redirect target. Placeholders are supported. Let's asume there is a page 'Blog' with the following URL: `/blog/:category/:subcategory`. 

It is possible to create a Redirect with placeholders that has this CMS Page as a target:

````
Redirect with:
Source: `/blog.php?cat={category}&subcat={subcategory}`
Placeholders: {category}, {subcategory}
Target: CMS Page `Blog`

Request path: /blog.php?cat=news&subcat=general
Result: /blog/news/general
````

## SQLite

SQLite is not supported in version 1.0.0 - 1.0.13.

## More information

This plugin makes advantage of the `symfony/routing` package. So if you need more info on how to make requirements for your redirection URLs, please go to: [https://symfony.com/doc/current/components/routing/introduction.html#usage]()

## Contribution

If you like to contribute to this plugin feel free to create a Pull Request. But you can also contact me. My contact details can be found in the source code of this project.

## Questions? Need help?

If you have any question about how to use this plugin, please don't hesitate to contact me. I'm happy to help you.

You can also create an issue on the [GitHub](https://github.com/adrenth/redirect) page of this plugin.

Kind regards,

Alwin Drenth -- *Author of the Redirect plugin*
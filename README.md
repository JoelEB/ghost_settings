# Ghost Settings

## Capser Theme Changes

* Change Logo size by changing the max size on `.site-logo` in this file
```
sudo nano /var/www/html/joeleb.com/public_html/content/themes/casper/assets/css/screen.css
```
and this file

```sudo nano /var/www/html/joeleb.com/public_html/content/themes/casper/assets/css/screen.css.map```

* Add links to Footer  in `default.hbs` with 
```
<a href="http://github.com/joeleb" target="_blank" rel="noopener">GitHub</a>
```


* Add GitHub Icon to Floating Nav Bar

First, add font awesome link to `<head>` of `default.hbs`
```
<script defer src="https://use.fontawesome.com/releases/v5.0.6/js/all.js"></script>
```

Then, in `/var/www/html/joeleb.com/public_html/content/themes/casper/partials/site-nav.hbs`

File shoudld look like this:

```
<nav class="site-nav">
    <div class="site-nav-left">
        {{^is "home"}}
            {{#if @blog.logo}}
                <a class="site-nav-logo" href="{{@blog.url}}"><img src="{{@blog.logo}}" alt="{{@blog.title}}" /></a>
            {{else}}
                <a class="site-nav-logo" href="{{@blog.url}}">{{@blog.title}}</a>
            {{/if}}
        {{/is}}
        {{#if @blog.navigation}}
            {{navigation}}
        {{/if}}
    </div>
    <div class="site-nav-right">
        <div class="social-links">
            {{#if @blog.facebook}}
                <a class="social-link social-link-fb" href="{{facebook_url @blog.facebook}}" target="_blank" rel="noopener">{{> "icons/facebook"}}</a>
            {{/if}}
            {{#if @blog.twitter}}
                <a class="social-link social-link-tw" href="{{twitter_url @blog.twitter}}" target="_blank" rel="noopener">{{> "icons/twitter"}}</a>
            {{/if}}
                <a rel="noopener" target="blank" href="https://github.com/joeleb">
                <i class="fab fa-github fa-lg fa-fw" style="color:#CED1D4;"></i>
                 </a>
                <a rel="noopener" target="blank" href="https://www.linkedin.com/in/joeleb">
                <i class="fab fa-linkedin fa-lg fa-fw" style="color:#CED1D4;"></i>
                 </a>
                <a rel="noopener" target="blank" href="https://www.instagram.com/joel_e_b/">
                <i class="fab fa-instagram fa-lg fa-fw" style="color:#CED1D4;"></i>
                 </a>
            <a class="rss-button" href="https://feedly.com/i/subscription/feed/{{@blog.url}}/rss/" target="_blank" rel="noopener">{{> "icons/rss"}}</a>
        </div>
    </div>
</nav>

```

* Add Blog Title to Heading 

in ` /var/www/html/joeleb.com/public_html/content/themes/casper/index.hbs `

```
    {{#if @blog.logo}}
        <img class="site-logo" src="{{@blog.logo}}" alt="{{@blog.title}}" />
         <br>
         {{@blog.title}}
     {{else}}
        {{@blog.title}}
    {{/if}}
```

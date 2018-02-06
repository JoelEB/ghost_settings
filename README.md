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

Add

```
    <a rel="noopener" target="blank" href="https://github.com/joeleb">
      <i class="fab fa-github"></i>
    </a>
```


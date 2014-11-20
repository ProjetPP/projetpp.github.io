# Webpage of the PPP

The wepbage of the PPP is made using [Jekyll](http://jekyllrb.com/).

You can find more informations about the specific utilization of Jekyll with GitHub [here](https://help.github.com/articles/using-jekyll-with-pages).

To do thing more easily, [JekyllBootstrap](http://jekyllbootstrap.com/) is used.

## Using Jekyll locally

The following are some notes to myself to get Jekyll to work on my PC.
These are additional informations to the official Jekyll and GitHub help.

1. Have `ruby`, `ruby-dev` and `nodejs` packages installed.
2. When some installation does not work, try with sudo.
3. Do not forget `source 'https://rubygems.org'` in your Gemfile.

Then, run `bundle exec jekyll serve`.


## Adding links in the navigation bar

Modifies the class `navbar` in the file `_includes/themes/your_theme/default.html`.
Example:
```
    <div class="navbar">
      <div class="navbar-inner">
        <div class="container-narrow">
          <a class="brand" href="{{ HOME_PATH }}">{{ site.title }}</a>
          <ul class="nav">
            {% assign pages_list = site.pages %}
            {% assign group = 'navigation' %}
            {% include JB/pages_list %}
            <li><a href="https://github.com/ProjetPP/">GitHub</a></li>
            <li><a href="http://ppp.pony.ovh/">Ask a question</a></li>
          </ul>
        </div>
      </div>
    </div>
```

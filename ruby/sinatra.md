# Sinatra resources

## ERB views

`<% %>` without the `=` get executed but not displayed in the view

Displaying all bookmarks in the bookmarks array in index:

```
<h1>Bookmark Manager</h1>
<ol><% @bookmarks.each do |bookmark| %>
<li><a href="<%= p bookmark %>"><%= p bookmark %></a></li>
<% end %>
</ol>
```

[Intro resource](https://www.stuartellis.name/articles/erb/)

[My Sinatra and Rack notes from Makers](https://github.com/aniasobo/portfolio/blob/master/challenges/battle.md)

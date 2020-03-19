# evote-movie-2020-05-twig-base-template-inheritance

- move all common header and nav and footer content to `/templates/_base.html.twig`

    - define overridable  `title` Twig block in base template (in HTML head) `{% block title %}{% endblock %}`
    
    - define overridable `main` Twig block in base templatee `{% block main %}{% endblock %}`
        

```twig
<!doctype html>
<html lang="en">
<head>
    <title>EVOTE MOVIE - {% block title %}{% endblock %}</title>
    <meta charset="utf-8">
    <style>
        @import "/css/basic.css";
        @import "/css/nav.css";
        @import "/css/footer.css";
    </style>
</head>
<body>

<header>
    <img src="/images/smithit_logo.gif" alt="logo">
</header>

<nav>
    <ul>
        <li>
            <a href="/">Home</a>
        </li>

        etc.]

    </ul>
</nav>

{% block main %}
{% endblock %}

<footer>
    2020 &copy; A Matt Smith productions international enterprises limited production
</footer>

</body>
</html>
```

- make all other template pages extend base and override `main` Twig block, e.g. for home page `/templates/index.html.twig':

    ```twig
    {% extends '_base.html.twig' %}
    
    {% block title %}home page{% endblock %}
    
    {% block main %}
        <h1>
        Welcome to SmithIT Home Page
        </h1>
    
        <p>
        This site offers you the chance to VOTE on your favourite movies ...
        </p>
    {% endblock %}
    ```  

- NOTE: we have lost and current page nav indicator - we'll fix this soon :-)
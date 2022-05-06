This website uses a very simple templating system called tuplates. The
tuplates.py file is self-contained and has no dependencies.

To build the website, run:

```bash
python3 tuplates.py
```

The way tuplates works is it looks through all your files. Any comment lines
including `tuplate_start` or `tuplate_end` tell tuplates where to embed
snippets from other code.

For example, the HTML comments:

```html
<!-- tuplate_start(tuplates/header.html) -->
<!-- tuplate_end -->
```

Tell tuplates to find the files `tuplates/header.html` (doesn't have to be in
the `tuplates/` directory, this is just an example) and inject it's contents
between the comments. So if `tuplates/header.html` contained:

```html
<h1>Hi there</h1>
```

After running `python3 tuplates.py` the content of `index.html` would be:

```html
<!-- tuplate_start(tuplates/header.html) -->
<h1>Hi there</h1>
<!-- tuplate_end -->
```

This lets you reuse various bits of code simple by making comment blocks in
whatever language you're using. The benefit over a traditional templating
language is that index.html is always a valid HTML file that can be checked
into source control in it's production form.

The most important thing to remember is anytime you want to modify code that is
between `tuplate_start` and `tuplate_end`, you need to edit it in the correct
tuplate file and re-run `python3 tuplates.py`. Otherwise your changes will
be overwritten the next time tuplates runs.

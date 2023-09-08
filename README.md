<h1>
    WARNING: Thanks to GitHub's hostile policy the repository has migrated to
    <a href="https://gitlab.com/imn1/gruvbox-cgit">Gitlab</a>.<br>
    This repository won't be updated anymore.
</h1>


# Gruvbox theme for cgit

<p align="center">
    <img src="https://raw.githubusercontent.com/im-n1/gruvbox-cgit/master/assets/screenshot.png">
</p>

## Installation
Included CSS contains only gruvbox styles that pretty much
override cgit default styles. Therefore there are 2 possible
methods of installation:

### Separate styles file
Cgit allows you to include variable HTML block into `<head>`
with `head-include` config directive. That can be utilized 
like:

Create a new file `head_include.html` with the following content

```html
<link rel="stylesheet" type="text/css" href="/cgit-data/custom/gruvbox_theme.css">
```

and save that file to arbitrary location (cgit can access the
whole disk) but it's wise to save it to cgit app dir which
is usually `/usr/lib/cgit`. Then put the following line to
your `cgitrc` file:

```ini
head-include=/usr/lib/cgit/head_include.html
```

Create new `custom` directory inside cgit assets directory - which
usually sits in `/usr/share/cgit` or `/usr/share/webapps/cgit` - and
where your proxy should point to. Put the CSS file from this repository
to the directory so proxy (you have to use one to run cgit) can
now access that CSS file.

### One styles file
This approach is simpler but more messy. First locate your cgit main
CSS file which usually sits in `/usr/share/cgit` or `/usr/share/webapps/cgit`.
Append content of CSS file from this repository and that's is. Cgit will now
use the same CSS file so no need to change your proxy nor cgit config.

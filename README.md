## Description

`org-protocol` scans the list of filenames passed to the Emacs server for `org-protocol:/sub-protocol:/` and triggers actions associated with `sub-protocol`. `org-protocol-jekyll` realizes the `jekyll` sub-protocol to open sources of a site built with [Jekyll](http://jekyllrb.com) in Emacs for editing. `org-protocol-jekyll` has been successfully tested with Jekyll 1.0.2.

## Usage

Add the following line in the Emacs initialization file:

```lisp
(require 'org-protocol-jekyll)
```

Customizable variable `org-protocol-jekyll-alist` contains the list of Jekyll's sites, for instance,

```lisp
(setq org-protocol-jekyll-alist
      '(("Jekyll's awesome website."
         :base-url "http://jekyllrb.com"
         :permalink "pretty"
         :working-directory "/home/user/jekyll"
         :working-suffix (".md", ".markdown"))
        ("Local Jekyll's site."
         :base-url "http://localhost:4000"
         :permalink "pretty"
         :working-directory "/home/user/jekyll"
         :working-suffix (".md", ".markdown"))))
```

where

* `:base-url` is the base URL of the Jekyll's site (e.g. `http://www.example.com/project`)
* `:permalink` is the [permalink](http://jekyllrb.com/docs/permalinks) to generate URLs for the site
* `:working-directory` is the local working directory of the site
* `:working-suffix` is the acceptable suffixes for the file converted to HTML by Jekyll. `:working-suffix` can be a list of suffixes, e.g. `(".md", ".markdown")`, or one suffix, e.g. `".org"`. By default, only files with suffix `".html"` are taken into account.

## Installation

[ELPA](http://www.emacswiki.org/emacs/ELPA) affords the easy way to install `org-protocol-jekyll` for Emacs from [MELPA](http://melpa.milkbox.net) or [Marmalade Package Archive](http://marmalade-repo.org).

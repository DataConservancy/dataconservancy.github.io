# Data Conservancy Developers Website

This repository manages the content of the 
[Data Conservancy][dc] [developers website][devhome].

# Developers Documentation

## Using GitHub Pages

This [site][devhome] is managed using GitHub Pages [pages].

To use [GitHub Pages] [pages], you will need to create a
GitHub [OAuth token](https://github.com/settings/tokens) that
has the following permissions:

* _repo_
* _user:email_

Then, add the following `<server>` entry to your Maven 
`settings.xml` file:

    <server>
      <id>github</id>
      <!-- no username -->
      <password><!-- token value --></password>
    </server>

## Site Management

The content of the site is in `src/site/markdown`.  Files ending 
in `.md` are parsed as Markdown documents, and converted 
to XHTML prior to publication.  

### Edits

To make edits to site content, clone this repository. 

Check out the `maven-site` branch.  

    Unlike typical GitHub Pages sites, the HTML content of 
    this site is read from the `master` branch (not 
    `gh-pages`).  The Markdown version of the site is
    kept on the `maven-site` branch, and the GitHub
    Maven plugin commits it to `master`.

Edit the files under `src/site/markdown`.  To preview your changes, run:

    mvn clean site

The output will be in the `target/site` directory.

When you are happy with your changes, use `git` to commit them,
**providing appropriate detail with your changes** (the entire
reason these documents are managed in git is to provide provenance).

Push your changes.  

### Peer Review

**If your changes require peer review**, STOP HERE.  Point your
colleagues to your changes and iterate over their feedback.

### Publishing the site

When the changes have been approved, publish them to the [website][devhome] by
running:

    mvn clean site -Dpush

The site will be rendered and published to GitHub.

[dc]: http://www.dataconservancy.org "Data Conservancy"
[pages]: https://pages.github.com/
[devhome]: http://dataconservancy.github.io/ "Data Conservancy Developers Home"

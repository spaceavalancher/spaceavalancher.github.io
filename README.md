# IPGP generic web site

This repo can be used to construct a simple static web site for use with the Institut de Physique du Globe de Paris. It is based on Jekyll that converts markdown/yml formatted files into a static html web site. The static html web site can then be hosted on any web server, or alternatively, you can easily host your web site automatically on github. The web site uses the [al-folio theme](https://github.com/alshedivat/al-folio) with a few minor changes.

## How to modify this repo as quickly as possible

Full instructions on how to use this theme can be found on the [al-folio github repo](https://github.com/alshedivat/al-folio). Nevertheless, if you kind of know what you are doing, here is the list of files that you will need to change:

* Edit `_config.yml` to set up some of the system variables.
* Replace the `_bibliography/papers.bib` file with a bibtex file that contains all of your publications.
* Add the field `selected = {true},` to those bibtex entries that you want to appear on your home page. Also, please think of adding an `abstract` field so that this can be clicked on your web site. If you want to include a preview image, add the field `preview = {image.png}` and then add the image to the folder `assets/img/publication_preview/`.
* All of the main content for the web pages is found in the `_pages` directory. You can enable or disable each of these pages by setting the variable `nav:` to `true` or `false`.
* Edit your project pages in the folder `_projects`.
* The data for the CV page is located in the file `_data/cv.yml`.
* Change the web site images that are located in the folder `assets`.

Then, after installing all the dependencies, run this command in the root directory of your project
```
bundle exec jekyll serve
```
This will allow you to inspect your web page locally at `http://127.0.0.1:4000` and will also generate the static web site in the directory `_site`.

To serve your website on github, after you make your first commit, a branch `gh-pages` will be created with the static web pages. Under the settings for Pages, choose the Build and deployment branch to be gh-pages/root.

## For experts

There are lots of features in the al-folio theme that are not used here, like a news feed, a blog, dropdown menus, highly customizable publication formatting, etc. Please see the [example web pages](https://github.com/alshedivat/al-folio) for inspiration on what else can be done!

# Website for Ann Arbor Go Developers Meetup - A2Go

This is the static website for [a2go.org](http://a2go.org)! It is generated automatically via hugo and a github action from changes made to the [a2go/a2go](https://github.com/a2go/a2go) repository source. Edits made here directly may cause merge conflicts!

### Editting and publishing a2go.github.io

Make changes to the [a2go/a2go](https://github.com/a2go/a2go) repository source (markdown files there, nothing here!) and merge to master. 7 minutes later, our website is fully baked. Mmmm... smells delicious!

### What's in the Sauce?

We use [Hugo](https://gohugo.io) for generating the static files in this repository https://a2go.org.

The source is found in that repository's `master` branch. The static site is generated to that repository's `public` directory, which is a git submodule pointing to this repository.

As mentioned [the GitHub Pages documentation][ghorgs], you can host a organization page in addition to project pages. Here are the key differences in GitHub Pages websites for Organizations:

1. You must use a repository named `<YOUR-ORGNAME>.github.io` to host your **generated** content
2. Content from the `master` branch will be used to publish your GitHub Pages site
Your Hugo source files and the generated content are published into two different repositories.

### Wait, how did you grow the ingredients for the sauce?

1. Create a `<YOUR-ORGNAME>` (e.g. `blog`) repository on GitHub. This repository will contain Hugo's content and other source files.
2. Create a `<YOUR-ORGNAME>.github.io` GitHub repository. This is the repository that will contain the fully rendered version of your Hugo website.
3. `git clone git@github.com:<YOUR-ORGNAME>/<YOUR-ORGNAME>.git && cd <YOUR-ORGNAME>`
4. `git submodule add -b master git@github.com:<YOUR-ORGNAME>/<YOUR-ORGNAME>.github.io.git public`. This creates a git [submodule][https://git-scm.com/book/en/v2/Git-Tools-Submodules]. Now when you run the `hugo` command to build your site to `public`, the created `public` directory will have a different remote origin (i.e. hosted GitHub repository).
5. Paste your existing Hugo project into a new local `<YOUR-ORGNAME>` repository. Make sure your website works locally (`hugo server` or `hugo server -t <YOURTHEME>`) and open your browser to <http://localhost:1313>.
6. Once you are happy with the results:
    * Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to kill the server
    * cd public; git add -A; git commit -am "New Update"; git push; cd ..; git add -A; git commit -am "New Update"; git push



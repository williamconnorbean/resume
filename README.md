# How to Host your Resume on GitHub Pages

## Purpose
This README will describe the practical steps of how to host and format a resume using Markdown, GitHub Pages, and Jekyll, with an emphasis on the technical writing principles stated in Andrew Etter's book *Modern Technical Writing*.

## Prerequisites
1. This README assumes basic knowledge of how to edit a Markdown file. See [More Resources](#more-resources) below for information on how to get started with Markdown.
2. This README also assumes knowledge of how to use Git on the command line. See [More Resources](#more-resources) below for an interactive tutorial on learning the basics of command line Git.

## Instructions
### Create a GitHub Account and Repository
> GitHub will allow us to take advantage of the benefits of a distributed version control system. As Andrew Etter puts it, it will allow us to work in an offline manner, enabling concurrent and collaborative work on the same file. Furthermore, with access to a version control system like Git, there will be a clear history of changes among modified files.
1. Navigate to [GitHub](https://github.com/join) and create an account.
2. Create a new GitHub repository [here](https://github.com/new).
3. Ensure the repository name is in the following format: `<username>.github.io`, where `<username>` is your GitHub username you created in step 1.
4. Ensure the visibility of your new repository is `Public`.
5. Download the contents of this repository [here](https://github.com/williamconnorbean/williamconnorbean.github.io/archive/main.zip) and extract it to a directory on your local machine. **This will be used as an initial template for creating your resume.**
7. Commit and Push this template to your new GitHub repository.
```
$ cd [directory-created-above]
$ git init
$ git add --all
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/<username>/<username>.github.io.git
$ git push -u origin main
```

### Viewing your GitHub Pages Static Site
> Andrew Etter recommends static sites for their simplicity, security, ease of hosting, and lack of server-side dependencies. Jekyll, our static site generator, is used to abstract away complexity. According to Andrew Etter, "The basics are that you provide a static site generator with content (lightweight markup) and a theme (templated HTML and CSS), and it processes everything into a working website." This allows us to simply modify our Markdown file and let Jekyll regenerate our site.
1. Navigate to your GitHub repository settings.
2. Scroll to the bottom where you will see the heading `GitHub Pages`.
3. Select the branch `main` under `Source` and select `Save`.
3. Ensure the `Minima` theme is selected under `Theme Chooser` after saving. This theme is pulled from the `_config.yml` file in the root of the project.
4. Navigate to `https://<username>.github.io/` to view your static site.

![view-resume](/assets/view-resume.gif)

### Editing Resume and Jekyll Front Matter
> Editing the resume content is simple. This is thanks to the use of the lightweight markup language Markdown. As Andrew Etter puts it, "The entire point of lightweight markup is to make it easier to produce well-formed XML, and we need XML in order to build websites." This allows the content of your resume to remain human-readable while still allowing it to be easily processed into a static website.
1. Update `index.md` with your resume information using Markdown. Note the YAML front matter block at the top of the file, indicated by:
```YAML
---
layout: resume
---
```
This tells Jekyll to use `resume.html` as a template to wrap around the content of your resume. For more information on Jekyll layouts see [More Resources](#more-resources) below.

2. Update the `title` and `description` front matter within `_config.yml`.
```YAML
title: Connor Bean's Resume
description: >- # this means to ignore newlines
  This is my resume formatted in Markdown and deployed to GitHub
  Pages using the static site generator Jekyll.
```
These variables are used within `resume.html` to provide HTML header information. They are accessed via the global Jekyll variable `site`.

### Styling your Resume
> The separation of our CSS stylesheets from the content of the resume further reinforces Andrew Etter's recommendation to use a lightweight markup language. According to Andrew Etter, this creates a natural separation between the content and style; this is ideal for documentation being kept in version control.
1. Custom CSS can be used to style your resume via custom stylesheets in the `css` directory.
2. Sytlesheets can be added to `resume.html` by supplying a link to the custom stylesheet in the header information.
```HTML
<head>
    <link href="css/styles.css" type="text/css" rel="stylesheet" />
</head>
```
3. CSS classes can be added to `index.md` by applying `{:.classname}` to a Markdown element.
```markdown
## **Education and Awards**
{:.titles}
```
In the above example, we apply the CSS class `titles` (which is defined in `styles.css`) to the `## **Education and Awards**` Markdown element.

See [here](https://kramdown.gettalong.org/quickref.html#block-attributes) for more information on the Kramdown renderer.

## More Resources
1. [Markdown Tutorial](https://www.markdowntutorial.com/)
2. [Andrew Etter's book *Modern Technical Writing*](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
3. [Jekyll Documentation](https://jekyllrb.com/docs/)
4. [Git Tutorial](https://learngitbranching.js.org/)

## Authors and Acknowledgement
Group Members: Conner Kulbaski, Johnnus Gomez and Ayush Patel.

## FAQs
### **Why is Markdown better than a word processor?**

Markdown creates a clear separation between content and style. With a conventional word processor, the workflow often follows a pattern of styling the content as it is written. This leads to difficulties when hosting content online as there are no easy means of converting the content into its respective HTML and CSS components.

Additionally, we want our resume to be a living document within our version control system. Markdown's syntax is clean and human-readable, allowing it to live within our version control system in a manner that clearly shows our history of changes. A conventional word processor such as Microsoft Word would track our changes in a compressed collection of XML files, making it difficult to digest at a glance.

---

### **Why is my resume not showing up?**

Navigate to the settings of your GitHub repository and check the following:

1. Check that your respository name is in the following format: `<username>.github.io`.
2. Ensure your repository's visibility is set to `public`.
3. Ensure your GitHub Pages site is being built from the `master` branch.
4. Ensure your site is using the `Minima` theme.

After completing the above, you should see a green checkmark below the `GitHub Pages` section in your repository settings. Your resume should now be published at `https://<username>.github.io/`.

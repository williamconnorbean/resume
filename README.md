# How to Host your Resume on GitHub Pages

## Purpose
---
This README will describe the practical steps of how to host and format a resume using Markdown, GitHub Pages, and Jekyll, with an emphasis on the technical writing principles stated in Andrew Etter's book *Modern Technical Writing*.

## Prerequisites
---
This README starts with the assumption of the possession of a resume formatted in Markdown. See [More Resources](#more-resources) below for information on how to get started with Markdown.

## Instructions
---
### Setup
1. 

## More Resources
---
1. [Markdown Tutorial](https://www.markdowntutorial.com/)
2. [Andrew Etter's book *Modern Technical Writing*](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
3. [Jekyll Documentation](https://jekyllrb.com/docs/)

## Authors and Acknowledgement
---
Group Members: 

## FAQs
---
### **Why is Markdown better than a word processor?**

Markdown creates a clear separation between content and style. With a conventional word processor, the workflow often follows a pattern of styling the content as it is written. This leads to difficulties when hosting content online as there are no easy means of converting the content into its respective HTML and CSS components.

Additionally, we want our resume to be a living document within our version control system. Markdown's syntax is clean and human-readable, allowing it to live within our version control system in a manner that clearly shows our history of changes. A conventional word processor such as Microsoft Word would track our changes in a compressed collection of XML files, making it difficult to digest at a glance.

---

### **Why is my resume not showing up?**

Navigate to the settings of your GitHub repository and check the following:

1. Check that your respository name is in the following format: `<username>.github.io`
2. Ensure your GitHub Pages site is being built from the `master` branch.
3. Ensure your site is using the `Minima` theme.

After completing  the above checks, you should see a green checkmark below the `GitHub Pages` section in your repository settings informing you your site is published at `https://<username>.github.io/`.

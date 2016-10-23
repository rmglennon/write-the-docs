# My GitHub Pages site

## Basic terminology

You can think of a _repository_ as the folder for a project, which contains all of the component files, such as code, documentation, and examples. Open-source software uses public repositories that are visible on the GitHub website.

To work on a project, you need to make your own _branch_ of a repository, which is a parallel version that contains your changes. When you are done working, you can propose that your changes be added into the main, or _master branch_ of the project by opening a _pull request_. Other _collaborators_ who have write access to the project can review and approve your work.

## General workflow for making a website with GitHub Pages

You can follow these general instructions to make a website with GitHub Pages.

1. Create a new repository for your site.
2. Create a branch to hold your changes.
2. Add some files for your website. At a minimum, you need a file for the homepage. You can name this file index.md and use markdown formatting, or index.html and add the basic HTML page structure.
3. Open a pull request to propose adding your changes into the master branch.
4. Merge files into the master branch.
5. Go to the repository settings and enable GitHub Pages on the master branch.
6. Open browser to the page.

## Common markdown examples

`#` for headings.

Backticks around inline `code`.

Two `**` **asterisks** around bold text.

Add `_` _underscores_ for italics.

### List examples

Put items in an unordered list with hyphens, asterisks, or plus signs.

```
- Item 1
- Item 2
```

Displays like this:

- Item 1
- Item 2

Use a number with a period for ordered list items. You could use `1.` for all and they will display properly on the output.

```
1. Item 1
1. Item 2
```

Displays like this:

1. Item 1
1. Item 2

### Links and images examples

`[Text that displays in the link](https://github.com)` looks like [Text that displays in the link](https://github.com).

To add an image:

`![alt text for image](https://octodex.github.com/images/collabocats.jpg)` looks like

![alt text for image](https://octodex.github.com/images/collabocats.jpg)

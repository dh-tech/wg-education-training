+++
title = 'Organizing Your Project'
date = 2025-03-12T10:03:06-04:00
status = 'draft'
+++

# Organizing your project

For a software developer, an empty project can feel like a blank page does for a writer. There are several practical considerations, including: Where do I start? How will I add to my project as it grows? How do I organize my project so that others can contribute to it? There are no easy answers to these questions, but this lesson will provide some concrete ways to think about project organization.

A project will involve a number of components. This may include raw data, processed data, documentation, source code, and code for dependencies. The project may be developed by a team, or it may be used or maintained in the future by someone other than the original developer. With this in mind, it is important to think about how your project communicates information. File and directory names will give other developers valuable clues about where to look for the code they need to update, modify, or otherwise work with. Ideally, a project should be organized so that someone unfamiliar with the project can quickly find the information they need, whether these are datasets or functions in your code. Consistent project organization is a key component of developing [reproducible research](https://dh-tech.github.io/wg-education-training/lessons/repro_research/).

## File structures and directories

[This lesson](https://coderefinery.github.io/reproducible-research/organizing-projects/) from Code Refinery has some recommendations about you might choose to organize your project. The important points for humanist researchers are the following:

- Each project should have its own folder
- The structure of your project should be consistent. Another researcher should be able to understand your file structure without you explaining it to them.
- Your project should have a README file that explains how to run the project on a different machine.
- Different parts of the project should be in different files and/or directories.

Your project organization might look something like this:

```
impressive-project/
├── data/
|  ├── README.md
|  ├── metadata.csv
|  └── texts/
|     ├── book_a.txt
|     ├── book_b.txt
|     └── ...
├── code/
├── tests/
├── doc/
│   ├── index.rst
│   └── ...
├── .gitignore
├── CITATION.cff
├── CONTRIBUTING.md
├── dependencies.md
├── LICENSE
├── README.md
```

By using a clear organizational structure like this one, someone unfamiliar with your project will quickly be able to understand what your project is doing and how they might go about reproducing your work or building upon it for their own purposes. 

## Important aspects of project organization

### 1. Separate code from data

Data should be stored separately from the code you write to manipulate it. Depending on the size of your project, this could mean storing them in different folders, or it could mean separating them into separate repositories entirely. For particularly complex datasets, you may also consider providing separate documentation for the data.

### 2. Provide documentation

Your project should include a README that explains installation instructions and guidelines for usage. The core functions of your package should be described in this README so that new users can get working with your project quickly. It is always nice to include a full API reference as well, but it is better to use a documentation generator such as [Sphinx](https://www.sphinx-doc.org/en/master/) rather than writing this from scratch, as documentation and code can easily get out of alignment as a project grows.

### 3. Document your dependencies

Your project should contain a clear list of dependencies. How you manage this will depend on the languages the project is written in. For Python, using a package manager such as [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html) or [uv](https://docs.astral.sh/uv/) can help automate this step.

### 4. Provide a citation file

Adding a [citation file](https://citation-file-format.github.io/) helps others know how they should cite your project and will encourage others to reuse your work. the ```CITATION .cff``` file is supported by popular repositories, including Github, Zenodo, and Zotero.

## Using a framework

It may be helpful to software framework for your project to aid in organization. In addition to providing useful pre-built tools, frameworks often contained prescribed file structures that automate some of the decision making about where files or bits of code should go. Frameworks are particularly useful for web development, where complex apps may need to handle database logic, data transformation, and front-end display, though there are also frameworks available for data science and other purposes as well. 

In addition to frameworks, certain software libraries may come with conventions about how to organize code or data. It is useful to familiarize yourself with how these libraries are used in your own research community and align your practices to the practices of the community.

## Version control and project organization

Project organization presents particular challenges when it comes to version control. If you are using [version control](https://dh-tech.github.io/wg-education-training/lessons/git/)—as you hopefully are—, you want other developers to be able to see the history of the project's development. However, if you need to reorganize your project, you have to take additional care to ensure that the file's history is reflected in your project's version tree. Instead of using the GUI file explorer, your terminal's command interpreter, or your text editor's file system, you should move files through the command [```git mv```](https://git-scm.com/docs/git-mv). Additionally, changes in content should be in separate commits from changes in organization. This is a fairly advanced version control procedure that can trip up even experieced developers!

## Additional resources

- Project organization:
  - [Python package structure](https://py-pkgs.org/04-package-structure)
  - [Basics of Packaging Python Programs](https://kyleniemeyer.github.io/research-software-dev-modules/module-packaging/)
- Workflow management
  -  [Carpentries lesson](https://carpentries-incubator.github.io/singularity-introduction/")
  -  [Singularity Intro Docs](https://carpentries-incubator.github.io/singularity-introduction/)
- Tracking organization in Git:
    - [Renaming files in Git](https://www.git-tower.com/learn/git/faq/git-rename-file)
    - [Official documentation on ```git mv```](https://git-scm.com/docs/git-mv)

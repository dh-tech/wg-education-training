+++
title = 'Organizing Your Project'
date = 2025-12-11T08:03:06-04:00
status = 'draft'
author = ["David Ragnar Nelson"]
pathways = ["intro-to-software-development"]
toc = true
+++


For a software developer, an empty project can feel like a blank page does for a writer. There are several practical considerations, including: Where do I start? How will I add to my project as it grows? How do I organize my project so that others can contribute to it? There are no easy answers to these questions, but this lesson will provide some concrete ways to think about project organization.

Project organization is first and foremost an act of communicaton. Like aisle labels in a grocery store, your file and folder names ultimately help people find what they are looking for. Your project may include raw data, processed data, documentation, source code, and code for dependencies. This information may be accessed by a team, or it may be used or maintained in the future by someone other than the original developer. File and directory names will give other developers valuable clues about where to look for the code they need to update, modify, or otherwise work with. Ideally, a project should be organized so that someone unfamiliar with the project can quickly find the information they need, whether these are datasets or functions in your code. Consistent project organization is a key component of developing [reproducible research](https://dh-tech.github.io/wg-education-training/lessons/repro_research/).

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

Your project should include a ```README``` that explains installation instructions and guidelines for usage. The core functions of your package should be described in this ```README``` so that new users can get working with your project quickly. It is always nice to include a full API reference as well, but it is better to use a documentation generator such as [Sphinx](https://www.sphinx-doc.org/en/master/) rather than writing this from scratch, as documentation and code can easily get out of alignment as a project grows.

### 3. Document your dependencies

Your project should contain a clear list of dependencies. How you manage this will depend on the languages the project is written in. For Python, you may provide a ```requirements.txt``` file or a ```pyproject.toml``` file. JavaScript projects may provide a ```package.json``` file. Using a package manager such as [conda](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html) or [uv](https://docs.astral.sh/uv/) for Python, or [npm](https://www.npmjs.com/) for JavaScript, can help automate this step.

### 4. Provide a citation file

Adding a [citation file](https://citation-file-format.github.io/) helps others know how they should cite your project and will encourage others to reuse your work. The ```CITATION.cff``` file format is supported by popular repositories, including GitHub, Zenodo, and Zotero.

### 5. Follow good file naming conventions

We have all faced the dilemma of trying to find the right file from a list of file names that are either not specific enough—"draft.docx", "data.csv"—or far too specific, and not necessarily helpful—"NEHGrant2024-11-05-FINAL_NOREALLY_v5.docx". [This tutorial from the University of British Columbia Library](https://ubc-library-rc.github.io/rdm/content/01_file_naming.html) provides some helpful tips on choosing good, descriptive file names. You may also want to consider how your file names will influence how they are sorted by the system, particularly for data files or scripts that need to be run sequentially.

In addition to choosing clear file names, there may also be conventions specific to the programming language you are using. For instance, in Python, we tend to use [snake case](https://peps.python.org/pep-0008/#package-and-module-names) (```my_python_script.py```), while JavaScript developers prefer using kebab case (```my-js-script.js```).

## Organization structures

### Language-specific conventions

Your programming language may have a preferred way to organize files. This can be important—if your Python package is not organized as a package, it won't be installable via package managers!

You should familiarize yourself with the dominant conventions in your programming language of choice. For instance, Python provides two methods for organizing packages. [pyOpenSci](https://www.pyopensci.org/python-package-guide/package-structure-code/python-package-structure.html) provides a good tutorial for these two formats. In one, the package lives in a directory that shares the same name as the package:

```
my-package-repo
├──my_package
|     ├──__init__.py
|     ├──app.py
|     └── ...
├── LICENSE
├──README.md
```

In the other format, the package files are organized in a subdirectory ```src```, which contains a directory named after the package:

```
my-package-repo
├──src
|     └──my-package
|         ├──__init__.py
|         ├──app.py
|         └── ...
├── LICENSE
├──README.md
```

There are advantages to both approaches, but it is ultimately at the programmer's discretion which organization they use. You may want to look at packages you admire or use frequently in your own work and use the approach they use.

Different programming languages will approach this question differently, so it is important to spend some time familiarizing yourself with the community's best practices and standards. 

### Using a framework

It may be helpful to software framework for your project to aid in organization. In addition to providing useful pre-built tools, frameworks often contained prescribed file structures that automate some of the decision making about where files or bits of code should go. Frameworks are particularly useful for web development, where complex apps may need to handle database logic, data transformation, and front-end display, though there are also frameworks available for data science and other purposes as well. Additionally, for languages with a large number of conventions (e.g. JavaScript, PHP), choosing a framework may provide commonly used patterns that reduce the potential complexity of the application.

In addition to frameworks, certain software libraries may come with conventions about how to organize code or data. It is useful to familiarize yourself with how these libraries are used in your own research community and align your practices to the practices of the community.

## Version control and project organization

Project organization presents particular challenges when it comes to [version control](https://dh-tech.github.io/wg-education-training/lessons/git/).

### Tracking changes in organization

The whole point of version control is to track changes in the history of a project. However, if you need to reorganize your project, you have to take additional care to ensure that the file's history is reflected in your project's version tree. Instead of using the GUI file explorer, your terminal's command interpreter, or your text editor's file system, you should move files through the command [```git mv```](https://git-scm.com/docs/git-mv). Additionally, changes in content should be in separate commits from changes in organization. This is a fairly advanced version control procedure that can trip up even experieced developers!

### Working with private files

There may be files you do not want to share with the world. These may be files that contain passwords or authentication tokens, or they may include proprietary data that you legally cannot share. These can be excluded from version control in your ```.gitignore```, but they also have ramifications for project organization. For instance, if your project requires a ```variables.env``` file for private credentials, you may want to provide an example file called ```variables.env_example``` that users can copy and rename to use for their own projects. Or for data, you may want to provide a folder with basic documentation for uploading and managing data, even if you cannot provide the data itself. Making sure you identify private files early on in the process can avoid serious headaches later in the project.

## Resources

- Project organization:
  - [Python package structure](https://py-pkgs.org/04-package-structure)
  - [pyOpenSci tutorial on package structure](https://www.pyopensci.org/python-package-guide/package-structure-code/intro.html)
  - [Basics of Packaging Python Programs](https://kyleniemeyer.github.io/research-software-dev-modules/module-packaging/)
  - [File Naming](https://ubc-library-rc.github.io/rdm/content/01_file_naming.html)
  - [Projcet Tree Generator](https://woochanleee.github.io/project-tree-generator/)
- Tracking organization in Git:
    - [```.gitignore``` documentation](https://git-scm.com/docs/gitignore)
    - [Renaming files in Git](https://www.git-tower.com/learn/git/faq/git-rename-file)
    - [Official documentation on ```git mv```](https://git-scm.com/docs/git-mv)

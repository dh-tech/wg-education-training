+++
title = 'Open Sourcing Your Project'
date = 2026-05-14T10:03:06-05:00
last_updated = 2026-05-14T10:03:06-05:00
author = ["Julia Damerow"] 
reviewer = ["Connie Dowell"]
toc = true
status = 'published'
pathways = []
doi = 'https://doi.org/10.5281/zenodo.20186489'
download = 'https://zenodo.org/records/20186489/files/Damerow-DHTechET-OpenSource.pdf?download=1'
+++

Before we start talking about what to consider when you want to make your project open source, we should briefly look at what open source software is and what it means to have an open source project. Many people, when they say their code or software is open source, refer to the code being on platforms like GitHub where other people can download and use the code for their own purposes. In a general sense, this is correct. The Open Source Initiative (OSI) includes this characteristic in their [10-point definition of open source](https://opensource.org/osd): 

*The program must include source code, and must allow distribution in source code as well as compiled form. Where some form of a product is not distributed with source code, there must be a well-publicized means of obtaining the source code for no more than a reasonable reproduction cost, preferably downloading via the Internet without charge.* 

The INTERSECT training on Software Licensing provides a great brief overview of what open source is and why you would want to make your project open source, which we encourage you to read:

- [INTERSECT: What is Open Source?](https://intersect-training.org/software-licensing/what-is-open-source.html)  
- [INTERSECT: Why Choose Open Source Licensing?](https://intersect-training.org/software-licensing/why-open-source.html)

## The Basics

Let’s first talk about a common misconception:

“My code is on GitHub, so it’s open source.” 

If you put your code up on GitHub, great\! That’s the first step. If you don’t know what GitHub is, then head over to our [Git & GitHub](https://learn-dh-software-dev.org/lessons/git/) lesson to learn more about it. However, putting your code on GitHub does not mean it’s open source. Even if your GitHub repository is public, **if you don’t add an open source license, your code is not open source**. So the first steps to open source any software should be:

1. Add the code to a public repository, for instance, using a platform like GitHub or GitLab.  
2. Add an open source license to your repository.

Choosing a license can be overwhelming. OSI maintains a [list of approved open source licenses](https://opensource.org/licenses). The INTERSECT training on Software Licenses has [a lesson](https://intersect-training.org/software-licensing/choosing-license.html) worth reading on the topic. And then there is [choosealicense.com](http://choosealicense.com) that helps you navigate the jungle of open source licenses. So check those out\! Besides this, your institution might have some resources you can use to make a licensing decision, or they might even have an Open Source Program Office (OSPO) that can support you on your journey to make your software open source.

## If I open source it, will they come?

Once your code is in a public repository and has an open source license, are you done? Technically… yes, but practically… no. If you made it this far, awesome\! You can now include a link to your repository in publications so other researchers can find it. But if you want other people to use and adapt your code and maybe even contribute to its ongoing development, then unfortunately you’re far from done.

Have you ever tried to use someone else’s open source code? If so and if you were lucky, then the owner of the repository took care of documenting the structure of the repository, how to use the code, and other important information about the code. If you were not that lucky, then you might just have found potentially hundreds of files with no explanation how the files fit together, what their purpose is, or where to start. It’s a little like trying to build IKEA furniture without instructions. Chances are that you have turned away from the repository without thinking twice about it, because it seems too much of an effort to try to understand how to use or adapt the code.

To ensure that other people can understand your code, use, and adapt it, you will need to put some effort into documenting the code and the repository. Everything starts with a good [README](https://www.makeareadme.com/) file, which should be the entry point to your repository. Even if you have documentation elsewhere, **make sure that you have a README** and it points the reader to all the other places that are relevant (e.g. documentation compiled elsewhere, test or sandbox installations, etc.). The [Wikipedia article on READMEs](https://en.wikipedia.org/wiki/README) is a good place to start for a list of topics that should be included in a README.

<!-- TODO: Add link to documentation lesson here -->

## Please contribute\!

If you followed the above recommendations you now have (1) code that is publicly available (2) documentation that explains how to use your code and (3) a README that tells people where to find your documentation. This is great and would enable other researchers to use your software for their own projects. But if you want other developers to contribute, you also need to prepare your repository for this aspect. 

First, make sure that your documentation contains instructions on how to set up your code for development. What dependency manager do you use? Are there any pre-commit hooks? Are there any steps like setting up test data that need to be completed to be able to effectively develop your software? If your documentation answers these types of questions, it will make it a lot easier for someone else to contribute. And you want to make it as easy as possible so people don’t turn away frustrated.

Besides development setup instructions, you also need to tell people how you want them to contribute. Do you want them to fork your repository and make pull requests? Do you want them to email you and ask to be added to your repository? Do you want a different process? Similarly, if someone finds a bug in your software or would like a new feature added, how do you want them to tell you that? Send an email? Create a new issue? If you use issues in GitHub for example, you can utilize issue templates to specify what information you want people to provide when opening a new issue. Make sure that you describe or link to a description of your process in your README. Often there is a file [CONTRIBUTING.md](http://CONTRIBUTING.md) that contains information about how to contribute to a project.

<!-- TODO: link to planned lesson on project management with GitHub -->

## Give credit\!

Lastly, think about how you give credit to other people that contribute to your project. At what point does someone count as a maintainer? How will you recognize them? A good way of keeping track of contributors is to maintain a file called CONTRIBUTORS.md. There are also tools out there such as [All Contributors](https://allcontributors.org/) that help you keep track of contributions. 

You do not have to have final answers to these questions right from the start. It is ok to wait and see who will be willing and able to help you in your development efforts and talk to them about how they would like to be recognized for their contributions. However, it can’t hurt to be aware that these questions will likely come up eventually and to have given them some thought ahead of time.

## Building a Community

The last step, which might be the most challenging, is finding other people who want to use and contribute to your software. If you build a piece of software that others use, eventually you will have to answer the question about how it can be maintained long-term. What happens if you don’t have the time anymore to update the software or add new features to it? Will everyone who relies on it have to find a new tool? The most promising way to avoid this scenario is to build a community around your software. However, this can also be a very difficult task. First you need to get the word out and encourage other developers to contribute. Once you have found some people, you will need to define processes for decision making (e.g. who gets to decide what new features to add or what technologies to use?) and coordination (e.g. how do you decide who works on what?). There are many resources available that provide guidance and recommendations. For example, the [Open Source Guides](https://opensource.guide/) website has several articles on the topic:

- [Building Welcoming Communities](https://opensource.guide/building-community/)  
- [Finding Users for Your Project](https://opensource.guide/finding-users/)  
- [Best Practices for Maintainers](https://opensource.guide/best-practices/)  
- [Leadership and Governance](https://opensource.guide/leadership-and-governance/)

## Final Thoughts

There are many processes to be defined and set up, decisions to be made, and documents to create when making a project open source. Not everything applies to every project and not everything needs to be in place right from the start, but you should be aware of all these aspects when making the decision to create an open source project. Many projects that are open source never find any other contributors or are even maintained, many projects eventually die, but there are also many examples of very successful open source projects. It takes a lot of effort and work though, which needs to be planned for and should be considered when writing proposals to fund a project.

## Resources

- [INTERSECT Software Licensing Lesson](https://intersect-training.org/software-licensing/index.html)  
- [Open Source Initiative](https://www.gnu.org/philosophy/free-sw.en.html#four-freedoms)  
- [Open Source Guides: Starting an Open Source Project](https://opensource.guide/starting-a-project/)  
- [CodeRefinery: Social coding and open software \- What can you do to get credit for your code and to allow reuse](https://coderefinery.github.io/social-coding/)  
- [All Contributors tool](https://allcontributors.org/)  
- [CURIOSS \- A community for those working in University and Research Institution OSPOs](https://curioss.org/)  
- [Building a Better Open Source Ecosystem: Lessons from Growing the OSF Open Source Community](https://www.cos.io/blog/building-a-better-open-source-ecosystem-lessons-from-growing-osf-open-source-community)  
- [Open Source Guides](https://opensource.guide/)

# Hosting a Resume on GitHub Pages

## Purpose

___

The goal of this README is to teach the key principles of [Andrew Etter's book](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS) by demonstrating how to host a markdown resume on GitHub Pages.

## Prerequisites

___

1. A resume formatted in [markdown](https://www.markdownguide.org/getting-started/)
2. A markdown editor. I recommend [Visual Studio Code](https://code.visualstudio.com/) for its versatility
3. Jekyll. Follow Jekyll's [official installation guide](https://jekyllrb.com/docs/installation/) to install Jekyll and its dependancies
4. A [GitHub account](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account)
5. [GitHub Desktop](https://desktop.github.com/)

## Instructions

___

### Step 1: Create your GitHub Pages repository

1. Navigate to the repositories section of your GitHub profile and click on the green **new** button to create a new repository ![step 1.1](/assets/images/Step1.1.gif)
2. Make sure you title your new repository **yourgithubusername.github.io**
3. If you want to host your GitHub page for free, make sure your repository is set to **Public**
4. Click create repository to create your new GitHub Pages repository

### Step 2: Create and link a local copy of your GitHub Pages files

1. Navigate to the repository for your GitHub page and click on the green **Code** button and select **"Open with GitHub Desktop"** from the drop down menu
2. Once GitHub Desktop opens, a window will pop up with the GitHub URL, local path and a clone button. Feel free to change the local path to store the local copy of your site files somewhere else on your PC, however I recommend using the default path
3. Click on the blue Clone button to create a local copy of your files ![step 2](/assets/images/step2.gif)**Note: The Process is shown with an example Hello World repository**

### Step 3: creating a new Jekyll project

1. On GitHub Desktop click on **Open with visual studio code**
2. Click on **Terminal** and select **New Terminal** from the top task bar of VS Code
3. In the terminal, make sure the file path displayed is the same file path you chose when cloning your GitHub Pages repository and run the following command to have jekyll overwrite the existing files in the directory and create a new jekyll site with all of the necessary files and folders

```sh
jekyll new . --force
```

![Step 3](/assets/images/Step3.gif)
**Note: The Process is shown with an example Hello World repository**

### Step 4: Adding your resume to your site

There are two ways we can go about doing this

#### Option 1: Make your resume the homepage

1. Delete the file named **"index.markdown"** in your sites root directory. The root directory should be called yourgithubusername.github.io
2. create a **copy** of your resume in the root directory of your site
3. Add the following frontmatter to the very top of your resume markdown file

```yml
---
layout: "home"
---
```

4. Change the filename of your resume to **index.md**

![Step 4.1](/assets/images/Step4.1.gif)

#### Option 2: Make your resume a seperate page on your site

1. Copy your Resume.md file into the root directory of your site
2. Add the following frontmatter to the very top of your resume markdown file

```yml
---
layout: "page"
---
```

### Step 5: Preview your site locally

1. In the VS Code terminal, make sure the file path displayed is the same file path you chose when cloning your GitHub Pages repository and run the following command to start a local server to host your site

```sh
bundle exec jekyll serve 
```

2. Go to http://localhost:4000 in the browser of your choice to see your site

### Preview of Option 1

![Step 5 Option 1](/assets/images/Step5.gif)

### Preview of Option 2

![Step 5 Option2](/assets/images/Step5.1.gif)

### Step 6: Customize your configuration file

1. Open the _config.yml file in your sites root folder
2. Update the relevent fields such as follows

```yml
title: Whatever title you wish to give your site
email: youremail@hexample.com
description: >- # this means to ignore newlines until "baseurl:"
  Give a brief description of your site
baseurl: "" # the subpath of your site, e.g. /blog
url: "yourgithubusername" # the base hostname & protocol for your site, e.g. http://example.com

github_username:  yourgithubusername
```

To learn how to further customize your site or change your Jekyll theme, see the [More Resources Section](#more-resources)

### Step 7: Commit and Push your changes to github

1. Make sure you have saved all of the changes you have made to each file
2. Open GitHub desktop and select your sites repository as your current repository
3. Fill out the summary field in the bottom left of the window and click **commit** to commit all of your changes
4. Now click the blue **Push Origin** button to push all of your changes to GitHub
5. Wait for github to build your site, this could take up to 10 minutes, and view your new site in your browser at yourgithubusername.github.io

### More Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [Andrew Etter's book on modern technical writing](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
- [Mike Dane's Jekyll tutorial](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB)
- [Editing markdown in Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown)
- Indeed's [Resume guide](https://www.indeed.com/career-advice/resumes-cover-letters/how-to-make-a-resume-with-examples)
- [Jekyll's themes documentation](https://jekyllrb.com/docs/themes/)
- [Minima theme documentation and customization](https://github.com/jekyll/minima#readme)

## Authors and Acknowledgements

___

### Revisions and Editing

- [Al Fahiyan Siyam]()
- [Nurida Karimbaeva]()
- [Gurman Toor]()

### Page Theme and Templates

- [Jekyll's minima theme](https://github.com/jekyll/minima)

## FAQs

___

**Question:** Why is Markdown better than a word processor?  

**Answer:** Markdown is better than using a word processor since it is:

- Easy and quick to learn and write
- Easier to publish the web quickly as a static site
- Easier to distribute since everyone can access the same static site instead of needing a copy of the document
- Widely compatable

___
**Question:** Why is my resume not showing up?

**Answer:** There are a number of reasons that your resume might not be showing up. Make sure that:

1. Your resume is located in the root directory of your GitHub pages repository
2. An index.md file is present in your repositories root directory
3. Make sure the [visibility of your site is set to public](https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site)  

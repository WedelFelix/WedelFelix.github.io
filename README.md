# Hosting a Resume on GitHub Pages

## Purpose

The goal of this README is to teach the key principles of [Andrew Etter's book](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS) by demonstrating how to host a markdown resume on GitHub Pages.

## Prerequisites

1. A resume formatted in [markdown](https://www.markdownguide.org/getting-started/). Here is a [sample resume](Resume.md)
2. A markdown editor. I will be using [Visual Studio Code](https://code.visualstudio.com/) for this demonstration
3. Jekyll. Follow Jekyll's [official installation guide](https://jekyllrb.com/docs/installation/) to install Jekyll and its dependencies
4. A [GitHub account](https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account)
5. [GitHub Desktop](https://desktop.github.com/)

## Instructions

### Step 1: Create your GitHub Pages repository

We will be following Andrew Etter's key principle of *using distributed version control* by hosting all of our files on GitHub. This will allow us to maintain a local copy of all of our files while also making it really easy to constantly update and revise our content. Since our repository will be set to public, having our site hosted on a version control system will make it extremely easy for others to contribute

1. Navigate to the repositories section of your GitHub profile
2. Click on the green button labeled **New** to create a new repository ![step 1.1](/assets/images/Step1.1.gif)
3. Make sure you title your new repository **yourgithubusername.github.io**
4. Make sure your repository is set to **Public** if you want to host your GitHub page for free
5. Click create repository to create your new GitHub Pages repository

### Step 2: Create and link a local copy of your GitHub Pages files

1. Navigate to the repository for your GitHub page
2. Click on the green **Code** button and select **"Open with GitHub Desktop"** from the drop down menu

**Note: Once GitHub Desktop opens, a window will pop up with the GitHub URL, local path and a clone button. Feel free to change the local path to store the local copy of your site files somewhere else on your PC, however I recommend using the default path**

3. Click on the blue **Clone** button to create a local copy of your files ![step 2](/assets/images/Step2.gif)

**Note: The Process is shown with an example Hello World repository**

### Step 3: creating a new Jekyll project

We will be following Andrew Etter's key principle of *making a static website* by using the popular static website generator known as Jekyll. This will make it really simple to build and host our website for free on GitHub pages. Having your documents hosted as a static website also makes them easily accesible to others without the need to maintain multiple copies of your documents.

1. Click on **Open with visual studio code** in the GitHub Desktop app
2. Click on **Terminal** and select **New Terminal** from the top task bar of VS Code
3. Make sure the file path displayed in the terminal is the same file path you chose when cloning your GitHub Pages repository
4. Run the following command to have jekyll overwrite the existing files in the directory and create a new Jekyll site with all of the necessary files and folders

```sh
jekyll new . --force
```

![Step 3](/assets/images/Step3.gif)
**Note: The Process is shown with an example Hello World repository**

### Step 4: Adding your resume to your site

By creating our resume as a markdown file, we are following Andrew Etter's key principle of *using lightweight markup.* This will make it extremely easy to host our resume as a static site using a static site generator like Jekyll. Creating your documents as markdown files also makes them very simple to edit and update as needed

There are two ways we can go about doing this

#### Option 1: Make your resume the homepage

1. Delete the file named **"index.markdown"** in your sites root directory. The root directory should be called yourgithubusername.github.io
2. Create a **copy** of your resume in the root directory of your site
3. Add the following frontmatter to the very top of your resume markdown file

```yml
---
layout: "home"
---
```

4. Change the filename of your resume to **index.md**

![Step 4.1](/assets/images/Step4.1.gif)

#### Option 2: Make your resume a separate page on your site

1. Copy your Resume.md file into the root directory of your site
2. Add the following frontmatter to the very top of your resume markdown file

```yml
---
layout: "page"
---
```

### Step 5: Preview your site locally

1. Open the VS Code terminal
2. Make sure the file path displayed is the same file path you chose when cloning your GitHub Pages repository
3. Run the following command to start a local server to host your site

```sh
bundle exec jekyll serve 
```

4. Go to http://localhost:4000 in the browser of your choice to see your site

### Preview of Option 1

![Step 5 Option 1](/assets/images/Step5.gif)

### Preview of Option 2

![Step 5 Option2](/assets/images/Step5.1.gif)

### Step 6: Customize your configuration file

1. Open the _config.yml file in your sites root folder
2. Update the relevant fields as follows

```yml
title: Whatever title you wish to give your site
email: youremail@example.com
description: >- # this means to ignore newlines until "baseurl:"
  Give a brief description of your site
baseurl: "" # the subpath of your site, e.g. /blog
url: "yourgithubusername" # the base hostname & protocol for your site, e.g. http://example.com

github_username:  yourgithubusername
```

To learn how to further customize your site or change your Jekyll theme, see the [More Resources Section](#more-resources)

### Step 7: Commit and Push your changes to GitHub

1. Make sure you have saved all the changes you have made to each file
2. Open GitHub desktop and select your sites repository as your current repository
3. Fill out the summary field in the bottom left of the window
4. Click **commit** to commit all your changes
5. Click the blue **Push Origin** button to push all your changes to GitHub
6. Wait for GitHub to build your site, this could take up to 10 minutes, and view your new site in your browser at yourgithubusername.github.io

![Step 7](/assets/images/Step7.gif)

### More Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [Andrew Etter's book on modern technical writing](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
- [Mike Dane's Jekyll tutorial](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB)
- [Editing markdown in Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown)
- Indeed's [Resume guide](https://www.indeed.com/career-advice/resumes-cover-letters/how-to-make-a-resume-with-examples)
- [Jekyll's themes documentation](https://jekyllrb.com/docs/themes/)
- [Minima theme documentation and customization](https://github.com/jekyll/minima#readme)

## Authors and Acknowledgements

### Revisions and Editing

- [Al Fahiyan Siyam](https://github.com/alfahiyansiyam)
- [Nurida Karimbaeva](https://github.com/nuridak)
- [Gurman Toor](https://github.com/GurmanToor)

### Page Theme and Templates

- [Jekyll's minima theme](https://github.com/jekyll/minima)

### Principles followed in this guide

- [Modern Technical Writing by Andrew Etter](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)

## FAQs

**Question:** Why is Markdown better than a word processor?  

**Answer:** Markdown is better than using a word processor for several reasons, including that Markdown is:

- Easy and quick to learn and write
- Easier to publish the web quickly as a static site
- Easier to distribute since everyone can access the same static site instead of needing a copy of the document
- Widely compatible with static site generators

___
**Question:** Why is my resume not showing up?

**Answer:** There are a number of reasons that your resume might not be showing up. Make sure that:

1. Your resume is located in the root directory of your GitHub pages repository
2. An index.md file is present in your repository's root directory
3. Make sure the [visibility of your site is set to public](https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site)  

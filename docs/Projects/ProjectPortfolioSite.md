---
title: Project Portfolio Site
hide:
  - navigation
  - tags
template: comments.html
tags:
  - Software
  - HTML
  - CSS
  - Javascript
  - Markdown
  - GitHub Actions
  - Git
---

<link rel="stylesheet" href="../../assets/css/projects/project.css">

<script src="https://kit.fontawesome.com/79ff35ecec.js" crossorigin="anonymous"></script>

# Project Portfolio Site

<!--- Social Links

HTML Link Generator - https://www.websiteplanet.com/webtools/sharelink/

<span class="share" style=" color: inherit;">
<a class="fb" title="Share on Facebook" href="FACEBOOK-URL"><i class="fab fa-facebook-square"></i></a>
<a class="twitter" title="Share on Twitter" href="TWITTER-URL"><i class="fab fa-twitter"></i></a>
<a class="pin" title="Share on Pinterest" href="PINTEREST-URL"><i class="fab fa-pinterest"></i></a>
<a class="ln" title="Share on LinkedIn" href="LINKEDIN-URL"><i class="fab fa-linkedin"></i></a>
<a class="email" title="Share via Email" href="EMAIL-URL"><i class="fas fa-paper-plane"></i></a>
</span>

-->

<div style="margin-top: -0.8em;">
  <span class="abtlinks"><a href="https://teddywarner.org/About-Me/about/"><img src="https://avatars.githubusercontent.com/u/48384497" alt="Profile Picture" class="profilepic"><span class="abt" style="font-weight: 300; padding-left: 6px;"> Teddy Warner</a><span class="abt" style="font-weight: 300; padding-left: 6px;"><span class="year">| Summer, 2021 </span>| <i class="far fa-clock"></i> 6-7 minutes</span></span></span>
  <span class="share" style=" color: inherit;">
  <a class="fb" title="Share on Facebook" href="https://www.facebook.com/sharer/sharer.php?u=https://teddywarner.org/Projects/ProjectPortfolioSite/"><i class="fab fa-facebook-square"></i></a>
  <a class="twitter" title="Share on Twitter" href="https://twitter.com/intent/tweet?url=https://teddywarner.org/Projects/ProjectPortfolioSite/&text=Check%20Out%20the%20Behind%20the%20Scenes%20to%20teddywarner.org%20on"><i class="fab fa-twitter"></i></a>
  <a class="pin" title="Share on Pinterest" href="https://pinterest.com/pin/create/button/?url=https://teddywarner.org/Projects/ProjectPortfolioSite/&media=&description=Check%20Out%20the%20Behind%20the%20Scenes%20to%20teddywarner.org%20on%20https://teddywarner.org/Projects/ProjectPortfolioSite/"><i class="fab fa-pinterest"></i></a>
  <a class="ln" title="Share on LinkedIn" href="https://www.linkedin.com/shareArticle?mini=true&url=https://teddywarner.org/Projects/ProjectPortfolioSite/"><i class="fab fa-linkedin"></i></a>
  <a class="email" title="Share via Email" href="mailto:info@example.com?&subject=&cc=&bcc=&body=Check%20Out%20the%20Behind%20the%20Scenes%20to%20teddywarner.org%20on%20https://teddywarner.org/Projects/ProjectPortfolioSite/"><i class="fas fa-paper-plane"></i></a>
  </span>
</div>

---

**The behind the scenes of the site you are on right now :)**

This site relies on [MKdocs](https://www.mkdocs.org/), a static site generator is written in python to create the content of the site, as well as the [MKdocs Material Theme](https://squidfunk.github.io/mkdocs-material/) for customization. I used this same static site generator to create my [Fab Academy Documentation Site](http://fabacademy.org/2021/labs/charlotte/students/theodore-warner/), however, that site runs strictly on the [MKdocs Material Theme](https://squidfunk.github.io/mkdocs-material/) without custom alterations. This site relies on the same structure as the prior [Fab Academy Documentation Site](http://fabacademy.org/2021/labs/charlotte/students/theodore-warner/) but includes experiments with entirely custom components, and an altered [MKdocs Material Theme](https://squidfunk.github.io/mkdocs-material/). In addition to all that, it's also built and hosted through my personal [GitHub Pages](https://pages.github.com/) repo, under my personal domain. 

## Repo Setup and Cloning

To start the site I created a new [GitHub Pages](https://pages.github.com/) repo on my [GitHub](https://github.com/Twarner491) and cloned in some of my site files from my prior [Fab Academy Documentation Site](http://fabacademy.org/2021/labs/charlotte/students/theodore-warner/) (the cloned files were just so site setup files, as well as a bit of content on my Fab Academy final project to be displayed on this site). I then pulled this repo to my local system folder with the command

``` yaml linenums="1"
git clone REPO-HERE # (1)
```

1.  Replace the text `REPO-HERE` with your site repo's *Clone with SSH* link. This can be found under the *Clone* button in most Git web interfaces (i.e. Gitlab, Github, etc.).

??? question "Do I Need to Clone my Repo Locally?"

    Modern Hosting Platforms such as GitHub or GitLab allow for Repo editing to take place directly in the browser, and thus technically speaking, one does not need to pull their site Repo locally. However, browser editing eliminates the possibility of locally hosting, and thus one cannot view changes before pushing publically. Despite this, If you'd still like to work in a Browser-based editor, you may skip the *SSH Setup* and *Site Publishing* sections, and follow an editing and pushing workflow for your specific browser-based editor.

### SSH setup

To clone a Git repository locally, an SSH key must be generated on your computer and then attached to your GitHub account. GitHub has really good documentation on [creating a new SSH key](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and attaching it to your Git Web Interface (Github, Gitlab, etc.). 

The process for generating and attaching a new SSH key to your Git Web Interface is relatively pain-free when following this documentation and using the command written above. My process involved running these commands ...

``` yaml
ssh-keygen -t ed25519 -C "<Your-SSH-Name-Here>" # (1)

Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/user/.ssh/id_ed25519): # (2)

Enter passphrase (empty for no passphrase): # (3)
Enter the same passphrase again:

cat ~/.ssh/id_ed25519.pub | clip # (4)
```

1.  This generates a new SSH key on your computer.

2.  Click enter to confirm location.

3.  Enter a passphrase for your SSH key, you will need this password whenever you attempt to push your site.

4.  This copies your new SSH key to clipboard. Replace `id_ed25519.pub` with your filename. For example, use `id_rsa.pub` for RSA.

Once copied to the clipboard, you can paste the newly generated SSH key in your SSH key settings in your Git Web Interface, to link your computer and your Git Web Interface. Now you can finally clone your site Repository locally as discussed above.

## Mkdocs Material Install & Site Building

!!! abstract "Requirements"

     - Latest Version of [Python](https://www.python.org/downloads/) :warning: **Be Sure Your Python Installation is Installed to PATH in the setup wizard**
     - Latest Version of [Git](https://git-scm.com/downloads)

Open your cloned GitHub Pages repo in your code editor of choice, my personal favorite source-code editor is [Visual Studio Code](https://code.visualstudio.com/), so naturally, I used it. In a new terminal in the clone site folder, run the command

``` linenums="1"
pip install mkdocs-material
```
This will install all dependencies needed to run a static site with [MKdocs](https://www.mkdocs.org/), as well as the [MKdocs Material Theme](https://squidfunk.github.io/mkdocs-material/).

???+ warning "Note for Fab Academy Students"

    The *MKdocs Material* theme is paired with the *mkdocs-git-revision-date-localized-plugin* by default in your Fab Academy student repo. This plugin enables displaying the date of the last git modification of a page at the bottom of each page. To build your static site, this plugin must be installed in your local site folder with the line below ...

    ``` yaml linenums="1"
    pip3 install mkdocs-git-revision-date-localized-plugin
    ```

    However, one may opt to not use it via the removal of the line 

    ``` yaml
    - git-revision-date-localized
    ```

    found under the `plugins` section of your sites *mkdocs.yml* file.

Following this setup, I build my static site locally with the command in my site folders terminal

``` linenums="1"
mkdocs serve
```

and followed the link given in my computer's web browser. You should get an output like this after the *mkdocs serve* command ...

```
INFO     -  Documentation built in X.XX seconds
INFO     -  [XX:XX:XX] Serving on http://YOUR-LOCAL-SITE/
```

### Auto Site Building

!!! tip "GitHub Actions"

    The easiest way for your static site to be built in GitHub pages upon a push is through [GitHub Actions](https://github.com/features/actions) allowing for an automated workflow to run to build and pipeline your static site publicly. 


At the root of your repository, create a new GitHub Actions
workflow, e.g. `.github/workflows/ci.yml`, and copy and paste the following
contents:

``` yaml linenums="1"
name: ci # (1)
on:
  push:
     branches: # (2)
      - master
       - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
       - uses: actions/checkout@v2
       - uses: actions/setup-python@v2
         with:
          python-version: 3.x
       - run: pip install mkdocs-material # (3)
       - run: mkdocs gh-deploy --force
```

1.  You can change the name to your liking.

2.  At some point, GitHub renamed `master` to `main`. If your default branch is named `master`, you can safely remove `main`, vice versa.

3.  This is the place to install further MkDocs plugins or Markdown extensions with `pip` to be used during the build.

For my site setup, I added the line ...

``` yaml linenums="16"
- run: pip install mkdocs-git-revision-date-localized-plugin
```

... to install the Git Revision date plugin to my site, allowing for the date each page was updated to be displayed under all of the contents of the page.

## Site Customisation

The basic setup and customization of your static site are covered wonderfully on the [Mkdocs Material Theme Setup Documentation](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/). However, following this basic theme setup, your site can be altered farther by extending the [Material Theme](https://squidfunk.github.io/mkdocs-material/) -  Witch can be read about [here](https://squidfunk.github.io/mkdocs-material/customization/#extending-the-theme). All of my overrides can be found in [this site's GitHub repo](https://github.com/Twarner491/Project-Documentation-Site/).

???+ abstract "Git Pull"

    When working with other developers in a Git Repo, the Git Pull command is necessary to keep your local branch up to date with others' work. Running the line ...

    ``` yaml linenums="1"
    git pull
    ```

    will pull in any pushed changes to your repository, allowing you to merge work/changes with work from other branches.

After working on *teddywarner.org* for a couple of months, I began to develop a project template page that accumulates different front-end HTML, CSS & Markdown aspects I use on my pages, which can be found via the button below. 

<center>

[:fontawesome-brands-github: Project Page Template](https://github.com/Twarner491/Project-Documentation-Site/blob/main/docs/Projects/PROJECT-TEMPLATE.md?plain=1){ .md-button .md-button--primary}

</center>

Here I've also compiled a bit of a mkdocs markdown cheat sheet with 10 sections for customization, formatting, or additional flair. Again, the [Mkdocs Material Theme Setup Documentation](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/) covers the theme-specific markdown at length and is a nice resource while setting up specific theme-specific bits. This section compiles theme-specific markdown with overall markdown features & all of the markdowns behind it can be found in the following sections, or on this page source - linked below.

<center>

[:fontawesome-brands-github: Project Portfolio Site Source Code](https://github.com/Twarner491/Project-Documentation-Site/blob/main/docs/Projects/ProjectPortfolioSite.md?plain=1){ .md-button .md-button--primary}

</center>

### 1. Markdown Meta Data 

``` yaml
markdown_extensions:
  - meta
```

```yaml linenums="1"
---
title: PROJECT-TITLE
description: Nullam urna elit, malesuada eget finibus ut, ac tortor.
template: custom.html
hide:
  - navigation
  - toc
---
```

---
### 2. Basic Syntax 

=== "Image & Caption"

      ``` markdown
      ![alt text](imageURL.jpg){: align=right/left width="100%"}
        <figcaption>Caption</figcaption>
      ```
      <center>
        ![alt text](https://picsum.photos/600/300){width="95%"}
          <figcaption>Caption Example</figcaption>
      </center>

=== "Headings"

    ``` markdown
    # Heading 1
    ## Heading 2
    ### Heading 3
    #### Heading 4
    ##### Heading 5
    ###### Heading 6
    ```

    <center>
    <h1>Heading 1</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <h4>Heading 4</h4>
    <h5>Heading 5</h5>
    <h6>Heading 6</h6>
    </center>

=== "Hyperlink"

      ``` markdown
      [Hyperlink Example](URl)
      ```
      <center>
      [Hyperlink Example](URl)
      </center>

=== "Blockquote"

      ``` markdown
      > blockquote
      ```
      >Vivamus id mi enim. Integer id turpis sapien. Ut condimentum lobortis sagittis. Aliquam purus tellus, faucibus eget urna at, iaculis venenatis nulla. Vivamus a pharetra leo.

---
### 3. Text Formatting

``` yaml
markdown_extensions:
  - pymdownx.critic
  - pymdownx.caret
  - pymdownx.keys
  - pymdownx.mark
  - pymdownx.tilde
```

 - **Bold Text** - `**bold text**`

 - *Italicized Text* - `*italicized text*`

 - ~~Strikethrough~~ - `~~Strikethrough~~`

 - Subscript - H~2~O - `H~2~O`

 - Superscript - X^2^ - `X^2^`

---
### 4. Buttons 

``` yaml
markdown_extensions:
  - attr_list
```

  ``` markdown linenums="1"
  [Solid Button :fontawesome-solid-download:](URL){ .md-button .md-button--primary}
  [Outline Button](URL){ .md-button}
  ```

<center>

  [Solid Button :fontawesome-solid-download:](URL){ .md-button .md-button--primary}
  [Outline Button](URL){ .md-button}

</center>

---
### 5. Different List Styles

``` yaml
markdown_extensions:
  - def_list
  - pymdownx.tasklist:
      custom_checkbox: true
```

=== "Unordered List"

    "Unordered lists can be written by prefixing a line with a `-`, `*` or `+` list marker, all of which can be used interchangeably. Furthermore, all flavors of lists can be nested inside each other:" [^1]

    ``` markdown linenums="1"
    - Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
        * Nullam dignissim ultrices urna non auctor.
    - Nam vulputate tincidunt fringilla.
        * Nam vulputate tincidunt fringilla.
        * Nullam dignissim ultrices urna non auctor.
    - Nullam dignissim ultrices urna non auctor.
        * Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
    ```

    **Result -**

    - Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
        * Nullam dignissim ultrices urna non auctor.
    - Nam vulputate tincidunt fringilla.
        * Nam vulputate tincidunt fringilla.
        * Nullam dignissim ultrices urna non auctor.
    - Nullam dignissim ultrices urna non auctor.
        * Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.

=== "Ordered List"

    "Ordered lists must start with a number immediately followed by a dot. The numbers do not need to be consecutive and can be all set to `1.`, as they will be re-numbered when rendered:" [^2]

    ``` markdown linenums="1"
      1.  Vivamus id mi enim. Integer id turpis sapien. Ut condimentum lobortis
          sagittis. Aliquam purus tellus, faucibus eget urna at, iaculis venenatis
          nulla. Vivamus a pharetra leo.

          1.  Vivamus venenatis porttitor tortor sit amet rutrum. Pellentesque aliquet
              quam enim, eu volutpat urna rutrum a. Nam vehicula nunc mauris, a
              ultricies libero efficitur sed.

          2.  Morbi eget dapibus felis. Vivamus venenatis porttitor tortor sit amet
              rutrum. Pellentesque aliquet quam enim, eu volutpat urna rutrum a.

              1.  Mauris dictum mi lacus
              2.  Ut sit amet placerat ante
              3.  Suspendisse ac eros arcu
    ```

    **Result -**

      1.  Vivamus id mi enim. Integer id turpis sapien. Ut condimentum lobortis
          sagittis. Aliquam purus tellus, faucibus eget urna at, iaculis venenatis
          nulla. Vivamus a pharetra leo.

          1.  Vivamus venenatis porttitor tortor sit amet rutrum. Pellentesque aliquet
              quam enim, eu volutpat urna rutrum a. Nam vehicula nunc mauris, a
              ultricies libero efficitur sed.

          2.  Morbi eget dapibus felis. Vivamus venenatis porttitor tortor sit amet
              rutrum. Pellentesque aliquet quam enim, eu volutpat urna rutrum a.

              1.  Mauris dictum mi lacus
              2.  Ut sit amet placerat ante
              3.  Suspendisse ac eros arcu

=== "Task List"

    ``` markdown linenums="1"
    - [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
    - [ ] Vestibulum convallis sit amet nisi a tincidunt
        * [x] In hac habitasse platea dictumst
        * [x] In scelerisque nibh non dolor mollis congue sed et metus
        * [ ] Praesent sed risus massa
    - [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque
    ```

    **Result -**

    - [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
    - [ ] Vestibulum convallis sit amet nisi a tincidunt
        * [x] In hac habitasse platea dictumst
        * [x] In scelerisque nibh non dolor mollis congue sed et metus
        * [ ] Praesent sed risus massa
    - [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque

=== "Definition List"

    ``` markdown linenums="1"
    `Lorem ipsum dolor sit amet`

    :   Sed sagittis eleifend rutrum. Donec vitae suscipit est. Nullam tempus
        tellus non sem sollicitudin, quis rutrum leo facilisis.

    `Cras arcu libero`

    :   Aliquam metus eros, pretium sed nulla venenatis, faucibus auctor ex. Proin
        ut eros sed sapien ullamcorper consequat. Nunc ligula ante.

        Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
        Nam vulputate tincidunt fringilla.
        Nullam dignissim ultrices urna non auctor.
    ```

    **Result -**

    `Lorem ipsum dolor sit amet`

    :   Sed sagittis eleifend rutrum. Donec vitae suscipit est. Nullam tempus
        tellus non sem sollicitudin, quis rutrum leo facilisis.

    `Cras arcu libero`

    :   Aliquam metus eros, pretium sed nulla venenatis, faucibus auctor ex. Proin
        ut eros sed sapien ullamcorper consequat. Nunc ligula ante.

        Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
        Nam vulputate tincidunt fringilla.
        Nullam dignissim ultrices urna non auctor.

---
### 6. Content Tabs, Code Styling & Annotations 

``` yaml
markdown_extensions:
  - attr_list
  - md_in_html
  - pymdownx.superfences
  - pymdownx.highlight:
      anchor_linenums: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences
  - pymdownx.tabbed:
      alternate_style: true 
```

``` yaml
theme:
  features:
    - content.code.annotate 
```
 
=== "YAML"

    ``` yaml linenums="1" title="YAML EXAMPLE"
    theme:
      features:
        - content.code.annotate # (1)
    ```

    1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
        text__, images, ... basically anything that can be expressed in Markdown.

=== "C++"

    ``` c++ linenums="1" title="C++ EXAMPLE"
    void setup() {
      pinMode(0, OUTPUT);
    }

    void loop() {
      digitalWrite(0, HIGH); 
      delay(500);
      digitalWrite(0, LOW); 
      delay(500); 
    }
    ```

=== "Python"

    ``` py linenums="1" title="PYTHON EXAMPLE"
    import tensorflow as tf
    ```

---
### 7. Footnotes

``` yaml
markdown_extensions:
  - footnotes
```

``` markdown linenums="1"
Here's a sentence with a footnote. [^3]

[^3]: This is the footnote. 
```

Here's a sentence with a footnote. [^3]

---
### 8. Formatted Tables

``` yaml
markdown_extensions:
  - tables

```

``` markdown linenums="1"
| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |
```

<center>

| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |

</center>

---
### 9. Admonitions 

``` yaml
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
```

!!! note inline "NOTE EXAMPLE" 

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

!!! info inline end "INFO EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

!!! abstract "ABSTRACT EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.


??? tip "TIP EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? success "SUCCESS EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? question "QUESTION EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? warning "WARNING EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? failure "FAILURE EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? danger "DANGER EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? bug "BUG EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? example "EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

??? quote "QUOTE EXAMPLE"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

---
### 10. Icons & Emojis 

``` yaml
markdown_extensions:
  - pymdownx.emoji:
      emoji_index: !!python/name:materialx.emoji.twemoji
      emoji_generator: !!python/name:materialx.emoji.to_svg
```

<center>

[Icon & Emoji Search Engine :fontawesome-solid-earth-americas:](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/#search){ .md-button .md-button--primary}

</center>

``` markdown
:fontawesome-regular-laugh-wink:
```

:fontawesome-regular-laugh-wink:

``` markdown
:smile: 
```
:smile: 

---
## Site Publishing

Finally, after any changes are made to your site, you can merge your local changes back to your [GitHub Pages](https://pages.github.com/) repo to be built and published with the commands ...

``` yaml
git add . # (1)
git commit -m "Updated Site" # (2)
git push # (3)
```

1.  Stages all new changes made to your site.

2.  Gives your push a title that will be visible on GitHub

3.  Pushes changes to your GitHub - when prompted, enter your SSH password.

!!! success "Congrats!"

    You now have built your very own static site with [MKdocs](https://www.mkdocs.org/) and its [Material Theme](https://squidfunk.github.io/mkdocs-material/).

**Wooo :partying_face: :partying_face:** as of 12/01/2021, *teddywarner.org* is now **100 Commits** old!!
![](../images/PortfolioSite/100commit.jpg){width="100%"}

**200 Commits :raised_hands:** - 5/02/2022!
![](../images/PortfolioSite/200commit.jpg){width="100%"}

*[FDM]: Fused Deposition Modeling
*[CNC]: Computerized Numerical Control
*[MPCNC]: Mostly Printed Computerized Numerical Control - https://docs.v1engineering.com/mpcnc/intro/
*[SSH]: Secure Shell
*[GPIO]: General-Purpose Input/Output
*[USB]: Universal Serial Bus
*[Baudrate]: Measurement of Symbol Rate
*[ETA]: Estimated Time of Arrival
*[GCode]: A software programming language used to control a CNC machine
*[Git]: Software for tracking changes in any set of files
*[GUI]: Graphical User Interface
*[Parametric]: Parametric design is a process based on algorithmic thinking that enables the expression of parameters and rules that, together, define, encode and clarify the relationship between design intent and design response.
*[ISO]: International Organization for Standardization
*[Kreg-Jig]: A Pocket-Hole Jig
*[UPDI]: Unified Program and Debug Interface
*[AVR]: A Family of microcontrollers developed since 1996 by Atmel
*[programmer]: A piece of electronic equipment that arranges written software to configure programmable non-volatile integrated circuits
*[jtag]: Joint Test Action Group
*[IDE]: Integrated Development Environment
*[Rx]: Receiving Signal
*[Tx]: Transmitting Signal
*[VCC]: Voltage Common Collector (+)
*[GND]: Ground / Common Drain (-)
*[IC]: Integrated Circuit
*[LED]: Light-Emitting Diode
*[Cap]: Capacitor
*[SPST]: Single Pole Single Throw Switch
*[SPDT]: Single Pole Double Throw Switch
*[DPST]: Double Pole Single Throw Switch
*[DPDT]: Double Pole Double Throw Switch
*[EEPROM]: Electrically Erasable Programmable Read-Only Memory

[^1]: https://squidfunk.github.io/mkdocs-material/reference/lists/#configuration 
[^2]: https://squidfunk.github.io/mkdocs-material/reference/lists/#configuration 
[^3]: This is the footnote. 
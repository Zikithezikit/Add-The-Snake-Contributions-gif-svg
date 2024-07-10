# How to add the cool contributions snake gif

### This is a simple step by step tutorial to add the snake gif. So there will be no customisation. Go to the original repository. 


Good luck     (￣^￣ゞ

![SnakeSvg](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/github-user-contribution.svg)

## Installation

Open a new repository with your name, so for example mine is **Zikithezikit/Zikithezikit**

![Personal_repo_img](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-rep.png)

In the repository nav-bar go to actions bar

![Navbar](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-navbar-repo.png)

Click  **New workflow** 

![New workflow Image](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/ZikithezikitNewWorkflow.png)

And then click **set up workflow yourself**

![Set up workflow yourself image](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-new-workflow-yourself.png)

In here

![main-yml](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-main-yml.png)

Copy this

```sh
name: Snake generator

on:
  push:
  workflow_dispatch:
  schedule:
    - cron: "0 * * * *" #  run every hour

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Create snake
        uses: Platane/snk@v3
        with:
          # github user name to read the contribution graph from (**required**)
          # using action context var `github.repository_owner` or specified user
          github_user_name: USERNAME-HERE

          # list of files to generate.
          # one file per line. Each output can be customized with options as query string.
          #
          #  supported options:
          #  - palette:     A preset of color, one of [github, github-dark, github-light]
          #  - color_snake: Color of the snake
          #  - color_dots:  Coma separated list of dots color.
          #                 The first one is 0 contribution, then it goes from the low contribution to the highest.
          #                 Exactly 5 colors are expected.
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
            dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9


      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Replace in this code the **USERNAME-HERE** with your username (case sensitive)
Save it (Commit)
<br></br>
Now go back to actions 
![Navbar](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-navbar-repo.png)

Click on **Snake generator**
![SnakeGen](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Snakegen-img.png)

And run it
![](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-run-workflow.png)
![](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-run-workflow-Green.png)


Now go to Code

![](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-Codenavbar.png)

Switch to the output branch

![](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/blob/main/assets/Zikithezikit-outout.png)

You will hopefully see this 
![image](https://github.com/Zikithezikit/Add-The-Snake-Contributions-gif-svg/assets/80419617/8e49ab71-386c-49b5-abbc-d612b87b9ac7)

You are done 🥳 find the one you want click it and copy the URL and write this in the README file
```sh
![Snake animation](The URL from before)
```
so mine looks like this
```sh
![snake animation](https://github.com/Zikithezikit/Zikithezikit/blob/output/github-snake-dark.svg)
```

(Keywords)
How to add the snake gif to your github
How to add the snake game to git hub README readme README.md readme.md
Insert contributions snake


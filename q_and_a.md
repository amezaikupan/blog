---
layout: default
title: Q&A
---

Lessons that I'm learning in the form of Q&A. Written in no order in particular. 

* TOC
{:toc}

## What is up with `conda`?

![image is taken from [here](https://www.chiarulli.me/Miniconda/01-Install-Miniconda/)](assets/images/miniconda.jpg)

- What is `conda`?
    - It's said on the website it's an open-source package + environment management system. 
- Why use `conda`?
    - Several points (which I stole from [here](https://hackmd.io/@samumantha/conda-slides#/16)): take care of dependencies, OS independent, not only for python, open source 
- What is `mamba`? `miniforge`? `mambaforge`?
    - `mamba` is community developed and basically faster `conda` built with C++.`miniforge` and `mambaforge` is a conda distribution (I'm not sure what a conda distribution is so just gonna drop it here for now.)
- Why don't I just use `pip`?
    - (Quoting [redC from this Reddit thread](https://www.reddit.com/r/Python/comments/w564g0/can_anyone_explain_the_differences_of_conda_vs_pip/)) *conda is a system package manager. pip is a Python package manager*
    - `pip` can help with dependencies but don't do environment management. If you just use `pip` and no environment management it will just install in your global Python - meaning you're playing around with the whole system and if something break you can't just delete the thing and start over, you have to do the hard work of **fixing it**. (And of course it's gonna be a nightmare to share your project cuz you don't know what `package` you need)
- Why don't I just use `venv` + `pip`?
    - Usually, you only use `venv` + `pip` in 1 project. This means you can't reuse the `packages` you have installed before (ex. installing `numpy` 2 times for each project). And the cross-os and cross-language thing.
    - But honestly if just for small projects `venv` + `pip` is still very chill. :) 
- Why don't I just use `docker`?
    - I haven't use docker so I can't say. From what I've read it's seem to manage more than `conda` (even the OS?)
- Why use `pip` when I already have `conda`?
    - The `pip` you are using are `conda`'s`pip`. Without conda, you're using your os own python system's `pip`. When you use `pip` with `conda`, the packages is install in side `conda` directory (and not global).
    - `conda` have packages that isn't limited to python, but conda channels may lagged behind PyPI (the Python Packages Index). That's where `pip` comes in. 
    - It's intended that `conda` and `pip` are used together. 
    - For more thorough explaintaion, check [redC from this Reddit thread](https://www.reddit.com/r/Python/comments/w564g0/can_anyone_explain_the_differences_of_conda_vs_pip/) and [live coding Jeremy Howard](https://www.youtube.com/watch?v=56sIyFjihEc&list=PLfYUBJiXbdtSLBPJ1GMx-sQWf6iNhb8mM&index=1).
- Workflow with `conda`?
    - The `base` env is always active, and most of the time I just use that env. It works fine most time, so no need to change. 
    - I install stuff with `conda` and `pip` (almost python exclusively).
    - Once in a while, I checked [fastai's conda set up](https://github.com/AnswerDotAI/fastsetup/blob/master/setup-conda.sh) to see if there are new conda recommendation. If yes, I just delete the old `conda` and download the new one. 
    - Sometimes I used `venv` to check and create `requirements.txt`.

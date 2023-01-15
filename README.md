# TypingMaster

I am a slow typer, my max WPM (word per minute) is around 40 WPM.
So, I was going to write a web crawler to type quicker and "hack" speed-typing games for fun.
After doing some research, I stumbled upon a [GitHub repository](https://github.com/HuakunShen/TypingMaster) that already had the script I intended to write.
Rather than reinviting the wheel, I decided to fork my first project and improve upon it.

## Working Technology Stack
<p align="left"> 
    <a href="https://www.python.org/" target="_blank"> <img src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" alt="python" width="40" height="40"/> </a> 
    <a href="https://www.selenium.dev/" target="_blank"> <img src="https://www.selenium.dev/images/logos/webdriver.svg" alt="selenium" width="40" height="40"/> </a>
    <a href="https://chromedriver.chromium.org/downloads" target="_blank"> <img src="https://upload.wikimedia.org/wikipedia/commons/e/e1/Google_Chrome_icon_%28February_2022%29.svg" alt="chrome" width="40" height="40"/> </a>
    <a href="https://jupyter.org/" target="_blank"> <img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Jupyter_logo.svg" alt="jupyter" width="40" height="40"/> </a>
</p>

## Dependencies
* [Selenium](https://pypi.org/project/selenium/) v4.7.2 - Automating web applications
* [Webdriver-manager](https://pypi.org/project/webdriver-manager/) v3.8.5 - Library to automatically manage drivers for different browsers 

## Quick Demos
<img src="README.assets/monkey-type.gif" alt="monkey-type" />

![thumbnail-icon](README.assets/thumbnail-icon.png)

## Getting Started
```terminal
# Install dependencies
pip install selenium
pip install webdriver-manager
```

### WebDriver: ChromeDriver

The web crawler uses the Python library called `Selenium` which requires a browser `webdriver`. In this project, we selected Google Chrome as a browser, thus we needed `ChromeDriver`. Download the latest verison here: https://chromedriver.chromium.org/.

### Environment: Anaconda [Optional]

Legacy code used `Anaconda` distribution of Python with environment configuration: [environment.yml](./environment.yml). However, this is not strictly required.

```terminal
# Create a conda environment
`conda env create -f environment.yml`
```

The main library used is `Selenium`, you could also simply install `selenium` using *conda* or *pip*.

```bash
conda install -c conda-forge selenium		# install with conda
pip install selenium						# install with pip
```

### Jupyter Notebook

Written in `Jupyter Notebook` to allow for better sequencial code execution.

## Monkey Type

* [Jupyter Notebook Source Code](./monkey-type.ipynb)

* Executed for https://monkey-type.com/

## Usage

There are 4 functions/methods, you can change the value of delay and method. Each method is of different styles with different techniques. The `delay` is for making the program more natural and more like a human typer. Typing too fast could be judged as invalid.

- **The fastest method: 3**

- **The most natural method: 4**

### Method 1: one_letter_at_a_time

Find all words from the DOM, for each word and for each letter, send the letters one by one to the browser.

But since all words are extracted at once and then entered, when words used up and loading more, the program needs some time to wait for loading and do the calculation, there are lags between each iteration.

![letter-by-letter](README.assets/letter-by-letter.gif)

### Method 2: all_letters_at_a_time

Similar to Method 1.

Find all words from the DOM, construct a long string, and enter the entire string at once. After each run, some new words would be loaded and some calculation needs to be performed, so there is some lag between each iteration.

![all-letters](README.assets/all-letters.gif)

### Method 3: one_word_at_a_time

This is the fastest method. Select the active word in every iteration and enter the entire word in each iteration.

<img src="README.assets/monkey-type.gif" alt="monkey-type" />

### Method 4: one_word_letter_at_a_time

Select the active word in every iteration and pop out each letter of the word, this is the most natural (human like) way.

A `delay` of 0.02 was given to make the behavior more human-like, so that this run wasn't judged to be invalid.

![natural](README.assets/natural.gif)

## Useful Links
Web console Javascript script for `typeracer.com`: https://gist.github.com/harishanchu/6852427

## Acknowledgement

Source code forked from: https://github.com/HuakunShen/TypingMaster <br>
Youtube demo: https://youtu.be/3QJkQ7hzdRE <br>

## Disclaimer

Copyright disclaimer under section 107 of the Copyright Act 1976, 
allowance is made for “fair use” for purposes such as criticism, 
comment, news reporting, teaching, scholarship, education and research.

Fair use is a use permitted by copyright statute that might otherwise 
be infringing.

# Automaton Dashboard

This is a graphical and easy to use automation flow designer. This is especially helpful for bot platforms that need to be orchestrated. This is based on a finite state machine approach in which the modules are connected between them and are able to actuate others. It is perfect to use in asynchronous environments where events happen suddenly and there is not a linear path. The main advantage of this approach is that there are no listeners turned on and listening all the time, in this approach all the modules are turned off and are only turned on when they are called and their pre-requisites have been fulfilled.

Example: The following image shows an automated human resources system on Linkedin. It is able to find relevant candidates, add them to contacts and contact them by sending them a message. All the actions happen asynchronously because we don´t know if a candidate will accept us as a contact and we don't know when it can happen.

![alt text](https://docs.google.com/drawings/d/e/2PACX-1vRxmrx764Goir0arSdxHMNMYDGhTm_KT6NGIPNIfaD5UC-ltB4qV61PwcrbYnQRdFHfTWip60QX6bO-/pub?w=1392&h=694 "Screenshot")

## Running User Interface

* Pre-requisites
    * Node.js
    * npm
    * nvm
    
    #### refer to https://nodejs.org/en/download/package-manager/ for further information regarding installation.

* Steps
    * Go to ui/ folder in your command line.
    * Run the run.sh file

> cd ui

> ./run.sh

Open your browser and go to the given URL when the platform is up.

## Running Back End

* Pre-requisites
    * Python 2.x or 3.x
    * Selenium
      * install using pip-
      > pip install selenium
    * PhantomJS
    * MongoDB
    
* Steps
    * Go to /automation folder in your command line.
    * Run the run.sh file

> cd automation

> ./run.sh

## Getting started

* Steps
    * Go to your user interface(by default: http://localhost:9000)
    * Click on Diagram on the left-side menu
    * Click on execute 
    
 If you are using firefox web browser you may encounter an error like  
 
 > "WebDriverException: Message: 'geckodriver' executable needs to be in PATH"
 
 In such a case, download the latest version of geckodriver from [here](https://github.com/mozilla/geckodriver/releases)
 
 * If you are using ubuntu just do the following after the download:
   
 > export PATH=$PATH:/path/to/directory/of/executable/downloaded/in/previous/step     
 
 * If using windows, then you can check [this](https://www.windows-commandline.com/set-path-command-line/) to know how to set path in Windows command prompt.

## Guide to creating your own bot

In order to automate any of your own desired task you need to create a `logic.json` file and corresponding modules.

* The `logic.json` gives the bot all related inputs and also specifies the order of running modules. You can have a look at the present logic.json present in the automation folder.

* Each module must have imported the `Module.py` file present in the core folder and must have the functions `run()` and `run_queue()`. The `run_queue()` function is responsible for performing operations over the data and for calling the next module. You can have a look at the modules present in the `modules` folder for reference.

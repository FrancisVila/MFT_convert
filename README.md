# About this repo

This is a trial for publishing SecureTransport docs with markdown, and also other MFT products. It is branched off the Axway-Open-Docs initiative.

## How to clone and launch on your PC

To try out this repo locally on your computer:

1.	Prerequisites: you will need

	- **nodejs**      
     `node -v` to know whether you already have it.  
     If not, [https://nodejs.org/en/download/](https://nodejs.org/en/download/) 

     - **hugo**  
     `hugo --help` to know whether you already have it.  
     If not, https://gohugo.io/getting-started/installing/  
     (Thisgives instructions for Windows, Linux and IOS. Requires you to have [Chocolatey](https://chocolatey.org/)  or [Scoop](https://scoop.sh/) installed)

     - **git**  
     Of course :-)   

1.	Clone the repo with the command:

     `git clone https://github.com/FrancisVila/MFT_convert --recursive`  
     If that does not work, contact me for authorization (fvila@axway.com)
	 
1.  Then go to the `MFT_convert/` folder, and update the node_modules

     `cd MFT_convert`  
     `npm i`

1. Still in `MFT_convert/`, launch the Hugo server 

     `hugo server`

1. If all went well, the docs should be accessible in 

     [localhost:1313/docs/](localhost:1313/docs/)


## Contribute

We welcome your contributions! To get started, go to <https://axway-open-docs.netlify.com/> and click **Documentation** in the top menu. Browse the documentation and use the options in the right navigation to edit any page using GitHub or Netlify CMS.

Before you start contributing, please read the [contribution guidelines](https://axway-open-docs.netlify.com/docs/contribution_guidelines/).

## Some more info

This is a docs-as-code implementation for Axway documentation. It is built using [Hugo](https://gohugo.io/) static site generator with the [Google Docsy](https://github.com/google/docsy) theme. The site is deployed on Netlify at <https://axway-open-docs.netlify.com/>

This repository contains all files for building and deploying the site. The Markdown files for the documentation are stored at `/content/en/docs`.

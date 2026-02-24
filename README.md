# nikola-websites
Notes on Nikola websites on Github

## Nikola

[Nikola](https://getnikola.com/) is an application written in Python that is used to build static websites. In normal use Nikola is downloaded to your PC. Webpages for a website are written in Markdown text. When Nikola is run it converts the Markdown to html and builds a website. This can be tested with Nikola's webserver feature, or deployed to a website hosting provider. This website creation process is somwhat complex, so it can be perfomed more simply by using Github.

On Github Nikola also have an account and their website creation application is available to users who have accounts on Github. Upon *Committing* and changes to a web-page in the Srv branch, the Nikola application is automatically run as a *workflow*. Nikola will build the website in the Main branch. This Main branch becomes the website on Github.
For example the Github user **kanako-web** logs into their Github account and creates the repository **kanako-web.github.io**. They set up this repository to have both *Main* and *Src* branches. The website pages are created and placed in the *Src* branch. The workflow tool gets the Nikola application to build the website. From a browser you connect to **https://kanako-wen.github.io** to view the website.





# nikola-websites
Notes on Nikola websites on Github

## Nikola

[Nikola](https://getnikola.com/) is an application written in the Python programing language that builds static websites. 

In normal use *Nikola* is downloaded to your PC. Webpages for a website are written in *Markdown* text. When *Nikola* is run it converts the *Markdown* to html and builds a website. The new website may be tested with *Nikola's* webserver feature, or deployed to a website hosting provider. This website creation process is somewhat complex, so it can be perfomed more simply by using *Github*.

*Nikola* have an account on *Github* and their website creation application is available to users who have accounts on *Github*. Upon *Commit*ting to changes you have made to a webpage in the **srv** branch, the Nikola application is automatically run as a *workflow*. Nikola will build the website in the **main** branch. This main branch then becomes the website on Github.

For example the Github user **kanako-web** logs into their Github account and creates the repository **kanako-web.github.io**. They set up this repository to have both *main* and *src* branches. The website pages are created and placed in the *src* branch. The workflow tool uses the *Nikola* application to build the website. From a browser you connect to **https://kanako-web.github.io** to view the website.

Additionally the Github user **kanako-web** has an *Organization* this is **kanako-online**. Another Nikola website can be created from the kanako-online organization. From a browser you connect to **https://kanako-online.github.io** to view the website.

## Markdown

Webpages are sent from a server to the browser on your PC as hyper-text markup language (html). It can be difficult to read and edit html. For example having a sentence with bold text would look like this: 
```
<p>This is <strong>bold</strong> text.</p>
```
and display on your browser as: This is **bold** text.

Using Markdown it is simplier to enhance a document. For example the above would be:
```
This is **bold** text.
```
In summary all web-pages are initially markdown files with a **.md** suffix to the file name. The Nikola application converts each Markdown file to an html web-page.

## Src branch of Github Repository

The Kanako-Animals website is a simple website that demonstrates how the Nikola builds the website from Markdown files written in Japanese. The Nikola source files for this website are located at: 

https://github.com/kanako-online/kanako-online.github.io/blob/src/README.md

The Kanako-Animals website can be viewed at:

https://kanako-online.github.io

The **src** branch of the Kanako Animals website, has the following tree structure. This shows the directories and files that are used by the Nikola application to build the website...

```
src <-- Source files used by the Nikola application to build the web-site in Main 
│
├── pages                          <-- Top Directory for the Markdown files that become web-pages.
│   ├── bird                       <-- Sub Directory for the Markdown file on birds.
│   │   └── bird.md                <-- Markdown file on birds that is used to create the webpage.
│   ├── cat                        <-- Sub Directory for the Markdown file on cats.
│   │   └── cat.md                 <-- Markdown file on cats that is used to create the webpage.
│   ├── dog                        <-- Sub Directory for the Markdown file on dogs.
│   │   ├── dog-black.md           <-- Markdown file on black dogs that is used to create the webpage.
│   │   ├── dog-introduction.md    <-- Markdown file to introduce the 4 x dogs. It is used to create the webpage.
│   │   ├── dog-puppy.md           <-- Markdown file on puppies that is used to create the webpage.
│   │   ├── dog-spot.md            <-- Markdown file on spotted dogs that is used to create the webpage.
│   │   └── dog-white.md           <-- Markdown file on white dogs that is used to create the webpage.
│   ├── mouse                      <-- Sub Directory for the Markdown file on the mouse.
│   │   └── mouse.md               <-- Markdown file on the mouse that is used to create the webpage.
│   │
│   ├── about.md                   <-- Markdown file about the website that is used to create the webpage.
│   ├── download.md                <-- Markdown file on downloading that is used to create the webpage.
│   └── index.md                   <-- Markdown file which is the Home page. Used to create the Home webpage.
│
│
├── images                         <-- Top Directory for all the images on the web-site.
│   ├── bird                       <-- Sub Directory for the images on birds
│   │   └── bird-fantail.jpg       <-- Image file of the bird.
│   ├── cat                        <-- Sub Directory for the images on cats
│   │   ├── cat.jpg                <-- Image file of the cat.
│   │   └── kitten.jpg             <-- Image file of the kittens.
│   ├── dog                        <-- Sub Directory for the images on dogs.
│   │   ├── dog-black.jpg          <-- Image file of the black dog.
│   │   ├── dog-puppy.jpg          <-- Image file of the puppy dog.
│   │   ├── dog-spot.jpg           <-- Image file of the spotted dog.
│   │   └── dog-white.jpg          <-- Image file of the white dog.
│   ├── mouse                      <-- Sub Directory for the images of the mouse.
│   │   └── mouse.jpg              <-- Image file of the mouse.
│   │
│   ├── favicon-cat.svg            <-- Image of cats face that is placed in the browsers tab.
│   └── logo.svg                   <-- Image of a cat that is the logo in each web-page header section.
│
│
├── files                          <-- Top Directory for additional files used.
│   ├── assets                     <-- Sub Directory.
│   │   └── css                    <-- Sub Sub Directory.
│   │       └── custom.css         <-- Cascading Style Sheets file that sets the colours, etc. for the website.
│   └── pdf
│       └── test-ja.pdf            <-- A Japanese pdf file to test that the download feature is working.
│
├── conf.py                        <-- Python programming language file used to configure the website.
│
└── .github                        <-- Directory
    └── workflows                  <-- Sub Directory
        └── main.yml               <-- Yaml command file that runs Nikola and rebuilds the website after every change is committed.



```


```
src branch tree.
│
├── .github                        <-- Directory 
│   └── workflows                  <-- Directory
│       └── main.yml               <-- File that is executed to request Nikola application to update the website   
│
├── conf.py                        <-- Python configuration file. Setup Navigation, etc. 
│
├── files                          <-- Directory
│   ├── assets                     <-- Directory
│   │   └── css                    <-- Directory
│   │       └── custom.css         <-- Cascading Style Sheets file. Sets colours and font size, etc.
│   │
│   ├── index.html                 <-- Initial html webpage. Used to select English or Japanese website.
│   │
│   └── pdf                        <-- Directory containing pdf files
│       ├── test-en.pdf            <-- English pdf file used to test downloading of file.
│       └── test-ja.pdf            <-- Japanese pdf file used to test downloading of file.
│
├── images                         <-- Directory containing all the images used in the webpages.
│   ├── favicon-cat.svg            <-- Cat image used in the browser tab.
│   ├── logo.svg                   <-- Cat image used for the logo.
│   │
│   └── uni                        <-- Directory with the images regading the university.
│       ├── uni-pa-2.webp          <-- Image of The Pa.
│       └── uni-pa.jpeg            <-- Smaller image of The Pa.
│
└── pages                          <-- Directory containing all the webpage Markdown (.md) files.
    ├── about.en.md                <-- Markdown webpage for About in English
    ├── about.ja.md                <-- Markdown webpage for About in Japanese
    ├── download.en.md             <-- Markdown webpage for Download in English
    ├── download.ja.md             <-- Markdown webpage for Download in Japanese
    ├── index.en.md                <-- Markdown webpage for Index in English. For the Home page
    ├── index.ja.md                <-- Markdown webpage for Index in Japanese. Gor the Home page
    │
    ├── english                    <-- Directory for the webpage English Course markdown (.md) files.
    │   ├── english-course.en.md   <-- Markdown webpage on English Course in English
    │   └── english-course.ja.md   <-- Markdown webpage on English Course in Japanese
    │
    ├── hamilton                   <-- Directory for the webpages on Hamilton. This has a drop-down menu.
    │   ├── bus.en.md              <-- Markdown webpage on the Hamilton buses in English
    │   ├── bus.ja.md              <-- Markdown webpage on the Hamilton buses in Japanese
    │   ├── city.en.md             <-- Markdown webpage on the city of Hamilton in English
    │   ├── city.ja.md             <-- Markdown webpage on the city of Hamilton in Japanese
    │   ├── shop.en.md             <-- Markdown webpage on the Shopping in English
    │   ├── shop.ja.md             <-- Markdown webpage on the Shopping in Japanese
    │   ├── train.en.md            <-- Markdown webpage on the Train to Auckland in English
    │   └── train.ja.md            <-- Markdown webpage on the Train to Auckland in English
    │
    ├── travel                     <-- Directory for the webpage on Travelling to places near Hamilton.
    │   ├── travel.en.md           <-- Markdown webpage on travelling to places near Hamilton in English
    │   └── travel.ja.md           <-- Markdown webpage on travelling to places near Hamilton in Japanese
    │
    └── uni                        <-- Directory for the webpage on Waikato University.
        ├── waikato-uni.en.md      <-- Markdown webpage Waikato University in English
        └── waikato-uni.ja.md      <-- Markdown webpage Waikato University in English

14 directories, 30 files

```

## Configuration file conf.py

The conf.py file is in the **scr** top-level directory.

The conf.py file is used by the Nikola application to configure the website. The following are some of the configuration items:

* Navigation titles and the files they navigate to.
* Website name.
* Filename of the website logo.
* Filename of the website favicon. The image used in the Browser tab to identify the website.

A Python dictionary is defines for configuring the Navigation links. (Around line 160)
```
NAVIGATION_LINKS = {
    DEFAULT_LANG: (
    #"ja": (
        ('/ja/index.html', '🏠'),
        (        
            (
                #('/ja/hamilton/introduction/', '導入'),
                ('/ja/hamilton/city/', '市'),
                ('/ja/hamilton/bus/', 'バス'),
                ('/ja/hamilton/train/', '電車'),
                ('/ja/hamilton/shop/', '買い物'),                
            ),
            'ハミルトン'
        ),
        ("/ja/uni/waikato-uni/", "ワイカト大学"),
        ("/ja/english/english-course/", "英語コース"),
        ("/ja/travel/travel/", "旅行"),
        ("/ja/download/", "ダウンロード"),
        ("/ja/about/", "詳細"),
    ),    

    "en": (
        ('/en/index.html', '🏠'),
        (
            (
                # ('/en/hamilton/introduction/', 'Introduction'),
                ('/en/hamilton/city/', 'City'),
                ('/en/hamilton/bus/', 'Bus'),
                ('/en/hamilton/train/', 'Train'),
                ('/en/hamilton/shop/', 'Shopping'),
            ),
            'Hamilton'
        ),
        ("/en/uni/waikato-uni/", "Waikato University"),
        ("/en/english/english-course/", "English Course"),
        ("/en/travel/travel/", "Travel"),        
        ("/en/download/", "Download"),
        ("/en/about/", "About"),
    ),

}
```
TODO: Show how to change to a website about animals.

The logo (around line 430)...
```
LOGO_URL = '/images/logo.svg'
```

The favicons (around line 1000)...
```
FAVICONS = (
     ("icon", "/images/favicon-cat.svg", "16 x 16"),
     ("icon", "/images/favicon-cat.svg", "24 x 24"),
     ("icon", "/images/favicon-cat.svg", "32 x 32"),     
)
```

Website title, in Japanese and English...
```
BLOG_TITLE = {"ja": "氏名", "en": "Kanako", }
```

Default language (Around line 110) 
```
# What is the default language?
DEFAULT_LANG = "ja"
#DEFAULT_LANG = ""
```

Support for more than one language
```
# What other languages do you have?
# The format is {"translationcode" : "path/to/translation" }
# the path will be used as a prefix for the generated pages location
TRANSLATIONS = {
    DEFAULT_LANG: "./ja",
    "en": "./en",
}
```

## Change Website

Change website from information on Hamilton and Waikato University to an Animals website, but keep support for two languages. Example of the src branch tree for Animals website
```
├── .github 
│   └── workflows
│       └── main.yml
│
├── conf.py
│
├── files
│   ├── assets
│   │   └── css
│   │       └── custom.css
│   │
│   ├── index.html <-- Edit the html to show website is about Animals.
│   │
│   └── pdf
│       ├── test-en.pdf
│       └── test-ja.pdf
│
├── images
│   ├── favicon-cat.svg
│   ├── logo.svg
│   │                     <-- Changes are to the files and directories below
│   └── cat             
│       ├── cat.webp
│       └── kitten.jpeg
│
└── pages
    ├── about.en.md
    ├── about.ja.md
    ├── download.en.md
    ├── download.ja.md
    ├── index.en.md
    ├── index.ja.md
    │
    ├── bird
    │   ├── bird.en.md
    │   └── bird.ja.md
    │
    ├── dog
    │   ├── puppy.en.md
    │   ├── puppy.ja.md
    │   ├── black-dog.en.md
    │   ├── black-dog.ja.md
    │   ├── white-dog.en.md
    │   ├── white-dog.md
    │   ├── spots-dog.en.md
    │   └── spots-dog.ja.md
    │
    ├── mouse
    │   ├── mouse.en.md
    │   └── mouse.ja.md
    │
    └── cat
        ├── cat.en.md
        └── cat.ja.md
```

Change website Animals website in Japanese and English to just using one language. Example of the src branch tree
```
├── .github 
│   └── workflows
│       └── main.yml
│
├── conf.py
│
├── files
│   ├── assets
│   │   └── css
│   │       └── custom.css
│   │
│   ├── index.html  <-- This file can be removed as there is no need to select languages.
│   │
│   └── pdf
│       ├── test-en.pdf
│       └── test-ja.pdf
│
├── images
│   ├── favicon-cat.svg
│   ├── logo.svg
│   │                     <-- Changes are the files and directories below
│   └── cat             
│       ├── cat.webp
│       └── kitten.jpeg
│
└── pages
    ├── about.md
    ├── download.md
    ├── index.md
    │
    ├── bird
    │   └── bird.md
    │
    ├── dog
    │   ├── puppy.md
    │   ├── black-dog.md
    │   ├── white-dog.md
    │   └── spots-dog.md
    │
    ├── mouse
    │   └── mouse.md
    │
    └── cat
        └── cat.md
```        

The navigation links would change to be like this...
```
NAVIGATION_LINKS = {
    DEFAULT_LANG: (
        ('/index.html', '🏠'),
        (        
            (
                ('/dog/puppy/', '子犬'),
                ('/dog/black-dog/', 'ブラックドッグ'),
                ('/dog/white-dog/', 'ホワイトドッグ'),
                ('/dog/spot-dog/', 'スポッティ・ドッグ'),
            ),
            '犬'
        ),
        ("/cat/cat/", "猫"),
        ("/bird/bird/", "鳥"),
        ("/mouse/mouse/", "ねずみ"),
        ("/download/", "ダウンロード"),
        ("/about/", "詳細"),
    ),    
}
```

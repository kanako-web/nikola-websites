# nikola-websites
Notes on Nikola websites on Github

## Nikola

[Nikola](https://getnikola.com/) is an application written in Python that is used to build static websites. In normal use Nikola is downloaded to your PC. Webpages for a website are written in Markdown text. When Nikola is run it converts the Markdown to html and builds a website. This can be tested with Nikola's webserver feature, or deployed to a website hosting provider. This website creation process is somwhat complex, so it can be perfomed more simply by using Github.

On Github Nikola also have an account and their website creation application is available to users who have accounts on Github. Upon *Committing* and changes to a web-page in the Srv branch, the Nikola application is automatically run as a *workflow*. Nikola will build the website in the Main branch. This Main branch becomes the website on Github.
For example the Github user **kanako-web** logs into their Github account and creates the repository **kanako-web.github.io**. They set up this repository to have both *Main* and *Src* branches. The website pages are created and placed in the *Src* branch. The workflow tool gets the Nikola application to build the website. From a browser you connect to **https://kanako-wen.github.io** to view the website.


## Src branch

In the **src** branch, the following tree structure shows the directories and files that are used by the Nikola application to build the website

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


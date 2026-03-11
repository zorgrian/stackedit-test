# Welcome to StackEdit!

This is a **Proper English** version of a **Guide to using StackEdit**. You can read this guide if you want to learn more about StackEdit. If you would like to experiment with Markdown, you can edit this file. Once you have finished with it, you may create new files by opening the **file explorer** on the left corner of the navigation bar ⇾ **Don't banjax it up.**


# Files

**StackEdit** stores your files in your browser's memory, which means all your files are automatically saved locally and are accessible **offline!** 

This is a **bummer**, as it totally wastes your browser's space. Then you will have to go and purge that rubbish, as it **will** accumulate.

## Create files and folders

The file **explorer** is accessible using the button in the left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

## Navigate to another file

All your files and folders are presented as a tree in the file explorer. You can switch from one to another by clicking a file in the tree.

## Rename a file

You can rename the current file by clicking the file name in the navigation bar or by clicking the **Rename** button in the file explorer.

## Delete a file

You can delete the current file by clicking the **Remove** button in the file explorer. The file will be moved into the **Rubbish** folder and automatically deleted after 7 days of inactivity.

## Export a file

You can export the current file by clicking **Export to disk** in the menu. You can choose to export the file as plain Markdown, as HTML using a Handlebars template, or as a PDF.

## Copy to Typora, or another Markdown editor

Use the source-code, which is on the left-hand pain. Do control+A, and then do control+C. The entire contents of the source-code are then in your clipboard. Once in Typora, use control+V. In other words, this works like any other system on a computer.


# Synchronisation

Synchronisation is one of the biggest features of StackEdit. It enables you to synchronise any file in your workspace with other files stored in your **Google Drive**, your **Dropbox** and your **GitHub** accounts. This allows you to keep writing on other **devices[^dev]**, collaborate with people you share the file with, integrate easily into your workflow... The synchronisation mechanism takes place every minute in the background, downloading, merging, and uploading file modifications. **Note:** Google Drive doesn't work properly. You'll never find those files again, and they slip away, or seemingly so, as the files waste your browser's memory.

There are two types of synchronisation, and they can complement each other:

- The workspace synchronisation will sync all your files, folders and settings automatically. This will allow you to fetch your workspace on any other device.
	> To start syncing your workspace, just sign in with Github in the menu.

- The file synchronisation will keep one file of the workspace synced with one or multiple files in **Google Drive**, **Dropbox** or **GitHub**.
	> Before starting to sync files, you must link an account in the **Synchronize** sub-menu.

## Open a file

You can open a file from **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronise** sub-menu and clicking **Open from**. Once opened in the workspace, any modification in the file will be automatically synced.

## Save a file

You can save any file of the workspace to **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronise** sub-menu and clicking **Save on**. Even if a file in the workspace is already synced, you can save it to another location. StackEdit can sync one file with multiple locations and accounts.

## Synchronise a file

Once your file is linked to a synchronised location, StackEdit will periodically synchronise it by downloading/uploading any modification. A merge will be performed if necessary and conflicts will be resolved.

If you have just modified your file, and you want to force syncing, click the **Synchronise now** button in the navigation bar.

> **Note:** The **Synchronise now** button is disabled if you have no file to synchronise.

## Manage file synchronisation

Since one file can be synced with multiple locations, you can list and manage synchronised locations by clicking **File synchronisation** in the **Synchronise** sub-menu. This allows you to list and remove synchronised locations that are linked to your file.


# Publication

Publishing in StackEdit makes it simple for you to publish online your files. Once you're happy with a file, you can publish it to different hosting platforms like **Blogger**, **Dropbox**, **Gist**, **GitHub**, **Google Drive**, **WordPress** and **Zendesk**. With [Handlebars templates](http://handlebarsjs.com/), you have full control over what you export.

> Before starting to publish, you must link an account in the **Publish** sub-menu.

## Publish a File

You can publish your file by opening the **Publish** sub-menu and by clicking **Publish to**. For some locations, you can choose between the following formats:

- Markdown: publish the Markdown text on a website that can interpret it (**GitHub,** for instance),
- HTML: publish the file converted to HTML via a Handlebars template (on a blog, for example).

## Update a publication

After publishing, StackEdit keeps your file linked to that publication, which makes it easy for you to re-publish it. Once you have modified your file, and you want to update your publication, click on the **Publish now** button in the navigation bar.

> **Note:** The **Publish now** button is disabled if your file has not been published yet.

## Manage file publication

Since one file can be published to multiple locations, you can list and manage publish locations by clicking **File publication** in the **Publish** sub-menu. This allows you to list and remove publication locations that are linked to your file.

## Make a new horizontal line

**Put this `***` where you want to make one, for the `*` token can't be confused with other tokens.**

A new horizontal line has been inserted below, and it uses the syntax shown above.

***

# Markdown extensions

StackEdit extends the standard Markdown syntax by adding extra **Markdown extensions**, providing you with some nice features.

> **ProTip:** You can disable any **Markdown extension** in the **File properties** dialog.


## SmartyPants

SmartyPants converts ASCII punctuation characters into "smart" typographic punctuation HTML entities. **For example:**

|                |ASCII                          |HTML                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|


## KaTeX

**You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/):**

**This is called inline syntax:**

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

**This is called display syntax:**

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> You can find more information about **LaTeX** mathematical expressions [here](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).
> This will almost cerainly be in **YankSide** English, which isn't actually English at all.

## UML diagrams

You can render UML diagrams using [Mermaid](https://mermaidjs.github.io/). **For example, this will produce a sequence diagram:**

```mermaid
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
```

**And this will produce a flow chart:**

```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgyODM1OTk4NSwtMTQzNjIzMjA5OF19
-->
# Smart Folders

A Smart Folder is a special kind of document 
gathers together all the documents with a specific 
tag.  The smart folder listed below is titled 
*Physics Notes.*  It gathers together all the 
documents with tag `"physicsnotes"`

![Smart Folder](https://i.ibb.co/QMdphTG/image.png)


## Making a smart folder

To make a smart folder, click on the **Folder** button
in the header, then fill out the form you see in the 
screenshot below: give the folder a name, .eg., 
*Physics Notes*, and give it a tag, e.g., "physicsnotes"

![Smart Folder - Make](https://i.ibb.co/zmp2pyj/image.png)

## Putting a document in a smart folder


We put a document into a smart folder by tagging it.
For example, the example document displayed above 
begins like this:

```text
\title{Entropy}

\tags{jxxcarlson:entropy, folder:physicsnotes}
```

The tag `folder:physicsnotes` is the tag that puts this
document into the given folder. In the L0 markup
language, you would write


```text
| title Entropy

[tags jxxcarlson:entropy, folder:physicsnotes]
```

Tags must be separated by commas.




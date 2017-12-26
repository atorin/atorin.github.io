.. title: How to translate a document or review a translation with OmegaT
.. slug: omegat-quick-start
.. date: 2017-12-26 15:00:00 UTC+01:00
.. tags: omegat, translation, cat tools
.. category: 
.. link: 
.. description: 
.. type: text


You want to translate a document or you're given someone else's translation to review. You also want to do it like a pro, i.e., using a professional `CAT tool <https://en.wikipedia.org/wiki/Computer-assisted_translation>`_. 

Then, you're best option is probably `OmegaT <http://omegat.org/>`_. OmegaT is a translation memory application that has, in my opinion, two main advantages over its competitors:

1. It's free and open-source,

2. It runs on Windows, Mac and Linux (actually, any system where the Java Runtime Environment can be installed). 

I found myself in this situation recently, so I'll give you a brief account based on my experience on how to import, translate and review translations for plain text files. 

.. TEASER_END

But first things first...


Install OmegaT
--------------

To get your copy of the program, head to `download web page <http://omegat.org/download>`_ and choose the link according to your operating system. Make sure you scroll down and choose the latest version (> 4.1), as some options are not present in the previous versions. 


Create a project
----------------

Once you have OmegaT installed, you might want to start your translation. First, however, you need to **create a project**. A project is basically a folder where all the files of your translation will be contained. 

Here's my recipe:

1. Go to **Project**, then **New**,

2. Choose a name and place for your project,

3. In the Create New Project window, select the source and target languages. 
   Leave everything else as default for the moment. 


You should have an empty folder where you can start working. Now, 

4. Copy the file(s) you want to translate inside the `project-name/source`    folder. Then, hit the F5 button to refresh the project. 
   
In the OmegaT website, you can find the `full list of compatible files <http://omegat.org/howtos/compatibility>`_. Bear in mind, however, that if a file is not directly supported, that doesn't mean that it cannot be translated. In my case, I was working with Markdown .md files, which are not recognised by default. But there's an easy fix for this, see below. 

Translating
-----------

At this point, you will probably see the file you want to translate in the editor window. Under **View**, I suggest you check "Mark Translated Segments" and "Mark Untranslated Segments", to visually see what's left to translate. 

OmegaT will divide the document for you, creating different segments at the sentence level. This has several advantages, the first being that you can concentrate on a single phrase at the time, without the risk of losing parts of the text. 

Translate a sentence, then move on to the next by pressing Enter. You can also move to the previous or next segments with Cmd+P or Cmd+N (Control on Windows). 

Once you have finished and are happy enough with your translation, you can **export the result** by going to **Project** > **Create Translated Documents**, or Cmd+D. You can find your translation inside the `target` folder in your project directory.  

Reviewing a translation
-----------------------

Suppose now that someone else translated the document, and you're given the task to do a review or post-edit it. You then have the original source file, plus the translation file. 

Start by placing the source file in the `source` folder, as explained above. Then, you will use the translation file to create a **translation memory**, i.e., a one-to-one correspondence between the segments of the source and target file. 

5. Go to **Tools** > **Align Files...** (Note: this option is not present in previous versions of OmegaT!)

6. Under Target, press **Browse** and select the translation you want to review, then **OK**

7. A new window will appear, giving you the option to select the segments of interest. Select all that are needed. It will also show you how the source is mapped to the target. If you don't need the fancy options on the bottom, click on **Continue**. 

8. In this last window, you will need to manually adjust the alignment, if needed. Sometimes, different segments are mapped incorrectly to the target, and you are given the option to correct mistakes here. I have to say, the matching algorithm is quite accurate, so you probably won't need this. When you are finished, save the translation memory with **Save TMX**. You should place it inside the `tm/auto` folder. This will automatically pre-populate the translation with the file you need to review. 

9. Once you saved the translation memory, close the tab and hit F5. Your translation will be populated with the segments from the file you need to review. Go through each segment and confirm or edit it as needed. 

10. Once you're finished, export the reviewed translation and look into the `target` folder. 

Handling uncommon file extensions
-----------------------------------------

As I mentioned before, Markdown files (as well as .rst and others) are not supported by default on OmegaT. If you try to import them, the program simply does not recognise them. 

However, as you know these are just plain text files. With a simple procedure, you can include these in the supported documents.

1. Go to **Preferences** > **File filters** 

2. Then, select "Text" and click on **Edit**

3. Click on **Add**, then specify the Source Filename Pattern by typing in the right extension. You can leave everything else as default. Then, click **OK** 

You should now be able to import other types of plain texts into OmegaT. 


Final comments
--------------

At first, this process might seem rather cumbersome. Why do I need a project folder, with many sub-folders, only to translate a single document? Many reasons are listed in `this post <http://www.web-translations.com/blog/use-cat-tools/>`_, but I'll give you my two pence anyway:

- Accuracy: you won't forget to translate or review a segment,

- Consistency: repetitions are handled inside the program, so that you won't translate the same sentence in different ways. 

- Speed: having to go back and forth between different documents is time consuming. Having the source and translated segments side by side helps speeding up the process tremendously. 


If you have comments or found this post useful, feel free to `reach out <https://twitter.com/intent/tweet?screen_name=_atorin>`_.

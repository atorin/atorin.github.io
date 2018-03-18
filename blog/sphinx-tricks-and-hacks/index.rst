.. title: Some tricks and hacks with Sphinx
.. slug: sphinx-tricks-and-hacks
.. date: 2018-03-17 15:00:00 UTC+01:00
.. tags: sphinx, rst
.. category: 
.. link: 
.. description: "A few tricks and hacks with RST documents and Sphinx"
.. type: text


This is a (hopefully!) growing collection of tricks and hacks that I have come across working with `RST documents <http://docutils.sourceforge.net/rst.html>`_, `Sphinx <http://www.sphinx-doc.org/>`_ and `Read the Docs <http://readthedocs.org>`_. 

.. TEASER_END

Vim and RST
===========

I love Vim (actually, MacVim), and as soon as I started working with RST documents for the first time, I hoped to find a nice plug-in to speed up my editing. 

Of course, someone had already thought about that... Enter Riv!

`Riv <https://github.com/gu-fan/riv.vim>`_ is a great plug-in, with many shortcuts to make your life easier when dealing with RST files. In my opinion, the best thing about Riv is how it handles table creation. You create cells by simply pressing tab, and when you modify the content, the table automatically reshapes when you exit the edit mode. 

A few shortcuts for you:

- :code:`tab`: move to the next cell

- :code:`option + enter`: create the header row

- :code:`control + enter`: create a new regular row

.. figure:: http://www.albertotorin.it/blog-files/rst-tables-with-riv.gif
   :alt: Create RST tables with Riv plug-in for MacVim
   :width: 600 px
   :align: center

   Create tables with Riv.

If you try Riv, don't forget to install `InstantRst <https://github.com/gu-fan/InstantRst>`_ as well. This will enable a live preview in the browser, as you edit your document. 


Tables in Sphinx
================

Tables in Sphinx can be a very frustrating thing. Sometimes you have a large table that is difficult to render with the RST syntax; in other cases, the table looks good in the HTML page but awful in the PDF output. 

For those cases, I have created a `short tutorial about tables with Sphinx <http://http://tables-with-sphinx.readthedocs.io/>`_. 

One of the best options, in my option, is to work with CSV tables. You can create your table in a spreadsheet, without the need to worry about the proper formatting in RST. 
To take care of the PDF output for those long tables that won't fit on a single page, you can use the :code:`longtable` class. Then, with the :code:`tabularcolumns` directive, you can control the width of the columns in your PDF. 

This is a sample code snippet to render a table from a CSV file. Check the result in the `tutorial <http://tables-with-sphinx.readthedocs.io/en/latest/csv-table.html>`_.

.. code-block:: rst

   .. tabularcolumns:: |p{1cm}|p{7cm}|
   
   .. csv-table:: Caption of the figure
      :file: path-to-the/file.csv 
      :header-rows: 1 
      :class: longtable
      :widths: 1 1

This approach also works if you use a `grid table <http://www.sphinx-doc.org/en/master/rest.html#tables>`_ instead of a CSV table, with the proper changes.

Convert HTML tables to RST
--------------------------

Speaking of tables, if you start from a table in HTML, you can use `DashTable <https://github.com/doakey3/DashTable>`_ to convert it to RST. This tool will produce for you a nice grid table that you can easily copy and paste in your RST document. 


Break numbered lists
====================

Whenever you start a line with :code:`1. Something...`, Sphinx produces a numbered list. Sometimes, however, this is not the behaviour you would like to achieve. 

To break the numbered list, you can just add a backslash after the number, like this: :code:`1\. Something...`. This is enough for Sphinx to treat the line as a normal sentence. 

CDSE Days 2020 Python Workshop
==============================

*Welcome to the Python workshop page. Below is some information about the workshop
and how to prepare for it. Additional materials will be posted here later on.
I am looking forward to meeting you on March 30!*

*Bernard Badzioch*

General information
-------------------

* The workshop will present basic features of Python and Jupyter Notebook. No Python
  background is expected, but we will be proceeding at a brisk pace, so general programming
  experience will be helpful. In the second part of the workshop I will demonstrate
  a few useful Python libraries - requests, pandas and beautiful soup, and show they
  can be used for gathering and analyzing data.

* This will be a hands-on workshop - we will write and execute code the entire time.
  All participants need to bring laptops. Any operating system (Windows/Mac/Linux) is fine.
  Instructions how to install software we will use are posted below.

* I set up a `Piazza <http://piazza.com/buffalo/spring2020/cdse2020>`_ page
  for the workshop. Please sign up so you can post questions and comments before,
  during, and after the workshop.


Software Installation
---------------------

1. Install the `Anaconda distribution of Python 3.7 <https://www.anaconda.com/download>`_.
   Be sure to select the 3.7 version.

   If you have Anaconda previously installed, make sure that it includes Python 3.6,
   3.7 or 3.8, and fairly recent versions of the the Jupter Notebook and the following
   Python packages: numpy, matplotlib, bokeh, pandas, requests, Beautiul Soup (bs4).
   Upgrade if needed. If you are installing Anaconda for the first time, you don't need
   to worry about it, everything is included in the distribution.

2. A part of the Anaconda distribution is the Jupyter Notebook app.
   It can be launched by typing::

     jupyter notebook

   in a terminal (Mac and Linux)  or command prompt (Windows). Once you execute
   this command, a web browser will open showing Jupyter Notebook dashboard.
   Here is a short video by prof. Lorena Barbra which demonstrates basic functionality
   of the Jupyter Notebook (watching the first 4 minutes or so will be enough for now):

   .. raw:: html

       <div align="center">
       <iframe  max-width="100%" width="560px" height="315px" src="https://www.youtube.com/embed/BJnro9jQ3fE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
       </div>
       <br/><br/>


3. To make sure that everything went fine, start Jupyter Notebook, copy and paste
   the following code into a code cell, and execute the cell. The code will check
   which version of Python you are using, and if the Python packages listed above
   are available on your computer. If you notice error messages, please contact me
   either on Piazza or by email `badzioch@buffalo.edu <badzioch@buffalo.edu>`_.

   .. code-block:: none

         from importlib import import_module
         import sys
         ok = True
         major, minor = sys.version_info[:2]
         if not (major == 3 and minor >= 6):
             print("ERROR: Your are using Python {}.{}. Please upgrade to Python 3.7.\n".format(major, minor))
             ok = False
         else:
             print(6*" "+ "Python {}.{} : OK".format(major, minor))
             for module in ["numpy", "pandas", "bs4", "matplotlib", "bokeh", "requests"]:
                 try:
                     m = import_module(module)
                     ver = m.__version__
                     print("{:>10} {:<6}: OK".format(module, ver))
                 except ImportError:
                     print("{:>16} : ERROR".format(module))
                     ok = False
         if ok:
             print("\nEverything seems to be working fine!")

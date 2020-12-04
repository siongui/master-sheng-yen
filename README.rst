===============
How to Develope
===============

.. .. image:: https://travis-ci.org/siongui/master-sheng-yen.png?branch=master
    :target: https://travis-ci.org/siongui/master-sheng-yen

.. image:: https://github.com/siongui/master-sheng-yen/workflows/Pelican%20site%20CI/badge.svg
    :target: https://github.com/siongui/master-sheng-yen/blob/master/.github/workflows/pelican.yml

Development Tool: Pelican_ (static site generator written in Python)

Development Environment: `Ubuntu 20.04`_


First-time Setup
----------------

1. Install git_ and pip_:

   .. code-block:: bash

     $ sudo apt-get install git
     $ sudo apt-get install python-pip

2. Install language packages to add locale (English, Traditional Chinese, and
   Thai in this example):

   .. code-block:: bash

     $ sudo apt-get install language-pack-en
     $ sudo apt-get install language-pack-zh-hant
     $ sudo apt-get install language-pack-th

3. git clone source code:

   .. code-block:: bash

     $ cd
     $ mkdir dev
     $ cd ~/dev/
     $ git clone https://github.com/siongui/pelican-template.git YOUR_REPO

4. Install Python tools:

   .. code-block:: bash

     $ cd ~/dev/YOUR_REPO/
     $ sudo pip install -r requirements.txt

5. Install Pelican `i18n_subsites`_ plugin and download `normalize.css`_:

   .. code-block:: bash

     $ cd ~/dev/YOUR_REPO/
     $ make download

6. Generate CSS file:

   .. code-block:: bash

     $ cd ~/dev/YOUR_REPO/
     $ make scss


Auto-deploy by GitHub Actions
-----------------------------

See `workflow file <.github/workflows/pelican.yml>`_.


Auto-deploy by `Travis CI`_
---------------------------

1. Sing up a `Travis CI`_ account. Go to your profile page and enable Travis CI
   for the repository you want to build. (See `Getting started - Travis CI`_)

2. delete global_ secure_ `environment variable`_ in
   `.travis.yml <.travis.yml>`_.

3. Go to your GitHub. Generate a `personal access token`_ in Personal Settings
   (only **public_repo** privilege is enough).

4. Install `Travis CI command line client`_ to encrypt token:

   .. code-block:: bash

     $ sudo apt-get install ruby ruby-dev
     $ sudo gem install travis

5. encrypt the token and add it to `.travis.yml <.travis.yml>`_:

   .. code-block:: bash

     $ travis encrypt GH_TOKEN=your_token --add -r YOUR_GITHUB_NAME/YOUR_REPO


Daily Development
-----------------

.. code-block:: bash

    # start edit and develope
    $ cd ~/dev/YOUR_REPO/
    # If something changes, re-generate the website:
    $ make html
    # start dev server
    $ make serve
    # open your browser and preview the website at http://localhost:8000/


UNLICENSE
---------

All works, including posts and code, of Siong-Ui Te are released in public domain.
Please see UNLICENSE_.


References
----------

.. [1] `Deploy Website by Pelican, Travis CI, and GitHub Pages <https://siongui.github.io/2016/01/05/deploy-website-by-pelican-travis-ci-github-pages/>`_

.. [2] | JINJA_FILTERS in `Settings — Pelican documentation <http://docs.getpelican.com/en/latest/settings.html>`_
       | `Jinja custom filters documentation <http://jinja.pocoo.org/docs/dev/api/#custom-filters>`_

.. [3] `拈花微笑　聖嚴法師著_自序 <http://www.book853.com/show.aspx?id=73&cid=170>`_

.. [4] | `How to set up TravisCI for projects that push back to github · GitHub <https://gist.github.com/willprice/e07efd73fb7f13f917ea>`_
       | `Tips — Pelican documentation <http://docs.getpelican.com/en/latest/tips.html#publishing-to-github>`_
       | `GitHub Pages Deployment - Travis CI <https://docs.travis-ci.com/user/deployment/pages/>`_
       | `Deploy gh-pages via Travis cheatsheet <http://ricostacruz.com/cheatsheets/travis-gh-pages.html>`_

.. _Pelican: http://blog.getpelican.com/
.. _Ubuntu 20.04: https://releases.ubuntu.com/20.04/
.. _UNLICENSE: http://unlicense.org/
.. _git: https://git-scm.com/
.. _pip: https://pypi.python.org/pypi/pip
.. _i18n_subsites: https://github.com/getpelican/pelican-plugins/tree/master/i18n_subsites
.. _normalize.css: https://necolas.github.io/normalize.css/
.. _Travis CI: https://travis-ci.org/
.. _Getting started - Travis CI: https://docs.travis-ci.com/user/getting-started/
.. _global: https://docs.travis-ci.com/user/environment-variables/#Global-Variables
.. _secure: https://docs.travis-ci.com/user/environment-variables/#Encrypted-Variables
.. _environment variable: https://docs.travis-ci.com/user/environment-variables/
.. _personal access token: https://help.github.com/articles/creating-an-access-token-for-command-line-use/
.. _Travis CI command line client: https://github.com/travis-ci/travis.rb
.. _Google Adsense: https://www.google.com/search?q=Google+AdSense

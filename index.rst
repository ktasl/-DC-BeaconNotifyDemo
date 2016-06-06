Welcome to Beacon Notify Demo Doc
========================

此份文件為*中華電信研究院* **Beacon感知元件** 的使用手冊
若有任何問題歡迎請直接聯繫 `技術窗口`_.

The code is open source, and `available on github`_.

.. _Read the docs: http://readthedocs.org/
.. _Sphinx: http://sphinx.pocoo.org/
.. _reStructuredText: http://sphinx.pocoo.org/rest.html
.. _CommonMark: http://commonmark.org/
.. _Markdown: http://daringfireball.net/projects/markdown/syntax
.. _Subversion: http://subversion.tigris.org/
.. _Bazaar: http://bazaar.canonical.com/
.. _Git: http://git-scm.com/
.. _Mercurial: http://mercurial.selenic.com/
.. _available on github: http://github.com/rtfd/readthedocs.org
.. _技術窗口: mailto:michaelangelo@cht.com.tw

The main documentation for the site is organized into a couple sections:

* :ref:`user-docs`
* :ref:`feature-docs`
* :ref:`about-docs`

Information about development is also available:

* :ref:`dev-docs`
* :ref:`design-docs`
* :ref:`ops-docs`

.. _user-docs:

.. toctree::
   :maxdepth: 2
   :caption: User Documentation

   getting_started
   versions
   builds
   features
   support
   faq
   yaml-config
   guides/index


.. _feature-docs:

.. toctree::
   :maxdepth: 2
   :glob:
   :caption: Feature Documentation

   webhooks
   badges
   alternate_domains
   localization
   vcs
   conda
   canonical
   single_version
   privacy
   user-defined-redirects
   automatic-redirects
   features/*


.. _dev-docs:

.. toctree::
   :maxdepth: 2
   :caption: Developer Documentation

   install
   changelog
   contribute
   tests
   architecture
   development/standards
   development/buildenvironments
   symlinks
   settings
   i18n
   issue-labels

.. _business-docs:

.. toctree::
   :maxdepth: 2
   :caption: Business Documentation

   business/index

.. _custom-docs:

.. toctree::
   :maxdepth: 2
   :caption: Custom Install Documentation

   custom_installs/index

.. _design-docs:

.. toctree::
   :maxdepth: 2
   :caption: Designer Documentation

   design
   theme


.. _about-docs:

.. toctree::
   :maxdepth: 2
   :caption: About Read the Docs

   open-source-philosophy
   sponsors
   talks


.. _ops-docs:

.. toctree::
   :maxdepth: 2
   :caption: Operations Documentation

   rtfd
=================================
Mozilla Source Tree Documentation
=================================

.. toctree::
   :maxdepth: 1

   browser/base/sslerrorreport/index
   browser/browser/index
   browser/experiments/experiments/index
   build/buildsystem/index
   dom/bindings/webidl/index
   gfx/gfx/index
   mobile/android/fennec/index
   mozbase/index
   python/mach/index
   taskcluster/taskcluster/index
   testing/geckodriver/geckodriver/index
   testing/marionette/marionette/index
   toolkit/components/crashes/crash-manager/index
   toolkit/components/extensions/webextensions/index
   toolkit/components/payments/docs/index
   toolkit/components/telemetry/telemetry/index
   toolkit/components/url-classifier/url-classifier/index
   toolkit/crashreporter/crashreporter/index
   toolkit/modules/subprocess/toolkit_modules/subprocess/index
   toolkit/modules/toolkit_modules/index
   toolkit/mozapps/extensions/addon-manager/index
   tools/compare-locales/index
   tools/lint/index

Python Packages
===============

.. toctree::
   :maxdepth: 2

   python/mach
   python/mozbuild
   python/mozlint
   python/mozpack
   python/mozversioncontrol
   python/mozwebidlcodegen
   python/taskgraph

Managing Documentation
======================

This documentation is generated via the
`Sphinx <http://sphinx-doc.org/>`_ tool from sources in the tree.

To build the documentation, run ``mach doc``. Run
``mach help doc`` to see configurable options.

Adding Documentation
--------------------

To add new documentation, define the ``SPHINX_TREES`` and
``SPHINX_PYTHON_PACKAGE_DIRS`` variables in ``moz.build`` files in
the tree and documentation will automatically get picked up.

Say you have a directory ``featureX`` you would like to write some
documentation for. Here are the steps to create Sphinx documentation
for it:

1. Create a directory for the docs. This is typically ``docs``. e.g.
   ``featureX/docs``.
2. Create an ``index.rst`` file in this directory. The ``index.rst`` file
   is the root documentation for that section. See ``build/docs/index.rst``
   for an example file.
3. In a ``moz.build`` file (typically the one in the parent directory of
   the ``docs`` directory), define ``SPHINX_TREES`` to hook up the plumbing.
   e.g. ``SPHINX_TREES['featureX'] = 'docs'``. This says *the ``docs``
   directory under the current directory should be installed into the
   Sphinx documentation tree under ``/featureX``*.
4. If you have Python packages you would like to generate Python API
   documentation for, you can use ``SPHINX_PYTHON_PACKAGE_DIRS`` to
   declare directories containing Python packages. e.g.
   ``SPHINX_PYTHON_PACKAGE_DIRS += ['mozpackage']``.

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

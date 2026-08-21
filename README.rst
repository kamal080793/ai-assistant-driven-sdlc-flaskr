Flaskr
======

Flaskr is a small Flask/Jinja/SQLite blog application based on the Flask tutorial. This repository is being enhanced under Jira epic EPMCDMETST-61339 to improve post discovery, post metadata, testing, local delivery, and documentation.

Links
-----

* Jira Epic: https://jiraeu.epam.com/browse/EPMCDMETST-61339
* Search Story: https://jiraeu.epam.com/browse/EPMCDMETST-61340
* Filter Story: https://jiraeu.epam.com/browse/EPMCDMETST-61341
* Tests/Scripts/Docs Story: https://jiraeu.epam.com/browse/EPMCDMETST-61342
* Metadata Story: https://jiraeu.epam.com/browse/EPMCDMETST-61343
* Confluence Design Pack: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/16547843/Flaskr+Discovery+Metadata+Design+Pack+-+EPMCDMETST-61339

Current Features
----------------

* User registration, login, logout, and session-based authentication.
* Anonymous users can view blog posts.
* Authenticated users can create posts.
* Authors can edit and delete their own posts; non-authors are blocked.
* SQLite persistence with user and post tables.
* Pytest coverage for core app factory, auth, blog CRUD, validation, and authorization flows.

Approved Enhancement Scope
--------------------------

The approved epic enhances Flaskr with:

* Keyword search for posts.
* Category, status, and optional due date metadata for posts.
* Category and status filtering.
* Backend regression tests and Playwright end-to-end test coverage.
* Local build/deployment scripts.
* README and Confluence documentation updates.

Implementation Branch
---------------------

Work is tracked on branch::

    feature/flaskr-discovery-metadata

Completed implementation commits currently available on the branch:

* ``91e60fee6872bc00d3ffb9637343aa95f941df40`` - ``feat: add category, status, and due_date fields to post schema [EPMCDMETST-61343]``
* ``e7bffc6331c26d723402664a24e1a435c4487818`` - ``feat: update test data with category and status fields [EPMCDMETST-61343]``

Install
-------

Create a virtual environment and activate it::

    $ python3 -m venv .venv
    $ . .venv/bin/activate

Or on Windows cmd::

    $ py -3 -m venv .venv
    $ .venv\Scripts\activate.bat

Install Flaskr::

    $ pip install -e .

Install test dependencies::

    $ pip install '.[test]'

Run Locally
-----------

Initialize the database and start the development server::

    $ flask --app flaskr init-db
    $ flask --app flaskr run --debug

Open http://127.0.0.1:5000 in a browser.

Local Build and Deployment Notes
--------------------------------

If scripts are present in the implementation branch, use::

    $ ./scripts/build.sh
    $ ./scripts/run.sh

If scripts are not yet present, use the manual commands in the Run Locally and Test sections.

Test
----

Run the backend test suite::

    $ pytest

Run with coverage report::

    $ coverage run -m pytest
    $ coverage report
    $ coverage html

Playwright end-to-end tests are part of the approved scope. When Playwright tests are added, install browsers and run them with the documented project command, for example::

    $ pip install playwright
    $ playwright install
    $ pytest tests/test_e2e.py

Documentation
-------------

Final SDLC documentation is maintained in Confluence and includes:

* BA Gap Analysis
* Functional Requirements Document
* Architecture document and diagram
* High Level Design
* Low Level Design
* Wireframes
* Implementation plan
* Test case summary
* Test execution report
* Deployment notes
* Demo flow evidence
* Traceability matrix

Primary Confluence pages:

* Design Pack: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/16547843/Flaskr+Discovery+Metadata+Design+Pack+-+EPMCDMETST-61339

Traceability Summary
--------------------

+----------------+-------------------------------------------+---------------------+
| Requirement    | Description                               | Jira                |
+================+===========================================+=====================+
| FR-01/FR-02    | Keyword search, case-insensitive matching | EPMCDMETST-61340    |
+----------------+-------------------------------------------+---------------------+
| FR-03          | No-results messaging                      | EPMCDMETST-61340/41 |
+----------------+-------------------------------------------+---------------------+
| FR-04..FR-07   | Category, status, due date metadata       | EPMCDMETST-61343    |
+----------------+-------------------------------------------+---------------------+
| FR-08          | Category/status filters                   | EPMCDMETST-61341    |
+----------------+-------------------------------------------+---------------------+
| FR-09..FR-11   | Tests, scripts, and documentation         | EPMCDMETST-61342    |
+----------------+-------------------------------------------+---------------------+

Notes for Reviewers
-------------------

The current repository branch contains committed schema and test-data changes. Final acceptance should verify that remaining approved backend/frontend implementation, tests, scripts, and PR links are complete before merge to main.

Flaskr SDLC Capstone
====================

Repository
----------

This repository contains the Flaskr tutorial blog application used for an AI-assisted SDLC capstone workflow.

* GitHub: https://github.com/kamal080793/ai-assistant-driven-sdlc-flaskr
* Default branch: ``main``
* Documentation branch: ``docs/final-sdlc-documentation``
* Confluence documentation index: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13205523/Flaskr+SDLC+Documentation+Package

Current Application Features
----------------------------

Authentication
~~~~~~~~~~~~~~

* User registration with username and password.
* Secure password hashing using Werkzeug.
* User login and logout.
* Session-based current-user loading.
* Login-required protection for restricted actions.

Blog Posts
~~~~~~~~~~

* Public blog index that lists posts in reverse chronological order.
* Authenticated users can create posts.
* Authors can update and delete their own posts.
* Non-authors are prevented from editing or deleting another user's post.
* Server-rendered Jinja templates and simple CSS-based UI.

Database
~~~~~~~~

* SQLite persistence.
* ``flask --app flaskr init-db`` database initialization command.
* User and post tables with an author relationship.

Tests
~~~~~

* pytest fixtures for app, client, runner, and auth helper.
* Authentication tests for register, login, logout, and validation paths.
* Blog tests for index, create, update, delete, authentication, and authorization behavior.
* Database initialization and application factory tests.

Approved Enhancement Scope
--------------------------

The following Jira stories were approved and created in project ``EPMEDUAI``:

* ``EPMEDUAI-2100`` - Search and filter blog posts.
* ``EPMEDUAI-2099`` - Manage blog post metadata.
* ``EPMEDUAI-2101`` - Add automated Playwright UI tests.
* ``EPMEDUAI-2102`` - Provide local build, deployment, and documentation updates.

Epic grouping: ``Enhance Flaskr blog content management and delivery readiness``.

Planned Enhancements
~~~~~~~~~~~~~~~~~~~~

* Search blog posts by title or body content.
* Filter posts by category and status.
* Add post metadata: category, status, and optional due date.
* Display metadata on the blog list.
* Add no-results messaging for search/filter states.
* Add Playwright UI tests for key workflows.
* Add repeatable local setup, validation, and deployment scripts.

Local Setup
-----------

Create and activate a virtual environment::

    python3 -m venv .venv
    . .venv/bin/activate

On Windows cmd::

    py -3 -m venv .venv
    .venv\Scripts\activate.bat

Install the application and test dependencies::

    pip install -e '.[test]'

Run Locally
-----------

Initialize the database and start the app::

    flask --app flaskr init-db
    flask --app flaskr run --debug

Open http://127.0.0.1:5000 in a browser.

Run Tests
---------

Run the existing backend test suite::

    pytest

Run with coverage::

    coverage run -m pytest
    coverage report
    coverage html

Deployment Notes
----------------

Current deployment target is local Flask development runtime for review and demo purposes.

Deployment steps:

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install the package with test dependencies.
4. Initialize the SQLite database using ``flask --app flaskr init-db``.
5. Start the app with ``flask --app flaskr run --debug``.
6. Smoke test registration, login, post creation, post update, post deletion, and logout.

Traceability
------------

+----------------+-----------------------------------------------+---------------------------------------------+
| Jira Key       | Requirement                                   | Validation                                  |
+================+===============================================+=============================================+
| EPMEDUAI-2100  | Search and filter blog posts                  | Backend tests and Playwright UI tests       |
+----------------+-----------------------------------------------+---------------------------------------------+
| EPMEDUAI-2099  | Manage category, status, and due date metadata | Backend tests and create/edit UI tests      |
+----------------+-----------------------------------------------+---------------------------------------------+
| EPMEDUAI-2101  | Add automated Playwright UI coverage           | Playwright execution report                 |
+----------------+-----------------------------------------------+---------------------------------------------+
| EPMEDUAI-2102  | Update scripts, README, and Confluence docs    | Documentation review and local smoke test   |
+----------------+-----------------------------------------------+---------------------------------------------+

Documentation
-------------

Final SDLC documentation is maintained in Confluence under the Flaskr SDLC Documentation Package page and includes:

* BA Gap Analysis
* FRD
* Architecture Document
* Architecture Diagram
* HLD
* LLD
* Wireframes
* Implementation Plan
* Test Case Summary
* Test Execution Report
* Deployment Notes
* Demo Flow Evidence

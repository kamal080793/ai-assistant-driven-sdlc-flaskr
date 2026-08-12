Flaskr
======

The basic blog app built in the Flask tutorial, maintained in this repository for the AI-assistant-driven SDLC Flaskr enhancement workflow.

Repository
----------

* GitHub: https://github.com/kamal080793/ai-assistant-driven-sdlc-flaskr
* Default branch: main
* Documentation branch: docs/final-sdlc-documentation-20260812

Current Application Features
----------------------------

* User registration, login, logout, and session-based user loading.
* Public blog post index rendered with Jinja templates.
* Authenticated post create, update, and delete flows.
* Author-only authorization for update and delete.
* SQLite database initialization through ``flask --app flaskr init-db``.
* pytest coverage for app factory, database, authentication, blog CRUD, validation, and authorization flows.

Approved Enhancement Scope
--------------------------

Epic: Enhance Flaskr blog post management and delivery readiness.

Approved user stories:

#. Add blog post metadata: category, status, and optional due date.
#. Add search and filters for blog posts.
#. Add automated Playwright tests.
#. Add local build/deployment scripts and update documentation.

Confluence Documentation
------------------------

Final SDLC documentation package:

* Parent page: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13139969/Flaskr+SDLC+Final+Documentation+-+2026-08-12
* FRD: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13205505/Flaskr+FRD+-+2026-08-12
* Architecture document: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13238273/Flaskr+Architecture+Document+-+2026-08-12
* Architecture diagram: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13041666/Flaskr+Architecture+Diagram+-+2026-08-12
* HLD: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13172737/Flaskr+HLD+-+2026-08-12
* LLD: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13303809/Flaskr+LLD+-+2026-08-12
* Wireframes: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13336577/Flaskr+Wireframes+-+2026-08-12
* Implementation plan: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13271041/Flaskr+Implementation+Plan+-+2026-08-12
* Test case summary: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13369345/Flaskr+Test+Case+Summary+-+2026-08-12
* Test execution report: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13402114/Flaskr+Test+Execution+Report+-+2026-08-12
* Deployment notes: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13434881/Flaskr+Deployment+Notes+-+2026-08-12
* Demo flow evidence: https://vishwakarmakamal8.atlassian.net/wiki/spaces/MFS/pages/13467649/Flaskr+Demo+Flow+Evidence+-+2026-08-12

Jira Traceability
-----------------

Human approval was received for the epic and stories as-is. Jira issue creation details were not available in this documentation node output. Add Jira Epic and Story links here after Jira issues are created or confirmed.

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

.. code-block:: text

    $ flask --app flaskr init-db
    $ flask --app flaskr run --debug

Open http://127.0.0.1:5000 in a browser.

Test
----

Run pytest::

    $ pytest

Run with coverage report::

    $ coverage run -m pytest
    $ coverage report
    $ coverage html

Planned browser test command when Playwright tests are added::

    $ playwright install
    $ pytest tests/playwright

Smoke Test Checklist
--------------------

#. Open the local index page.
#. Register or log in.
#. Create a post.
#. Confirm post list rendering.
#. Run pytest.
#. For the approved enhancement scope, validate metadata, search/filter, no-result messaging, and Playwright flows once implemented.

Deployment Notes
----------------

This repository currently supports local Flask deployment. See the Confluence Deployment Notes page for detailed setup, smoke test, and rollback instructions.

Review Checklist
----------------

* README links to repository, Confluence documentation, branch, tests, and deployment instructions.
* Jira links are added after issue creation/confirmation.
* Test execution evidence is attached or linked after local execution.
* Human reviewer approves final documentation package before demo.

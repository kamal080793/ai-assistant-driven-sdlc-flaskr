Flaskr
======

Flaskr is a Python Flask blog application based on the Flask tutorial structure. This repository is used as an AI-assistant-driven SDLC demonstration project.

Repository
----------

- GitHub: https://github.com/kamal080793/ai-assistant-driven-sdlc-flaskr
- Default branch: main
- Primary stack: Python, Flask, Jinja templates, SQLite, pytest

Current Features
----------------

- User registration with password hashing.
- User login and logout using session-based authentication.
- Current-user loading into ``g.user`` before each request.
- Public blog post listing ordered by newest first.
- Authenticated post creation.
- Author-only post edit and delete flows.
- Basic server-side validation and flash messages.
- SQLite schema initialization through the Flask CLI.
- Automated pytest coverage for app factory, database, authentication, and blog CRUD behavior.

Frontend and UI Summary
-----------------------

The application uses server-rendered Jinja templates and a shared CSS file. The UI includes a top navigation area, authentication links for anonymous users, current-user and logout controls for authenticated users, a post list, author-only edit links, and simple create/update forms. Flash messages provide user feedback for validation and authentication errors.

Approved Enhancement Backlog
----------------------------

Human review approved the following Epic and stories as-is before Jira creation.

Epic: Enhance Flaskr Blog Management and Delivery Readiness
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Improve the Flaskr blog application with post discovery, post metadata, lifecycle management, automated browser testing, local deployment scripts, and updated documentation.

Approved stories:

1. Search blog posts
   As a blog reader, I want to search blog posts by keyword so that I can quickly find relevant content.

2. Manage post category, status, and due date
   As a blog author, I want to assign category, status, and an optional due date to posts so that I can organize and manage blog content.

3. Filter posts by category and status
   As a blog reader, I want to filter posts by category and status so that I can narrow the post list to relevant content.

4. Improve delivery readiness with automation and documentation
   As a developer, I want automated Playwright tests, local build and deployment scripts, and updated documentation so that I can verify and run the application consistently.

Traceability Status
-------------------

+----------------+---------------------------------------------------+-------------------------------+-----------------------------+
| Work Item      | Requirement                                       | Implementation Status         | Test Evidence               |
+================+===================================================+===============================+=============================+
| Epic draft     | Blog management and delivery readiness            | Approved for Jira creation    | Pending implementation      |
+----------------+---------------------------------------------------+-------------------------------+-----------------------------+
| Story 1        | Search blog posts by keyword                      | Not started                   | Pending pytest/Playwright   |
+----------------+---------------------------------------------------+-------------------------------+-----------------------------+
| Story 2        | Category, status, and due date post metadata      | Not started                   | Pending pytest/Playwright   |
+----------------+---------------------------------------------------+-------------------------------+-----------------------------+
| Story 3        | Filter posts by category and status               | Not started                   | Pending pytest/Playwright   |
+----------------+---------------------------------------------------+-------------------------------+-----------------------------+
| Story 4        | Browser tests, local scripts, and documentation   | Documentation initiated       | README/docs commit          |
+----------------+---------------------------------------------------+-------------------------------+-----------------------------+

Jira issue links, PR links, implementation commits, test reports, and deployment evidence must be added after those artifacts are created.

Install
-------

Create a virtual environment and activate it::

    $ python3 -m venv .venv
    $ . .venv/bin/activate

On Windows cmd::

    $ py -3 -m venv .venv
    $ .venv\Scripts\activate.bat

Install the application::

    $ pip install -e .

Run Locally
-----------

Initialize the database and start the development server::

    $ flask --app flaskr init-db
    $ flask --app flaskr run --debug

Open http://127.0.0.1:5000 in a browser.

Test
----

Install test dependencies and run tests::

    $ pip install '.[test]'
    $ pytest

Run with coverage report::

    $ coverage run -m pytest
    $ coverage report
    $ coverage html

Local Deployment Notes
----------------------

For local review or demo deployment:

1. Clone the repository.
2. Create and activate a virtual environment.
3. Install with ``pip install -e .``.
4. Initialize the database with ``flask --app flaskr init-db``.
5. Run with ``flask --app flaskr run --debug``.
6. Open http://127.0.0.1:5000.
7. Register a user, log in, create a post, edit the post, delete the post, and log out to smoke-test current functionality.

Documentation Notes
-------------------

Confluence publishing was attempted during documentation finalization, but the caller did not have Confluence access. Confluence-ready final documentation is available in ``docs/final_documentation.md`` and can be manually published when access is available.

License
-------

This project retains the repository license included in ``LICENSE.txt``.

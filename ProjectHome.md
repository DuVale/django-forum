This is a basic forum component that can plug into any existing Django installation and use it's existing templates, users, and admin interface. Perfect for adding forum functionality to an existing website.

# Current Status #
This isn't really maintained any more. I'd suggest looking at one of the other more mature Django-based forum products: http://djangoplugables.com/grids/g/forums/

If you want to take over maintenance of this project please let me know.

# The Software #

  * Uses Django Admin for maintenance / moderation - no in-line admin features as yet
  * Uses existing django Auth and assumes you already have that up and running. I use and recommend django-registration
  * Roll your own site with little work: Install Django, install django-registration, flatpages, django-forum, setup your templates and you have an instant website :)
  * Code is as pulled out of my other projects - changes will be made as I go to make sure it's as standalone as possible, right now should be pretty good.

# Getting Started #

  1. Checkout code via [SVN](http://code.google.com/p/django-forum/source/): `svn co http://django-forum.googlecode.com/svn/trunk/ forum`
  1. Add `forum` to your `INSTALLED_APPS` in `settings.py`
  1. `./manage.py syncdb`
  1. Add `FORUM_BASE = '/forum'` to your settings.py (no trailing slash)
  1. Update `urls.py`: ` (r'^forum/', include('forum.urls')),`
  1. Go to your site admin, add a forum
  1. Browse to `yoursite.com/forum/`

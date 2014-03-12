Django-addressbook
--------------------

Features
-----------

* Allow users to register themselves via their Facebook, Twitter,
Google, or OpenID credentials
* Users can create contact records organized into user-defined contact groups
* The app supports storing for each contact:
** Multiple physical addresses
** Multiple phone numbers
** Multiple emails
* Each contact record supports exporting that record in vCard
format (`http://en.wikipedia.org/wiki/VCard`)
* Each contact record presents a QR code to allow a barcode
scanner to import it
* Each contact record accesses any Gravatar for the contact
(`http://en.gravatar.com/`)
* Each contact uses the hCard microformat in its markup
`http://microformats.org/wiki/hcard`
* A full unit test suite
* The app is installable using standard Python distutils

Installing the app 
----------------------

    git clone https://github.com/dkdndes/django-addressbook.git
    python setup.py install
OR
    pip install django-addressbook

Please, consider to use virtualenv in all cases.

Setting up the app
----------------------

Assuming you have Django installed and this app installed (`easy_install django-addressbook`),

1. `python manage.py syncdb`
2. Add addressbook.urls to your urls:
    `url(r'^addressbook/', include('addressbook.urls')),`
3. Add your site domain in settings.py: `DOMAIN = 'example.com'`
4. Ensure that you have base.html template in your templates folder
5. Sym-link uni_form media: ln -s /path/to/uni_form/static/uni_form /path/to/project/media/uni_form
   (setup may differ depending on your MEDIA_URL)
6. (optional) sym-link the sample css file for nicer looking forms (this may override your css): 
        `:~$ ln -s /path/to/addressbook/static/addressbook.css /path/to/proj/media/css/addressbook.css`
7. (optional) override templates as necessary by creating an `addressbook` directory

NOTES
---------

vCard Format: **http://www.ietf.org/rfc/rfc2426.txt**

Vobject Django snippet: **http://djangosnippets.org/snippets/58/**

Vobject usage: **http://vobject.skyhouseconsulting.com/usage.html, http://lists.brotherharris.com/pipermail/vobject/2009-January/000165.html**

==============================
On-premise database management
==============================

Register a database
===================

To register your database, you just need to enter your subscription code in the
banner in the App Switcher. Make sure you do not add extra spaces before or after
your subscription code. If the registration is successful, it will turn green and
will provide you with the expiration date of your freshly-registered database. You
can check this expiration date at the bottom of the settings page.

Registration Error Message
--------------------------

If you are unable to register your database, you will likely encounter this
message:

.. image:: on_premise/error_message_sub_code.png
   :align: center
   :alt: Something went wrong while registering your database, you can try again or contact Odoo
         Help

Solutions
~~~~~~~~~

* Do you have a valid Enterprise subscription?

  * Check if your subscription details have the tag :guilabel:`In Progress` on
    your `Odoo Account
    <https://accounts.odoo.com/my/subscription>`__ or with your Account Manager

* Have you already linked a database with your subscription code?

  * You can link only one database per subscription.
    (Need a test or a development database? :ref:`duplicate_premise`)

  * You can unlink the old database yourself on your `Odoo Contract
    <https://accounts.odoo.com/my/subscription>`__ with the button "Unlink database"

    .. image:: on_premise/unlink_single_db.png
       :align: center

    A confirmation message will appear; make sure this is the correct database as
    it will be deactivated shortly:

    .. image:: on_premise/unlink_confirm_enterprise_edition.png
       :align: center

* Sometimes, you may have multiple databases sharing the same UUID.

        Please check on your `Odoo Contract <https://accounts.odoo.com/my/subscription>`__,
        a short message will appear specifying which database is problematic:

    .. image:: on_premise/unlink_db_name_collision.png
       :align: center

    In this case, you need to change the UUID on your test databases to solve this
    issue or contact our `Support <https://www.odoo.com/help>`__

    For your information, we identify each database with a UUID. Therefore, each
    database should have a distinct UUID to ensure that registration and invoicing
    proceed effortlessly for you and us.

* Check your network and firewall settings

  * The Update notification must be able to reach Odoo's subscription validation servers. In other
    words, make sure that the Odoo server can open outgoing connections towards:

    * services.odoo.com on port 443 (or 80)
    * services.openerp.com on port 443 (or 80) for older deployments
  * Once you activate your database, you must keep these ports open, as the Update notification
    runs once a week.


Error message due to too many users
-----------------------------------

If you have more users in your local database than provisioned in your Odoo Enterprise subscription,
you may encounter this message:

.. image:: on_premise/add_more_users.png
   :align: center
   :alt: This database will expire in X days, you have more users than your subscription allows


When the message appears you have 30 days before the expiration. The countdown is updated every day.

Solutions
~~~~~~~~~

- **Add more users** to your subscription: follow the link and validate the upsell quotation and pay
  for the extra users.
- **Deactivate users** as explained here :ref:`users/deactivate`
  and **reject** the upsell quotation.

Once your database has the correct number of users, the expiration message
will disappear automatically after a few days, when the next verification occurs.

Database expired error message
------------------------------

If your database expires before you renew your subscription,
you will encounter this message:

.. image:: on_premise/database_expired.png
   :align: center
   :alt: This database has expired.

This **blocking** message appears after a non-blocking message that lasts 30 days. If
you fail to act before the end of the countdown, the database will expire.

Solutions
~~~~~~~~~

* Renew your subscription: follow the link and renew your subscription. If you
  pay by wire transfer, your subscription will be renewed when the payment arrives,
  which can take a few days. Credit card payments are processed immediately.

* Contact our `Support <https://www.odoo.com/help>`__

.. _duplicate_premise:

Duplicate a database
====================

You can duplicate your database by accessing the database manager on your
server (<odoo-server>/web/database/manager). On this page, you can duplicate your
database (among other things). Typically you will want to duplicate your
production database into a neutralized testing database. This can be done by
checking the neutralize box when prompted. This will execute all the neutralize.sql
scripts for every installed module.

.. image:: on_premise/duplicate_database.png
  :align: center

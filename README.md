eZ Paypal Payment Gateway extension [ExtensionVersion] README

What is the eZ Paypal Payment Gateway extension?
================================================

Payment gateway for Paypal


eZ Paypal Payment Gateway version
=======================

The current version of eZ Paypal Payment Gateway is [ExtensionVersion].
You can find details about changes for this version in doc/changelogs/CHANGELOG-[ExtensionVersion]


License
=======

eZ Paypal Payment Gateway is dual licensed. You can choose between the GNU
GPL and the eZ publish Professional Licence.

The GNU GPL gives you the right to use, modify and redistribute eZ Payal
Payment Gateway under certain conditions. The GNU GPL licence is distributed
with the software, see the file LICENCE. It is also available at
http://www.gnu.org/licenses/gpl.txt
Using eZ Paypal Payment Gateway under the terms of the GNU GPL is free of
charge.

The eZ publish Professional Licence gives you the right to use the source
code for making your own commercial software. It allows you full protection
of your work made with eZ Paypal Payment Gateway. You may re-brand, license
and close your source code. eZ Paypal Payment Gateway is not free of charge
when used under the terms of the Professional Licence. The eZ publish
Professional Licence is distributed with the software, see the file
PROFESSIONAL_LICENCE. It is also available at
http://ez.no/ez_publish/licenses/professional
For pricing and ordering, please contact us at info@ez.no.


Requirements
============

The following requirements exists for using eZ Paypal Payment Gateway extension:

o  eZ publish version:

   Make sure you use eZ publish version 4.0.1 or higher.

o  PHP version:

   Make sure you have PHP 5.2 or higher.

o  eZ publish must be reachable from the internet:

   Make sure you have installed eZ publish on a webserver that is reachable by
   the Paypal service.


Troubleshooting
===============

1. Read the FAQ
   ------------

   Some problems are more common than others. The most common ones are listed
   in the the FAQ.

2. Support
   -------

   If you have find any problems not handled by this document or the FAQ you
   can contact eZ Systems trough the support system:
   http://ez.no/support_and_services

Installation
============
Enable this extension, regenerate autoloads, clear cache, create a new "Event/Payment Gateway" workflow, select "paypal", set it as checkout-before trigger. Change paypal.ini settings.

Paypal Sandbox
==============

Create a seller (business) account and a buyer account.

Check your biz account and click "Enter sandbox test site".

Go to Profile->More options

-Payment Receiving Preferences:

For "Block payments sent to me in a currency I do not hold", check "No, accept them and convert them to U.S. Dollars".

-Instant Payment Notification Preferences

For "Notification URL", put http://yoursite.com/paypal/notify_url
For "IPN messages", check "Receive IPN messages (Enabled)"

-Website Payment Preferences

Enable auto return.
Return URL: http://yoursite.com/shop/checkout
Payment Data Transfer (optional): On

-eZ publish settings

In order to test your Paypal you need to change paypal.ini settings:

Business=your_sandbox_biz_test_account@email.com

BE AWARE
========

Paypal needs to able to communicate with your website, that means some localhosts website will not work. To test it, check your IP (google "what's my ip"), go to http://netrenderer.com/ and try to render your site with your ip address and the path to your site. If you are using a router you need to open port 80 to your computer, example, if you are using d-link wireless router just go to "http://192.168.0.1", "Advanced", "Virtual server", "Virtual Servers List". Put:

Application name = HTTP, public port 80, TCP.
IP address: Your gateway IP (192.168.0.XXX), private port 80 (your apache port).

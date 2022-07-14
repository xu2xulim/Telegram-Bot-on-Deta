# Telegram-Bot-on-Deta
This is a documentation only repo. It describes the basic features and components of the solution. It forms the basis for custom features to be added to the bots rather that an ready to use application.
## Software
The following software and or software libraries are used to develop this solution :
- Programming Languages :
  - python
- Python Libraries (only key libraries are listed)
  - python_telegran_bot
  - fastapi
  - py_trello
  - Platforms
    - Deta
    - Trello
 ## Approach
 The solution uses Telegram webhooks receive updates from messages and bot interaction from users in private chat, groups and or channels.
 ## Microservices and databases
 - a primary bot
 - a 'shop' bot
 - Deta Bases
   - user data and conversation persistence
   - user data
   - product data
  ## Trello as a backend
  The choice of Trello as a backend was based on the following considerations:
  - flexibility - Trello can use adapted and use in any small businesses
  - automation - Trello automation has rules, button, calendar and due date command that can be used in many use cases
  - extensibility - A host of add ons called Power Ups or to third party services via the http request action which is part of Trello Automation
  - Integration - Besides Zapier, custom integration can be build using py-trello library. Note that Deta Bases python SDK can be used together with py-trello
## Endpoints
  The following endpoints are currently available :
  - /webhook/{token} - the receives updates from bot (available on both primary and shop bots)
  - /set_webhook - collection of services for setting up the webhook and deleting it. You can also use it to get information on the webhook including the number of updates that are pending on the Telegram server (available on both primary and shop bots)
  - /{token}/trigger - to send messages to an user, group or channel
  - /{token}/join - send invite link to join group or channel
 ## Custom Endpoint and or Bot commands
 These are endpoints built for demo purposes only and they need to be customised to address specific use cases :
 - /update_shop_farms - to update the product database on Deta Base
 - /update_enrolment - to update products 'purchase' for a user
 - Commands
   - /tme to collect user data such as personal details, address, and emails
   - /stat to display information via some api calls
   - @shot_bot xxxx for inline_query of products...etc

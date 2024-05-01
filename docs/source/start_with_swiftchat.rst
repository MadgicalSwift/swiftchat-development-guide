Get started with swiftchat
==========================

Registration on Swiftchat
------------

Registration on SwiftChat is a simple process that allows users to create an account and access the platform's features. For registration follow these steps:

1. Open the APP or website of `SwiftChat <https://web.convegenius.ai/>`_.
2. On opening the App or website you will get the page to enter your phone number. Provide your number and generate the OTP.
   
   .. image:: ../images/installation_images/login.png
      :alt: login page 
      :width: 2000
      :height: 250
      :align: center
      
3. On generating the OTP, you will get the page to enter the OTP. Enter OTP and proceed with next steps.
   
   .. image:: ../images/installation_images/otp1.png
      :alt: login page 
      :width: 600
      :height: 250
      :align: center

4. Once OTP verification is completed, you'll be prompted to input additional details such as your name, state, preferred language, and more to finalize the registration process.
   
Following these steps will complete the registration process.


Obtaining API keys
------------
API keys are essential for authentication and accessing various features of the SwiftChat platform. They serve as a means of verifying your identity and ensuring secure communication between your application and the SwiftChat servers. Each API request you make to the SwiftChat platform must include your API key as part of the authentication process.

To obtain your API key and unlock access to the SwiftChat platform's features, you need to have a merchant account. Once you have registered and logged in to your merchant account, you can generate your API key.

.. tip:: 

   - Create your merchant account using this Post `API <https://documenter.getpostman.com/view/20587790/UyrGCuhH#57d73550-1c15-41a5-ac7e-0ba20b60b3e4>`_ 
   - Complete business KYC and email verification



**Follow these steps to get API key:**

- Open the `SwiftChat Merchant Dashboard <https://dashboard.swiftchat.ai/>`_
- Login to dashboard with your merchant credentials
- Click on profile settings tab and open **Manage Account**
  
   .. image:: ../images/installation_images/profile_settings.png
      :alt: login page 
      :width: 2000
      :height: 250
      :align: left

- In **Manage Account** page you will get the API key at the bottom of page. You can copy the API key from there or create a new one.
  
   .. image:: ../images/installation_images/apiKey_page.png
      :alt: login page 
      :width: 2000
      :height: 250
      :align: left


.. tip::
   You can also get the API key using the **GET** `API <https://documenter.getpostman.com/view/20587790/UyrGCuhH#3ed63aad-3f81-4f42-b0a0-8406feb59716>`_


Setting Up a New Bot
-----------------------------------
To begin utilizing the starter kit, you'll need to obtain a bot ID. You can create a chatbot either manually or via API.

Creating a Bot Using the SwiftChat API
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The SwiftChat APIs act as the conduit between your chatbot and yourself, processing your data accordingly. 

You can employ any tool or platform to interact with the SwiftChat APIs. In this instance, we'll demonstrate using **Postman**.

**Steps**

1. Open Postman or any other API Platform
2. Create a new **POST** request
3. Add this API ``https://v1-api.swiftchat.ai/api/bots`` in the url section
4. Open the authorization section and here add your API key that we generated or got in `Obtaining API Key <get_api_key.html>`_
   
   .. image:: ../images/create_bot_images/create_bot_auth.png
      :alt: Deployment Structure
      :width: 1300
      :height: 300
      :align: center
   

5. Now move to **Body** tab, and add details like, bot-name, mobile-number, and bot-category.

   .. image:: ../images/create_bot_images/create_bot_body.png
      :alt: Deployment Structure
      :width: 1300
      :height: 300
      :align: center


6. On successfully creating bot you will receive a message **created** and status code **OK**

   .. image:: ../images/create_bot_images/successful_bot.png
      :alt: Deployment Structure
      :width: 1300
      :height: 100
      :align: center


7. After creating bot, use the `**varify API** <https://documenter.getpostman.com/view/20587790/UyrGCuhH#a5fa0876-d1b1-48de-a475-dad2ff467071>`_ and varify your bot. This will generate the bot ID.


Creating a Bot Using the SwiftChat Dashboard
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You can also create bot using your SwiftChat Merchant Dashboard

**Steps:**

1. Login to your `SwiftChat Merchant Dashboard <https://dashboard.swiftchat.ai/bots>`_.
   

.. tip:: 

   - Create your merchant account using this Post `API <https://documenter.getpostman.com/view/20587790/UyrGCuhH#57d73550-1c15-41a5-ac7e-0ba20b60b3e4>`_ 
   - Complete business KYC and email varification

2. Click on **Add New Bot** button.

.. image:: ../images/create_bot_images/add_bot.png
   :alt: Deployment Structure
   :width: 2000
   :height: 200
   :align: center


3. Clicking **Add New Bot** button will redirect you to a page where you can input the bot details, including the phone number, bot name, and bot type.Enter these details and proceed for verification. Once verification is completed, the bot will be created and activated.

.. image:: ../images/create_bot_images/bot_detail.png
   :alt: Deployment Structure
   :width: 2000
   :height: 300
   :align: center


4. Copy the bot link and save it for future reference. The link should resemble this format: 

   .. code-block:: html

      https://cgweb.page.link/?link=https%3A%2F%2Fweb.convegenius.ai%3FbotId%3D0216260609726241&apn=ai.convegenius.app. 

   - In the link, the bot ID is structured as **botId%3D0216260609726241**, where the actual ID follows the "3D" prefix. So here the ID is **0216260609726241**.


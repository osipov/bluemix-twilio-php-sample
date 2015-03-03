# Twilio

##Twilio Telephony as a Service

Twilio enables phones, VoIP, and messaging to be embedded into web, desktop, and mobile software. To try the Twilio on Bluemix, you will first need to register for a Twilio account (unless you already have one) using the following link https://www.twilio.com/try-twilio?promo=bluemix

You will also need a number that can receive text messages. This number must be verified with Twilio using the following link http://twilio.com/user/account/phone-numbers/verified

**If you are going to use PHP**

Once you are registered with Twilio and ready to try the sample Twilio application, change directory to ```twilio```  and execute the following commands from your console.

```
cf login https://api.ng.bluemix.net
cf push
```

After the command completes successfully, look for the console output specifying the application URL. It should look something like 

```
usage: 128M x 1 instances
urls: twilio-random-word.mybluemix.net
```

Take note of the URL ending with mybluemix.net (such as twilio-random-word.mybluemix.net in the example above) from the console output. You will need it later to access the application.

Twilio service must be bound to your application using the Bluemix UI. Login to Bluemix and using the Dashboard menu item, navigate to your application. Click on your application, click Add a service and choose Twilio from the catalog. On the right side bar, specify ```Twilio``` as the service name and enter the Twilio SID and token values as available from your Twilio dashboard.

A more detailed example of binding Twilio service to your application is available from https://twilio.com/blog/2014/02/twilio-and-ibm-codename-bluemix-nt.html

Next execute the following commands from your console, using your Twilio assigned phone number instead of the  ```<TWILIO_NUMBER>``` string and using a number where you want to send a text instead of ```<TEXT_NUMBER>```.

```
cf set-env twilio MY_TWILIO_NUMBER <TWILIO_NUMBER>
cf set-env twilio MY_DESTINATION_NUMBER <TEXT_NUMBER>
cf restage twilio
```

To test the application, open your favorite browser using the application URL you noted earlier, i.e the one ending with mybluemix.net.

**To install PHP pre-requisites for a local deployment** 

Via [Composer](https://getcomposer.org/)

``` bash
$ composer install
```
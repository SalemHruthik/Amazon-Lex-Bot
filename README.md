# Amazon-Lex-Bot
# Integrating an Amazon Lex Bot with Facebook Messenger<a name="fb-bot-association"></a>

This exercise shows how to integrate Facebook Messenger with your Amazon Lex bot\. You perform the following steps:

1. Create an Amazon Lex bot

1. Create a Facebook application

1. Integrate Facebook Messenger with your Amazon Lex bot

1. Validate the integration

**Topics**
+ [Step 1: Create an Amazon Lex Bot](#fb-bot-assoc-create-bot)
+ [Step 2: Create a Facebook Application](#fb-bot-assoc-create-fb-app)
+ [Step 3: Integrate Facebook Messenger with the Amazon Lex Bot](#fb-bot-assoc-create-assoc)
+ [Step 4: Test the Integration](#fb-bot-test)

## Step 1: Create an Amazon Lex Bot<a name="fb-bot-assoc-create-bot"></a>

If you don't already have an Amazon Lex bot, create and deploy one\. In this topic, we assume that you are using the bot that you created in Getting Started Exercise 1\. However, you can use any of the example bots provided in this guide\. For Getting Started Exercise 1, see [Exercise 1: Create an Amazon Lex Bot Using a Blueprint \(Console\)](gs-bp.md)\.

1. Create an Amazon Lex bot\. For instructions, see [Exercise 1: Create an Amazon Lex Bot Using a Blueprint \(Console\)](gs-bp.md)\. 

1. Deploy the bot and create an alias\. For instructions, see [Exercise 3: Publish a Version and Create an Alias](gettingstarted-ex3.md)\.

## Step 2: Create a Facebook Application<a name="fb-bot-assoc-create-fb-app"></a>

On the Facebook developer portal, create a Facebook application and a Facebook page\. For instructions, see [Quick Start](https://developers.facebook.com/docs/messenger-platform/guides/quick-start) in the Facebook Messenger platform documentation\. Write down the following:
+ The **App Secret** for the Facebook App 
+ The **Page Access Token** for the Facebook page

## Step 3: Integrate Facebook Messenger with the Amazon Lex Bot<a name="fb-bot-assoc-create-assoc"></a>

In this section, you integrate Facebook Messenger with your Amazon Lex bot\.

After you complete this step, the console provides a callback URL\. Write down this URL\.

**To integrate Facebook Messenger with your bot**

1. 

   1. Sign in to the AWS Management Console and open the Amazon Lex console at [https://console\.aws\.amazon\.com/lex/](https://console.aws.amazon.com/lex/)\.

   1. Choose your Amazon Lex bot\. 

   1. Choose **Channels**\.

   1. Choose **Facebook** under **Chatbots**\. The console displays the Facebook integration page\.

Step to step process screen shorts
![image](https://user-images.githubusercontent.com/110277557/229875672-579db591-9272-45b5-821b-91f1cd433dfc.png)
![image](https://user-images.githubusercontent.com/110277557/229875709-7cb823e8-944b-484b-bfde-5e6541779bee.png)
![image](https://user-images.githubusercontent.com/110277557/229875794-c7bf3430-5567-441b-aa19-0ea961019307.png)
![image](https://user-images.githubusercontent.com/110277557/229875822-e59e5325-8a11-427f-a8c6-ec6260f57ee0.png)
![image](https://user-images.githubusercontent.com/110277557/229875847-7b2d68cd-e69d-4602-95b5-851cdf966e87.png)
![image](https://user-images.githubusercontent.com/110277557/229875860-a3a210e7-5cc4-45cc-bfbc-2fae9dc87e27.png)
![image](https://user-images.githubusercontent.com/110277557/229875884-ba4ae34c-6f36-4b72-9b2b-afd358913418.png)
![image](https://user-images.githubusercontent.com/110277557/229875909-f1810989-9cb1-44e1-8d09-7b43506dda60.png)
![image](https://user-images.githubusercontent.com/110277557/229875932-384c433f-daa8-4e76-ad3b-5e44718ed91a.png)

![image](https://user-images.githubusercontent.com/110277557/229875962-22686040-f20f-4063-a163-b9a4e7b93b56.png)
![image](https://user-images.githubusercontent.com/110277557/229876006-91964f63-cb3d-40a7-90e9-39575981174a.png)
![image](https://user-images.githubusercontent.com/110277557/229876046-d98caf12-2b91-489c-a0bb-7a575521e5e7.png)
![image](https://user-images.githubusercontent.com/110277557/229876080-e9f877d6-9480-48b9-875b-e8976b450c30.png)
![image](https://user-images.githubusercontent.com/110277557/229876110-dc7afe6e-9941-4b65-aac0-9f928d3eb91e.png)
![image](https://user-images.githubusercontent.com/110277557/229876134-d82608b6-6dcd-4e81-b20a-d56ec838aca7.png)


   1. On the Facebook integration page, do the following:
      + Type the following name: `BotFacebookAssociation`\.
      + For **KMS key**, choose **aws/lex** \.
      + For **Alias**, choose the bot alias\.
      + For **Verify token**, type a token\. This can be any string you choose \(for example, `ExampleToken`\)\. You use this token later in the Facebook developer portal when you set up the webhook\.
      + For **Page access token**, type the token that you obtained from Facebook in Step 2\.
      + For **App secret key**, type the key that you obtained from Facebook in Step 2\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/lex/latest/dg/images/fb-10a.png)

   1. Choose **Activate**\. 

      The console creates the bot channel association and returns a callback URL\. Write down this URL\.

1. On the Facebook developer portal, choose your app\.

1.  Choose the **Messenger** product, and choose **Setup webhooks** in the **Webhooks** section of the page\.

   For instructions, see [Quick Start](https://developers.facebook.com/docs/messenger-platform/guides/quick-start) in the Facebook Messenger platform documentation\. 

1. On the **webhook** page of the subscription wizard, do the following:
   + For **Callback URL**, type the callback URL provided in the Amazon Lex console earlier in the procedure\.
   + For **Verify Token**, type the same token that you used in Amazon Lex\.
   + Choose **Subscription Fields** \(**messages**, **messaging\_postbacks**, and **messaging\_optins**\)\.
   + Choose **Verify and Save**\. This initiates a handshake between Facebook and Amazon Lex\.

1. Enable Webhooks integration\. Choose the page that you created, and then choose **subscribe**\.
**Note**  
If you update or recreate a webhook, unsubscribe and then resubscribe to the page\.

## Step 4: Test the Integration<a name="fb-bot-test"></a>

You can now start a conversation from Facebook Messenger with your Amazon Lex bot\. 

1. Open your Facebook page, and choose **Message**\. 

1. In the Messenger window, use the same test utterances provided in [Step 1: Create an Amazon Lex Bot \(Console\)](gs-bp-create-bot.md)\.

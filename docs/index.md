---
layout: default
title: Home
---

Hello World!!

# How to Send Emails with Java

Infobip offers various solutions that enable you to use emails programmatically in your software solutions. This tutorial will show you how to send a simple email in Java.
Prerequisites and Dependencies

To reproduce this solution, you'll need a few things:
**an Infobip Account**

- [x] Oracle Java or OpenJDK, version 8 or greater (we target Java 11 in our examples)
- [ ] Apache Maven v3.3.4 or greater (Gradle equivalent will work just fine as well)
- [ ] basic knowledge of Java

## Solution
All the code you'd need to run this example is already available, runnable, and tailored for you in our cloud-based IDE solution. Feel free to check it out now or after finishing this tutorial.
Project Setup
First, open the Java project you'd like to send the email with—or create a new one now.
This tutorial relies on the Infobip API Java Client. This client is open-sourced and published on relevant central repositories, easily used in projects.
To be able to use the Infobip API Java Client in your project, you'll need to add it to your project POM file under the dependencies tag:
```
<dependency>
      <groupId>com.infobip</groupId>
      <artifactId>infobip-api-java-client</artifactId>
      <version>3.1.0</version>
</dependency>
```

Next, you need to initialize ApiClient and SendEmailApi. The quickest way to set it up is by using the snippet below. Still, you can always check out the docs for further 
```
ApiClient specifics and more authentication options.
ApiClient apiClient = new ApiClient();
apiClient.setApiKeyPrefix(API_KEY_PREFIX);
apiClient.setApiKey(API_KEY);
apiClient.setBasePath(API_BASE_URL);

Configuration.setDefaultApiClient(apiClient);
SendEmailApi sendEmailApi = new SendEmailApi();
 ```
Before running the solution, don't forget to replace the placeholders we set with your account values. For example, you should replace API_KEY_PREFIX from the snippet above with "App".
Next, find your API Key and API Base URL on the portal homepage, as pictured in the screenshot below:

Replace the prefilled API_KEY and API_BASE_URL from the snippet above with the string values you found on your Infobip portal homepage.
You should have ApiClient and SmsEmailApi set up and initialized by this point. The next step is sending the email, so let's see how you can do that!

## Sending an Email
To send an email via the Infobip API, you need to provide the following required parameters:
from - Sender's email address. Who is sending the email?
to - Recipient's email address. Who is it addressed to?
subject - The email's subject line. What is the title of that email?
On top of these, one of the following fields has to be defined as well: text, html or templateId. In this case, let's use text for simplicity.
See the API Reference for additional parameters.
   EmailSendResponse sendResponse = sendEmailApi
            .sendEmail(SENDER_EMAIL_ADDRESS, RECIPIENT_EMAIL_ADDRESS, EMAIL_SUBJECT)
            .text("Nothing to see here, just a test email message body.")
            .execute();
Don't forget to replace the SENDER_EMAIL_ADDRESS, RECIPIENT_EMAIL_ADDRESS, and EMAIL_SUBJECT placeholders with your actual values.
There are a couple of things to keep in mind if you're using a trial account. You can send up to 100 free emails—make sure you also check spam, as these tests might end up in there, and the default email domain to use is selfserviceib.com.
Once you upgrade your account, you'll need to set up your domain and the restrictions no longer apply.

## Troubleshooting
Our Java Client exposes an ApiException that will provide helpful info if anything goes wrong with your request. We suggest wrapping all API calls with a try-catch block, as shown below.

```
	try {
	    EmailSendResponse sendResponse = sendEmailApi
            .sendEmail(SENDER_EMAIL_ADDRESS, RECIPIENT_EMAIL_ADDRESS, EMAIL_SUBJECT)
            .text("Nothing to see here, just a test email message body.")
	    .execute();
	} catch (ApiException apiException) {
	    // HANDLE THE EXCEPTION
	}
        ```
Run your code, and the email should be on its way!

## Next Steps
Congratulations, you just sent your first simple email using the Infobip API Java Client!
There are plenty of additional options that could make your email sending service more robust, so make sure you check out the API Reference if you'd like to build on this use case.
If you'd like to take your emails one step further—like scheduling them, sending emails in bulk, validating email recipients, receiving delivery reports, etc.—see our Email Documentation for more ideas.
You can also find sample code for the most commonly used email options in the client repository.
Remember, there's also a cloud-based IDE solution for you to try!

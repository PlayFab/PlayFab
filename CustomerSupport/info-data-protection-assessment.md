# Azure PlayFab info for data protection assessment questions

This article shares specific Azure PlayFab info for data protection assessment questions.

## Background

Your titles have access to certain types of data based on the platform it's on. From the platform’s perspective, they want to build trust with the people who use their platforms, especially in the ever-changing privacy regulatory landscape and continuously evolving threats to people’s privacy. This is why platform providers, such as Meta (formerly known as Facebook), want to know how these data is being handled by you using the [Data Protection Assessment](https://developers.facebook.com/docs/development/maintaining-data-access/data-protection-assessment/faq) (DPA).

Unfortunately, PlayFab is a service and we can't advise you on how to answer the DPA questions because how you use our services in a title is ultimately your implementation. But we want to make sure that you have the information about the portion of the backend we provide. **Our answers are for the service and not for your title.**

It’s important to note that the purpose of the DPA is to understand about your entire title implementation, and this goes beyond the PlayFab service.  PlayFab is not responsible for how your title manages data, data privacy, and data security. **You are required to answer DPA questions accurately based on your actual title implementation.**

If you have questions about DPA, contact your Meta account manager. For PlayFab related questions, go to [PlayFab forums](https://community.playfab.com/index.html).

## Protecting Backend Data at Rest With Encryption 

Do you enforce encryption at rest for all Platform Data stored in a cloud, server, or data center environment?

* If you use other backend services to store Platform Data from Meta, answer this question according to your implementation.
* If you're using PlayFab exclusively (this means that PlayFab is your ONLY backend data storage solution), this is how backend data at rest is managed. 

  * Q: Do you store Meta Platform Data within a cloud, server, or data center environment, e.g., databases (primary storage, replicas, and backups), object storage buckets, or block storage”
  * A: PlayFab doesn't do this. Our answer is no.
    
  * Q: About [data sharing](https://developers.facebook.com/docs/development/maintaining-data-access/data-protection-assessment/assessment-questions#data-sharing)
  * A: Since Playfab is provided by Microsoft, our answer is check the box for **To enable a person or business to provide a service to you (a service provider)**. Check the box for **Microsoft** in the follow up question. 

## Protecting Data in Transit With TLS 

Do you enable security protocol TLS 1.2 or greater for all network connections that pass through, or connect, or cross public networks where Platform Data is transmitted?
 
* If you transmit Meta Platform Data via peer-to-peer connections (for example, using the Party SDK) then you need to ensure that these connections require TLS before answering. Likewise, if you transmit Meta Platform Data to other services besides PlayFab you should answer this question according to your implementation.
* If PlayFab is the only backend service that you transmit Meta Platform Data to and from clients AND because all PlayFab API calls require TLS 1.2 or greater, our answer is yes to this question. 

## Testing for Vulnerabilities and Security Issues 

Do you test your app and systems for vulnerabilities and security issues at least every 12 months? For example, do you perform a manual penetration test?

* Answer this question according to your approach for testing your own custom code (as opposed to vulnerability testing of the underlying PlayFab services).
* If you use the hosted services or hosted scripts features of PlayFab, Meta requires these services to be in scope for your security test. 

## Protecting Meta API access tokens and app secrets 

Are Meta API access tokens and app secrets protected in both of the following ways? 
1.	By never storing Meta API access tokens on client devices where they are accessible outside of the current app and user. 
2.	By using a data vault (like Vault by Hashicorp) with separate key management service (KMS) if these are stored in a cloud, server or data center environment. 

Answer the client part of this question according to your own implementation. 

For the cloud part of this question:  
* If you're using other backend services besides PlayFab, answer this question according to your implementation.  
* If you're using PlayFab as your only backend data storage solution:
    * You must never write Meta API access tokens or the app secret into PlayFab. Instead, you should rely on PlayFab's login features to handle access tokens seamlessly. 
    * If you adhere to this guidance of using PlayFab login features to handle access tokens, our answer is yes to the question about whether Meta API access tokens and app secrets are protected in a cloud, server, or data center environment. 

## Requiring multi-factor authentication  

Do you require multi-factor authentication for remote access to every account that is able to connect to your cloud or server environment? 

* PlayFab supports both email/password and Azure Active Directory (Azure AD - “Sign in with Microsoft”) for developer accounts in the PlayFab Game Manager, but only Azure AD meets this Meta security requirement. 
* If the PlayFab developer account you use to access the studio with the Meta uses username/password sign in, you need to create a new developer account that uses Azure AD authentication. Configure your Azure AD account to require multi-factor authentication(MFA) for sign in, then add that account to your studio and set up the permissions you need. You also need to remove all non-Azure AD accounts from your studio, so that they can’t access your titles. 
* Once that’s done, and all accounts in your studio use Azure AD for sign in (and have MFA enabled), our answer is yes to this question.

  ![image](https://github.com/PlayFab/PlayFab/assets/16616650/d7bce7be-55a0-4df3-b88b-19fc669132c7)


## Keeping software up-to-date 

Do you have a [system for keeping system code and environments updated](https://developers.facebook.com/docs/development/maintaining-data-access/data-protection-assessment/faq#system-updates), including servers, virtual machines, distributions, libraries, packages, and anti-virus software?

* Relevant to your use of PlayFab, you should answer this question according to your approach for patching third party software that you deploy to PlayFab (as opposed to how PlayFab approaches keeping its services up to date).  
* Specifically, if you are using PlayFab Multiplayer Servers (custom game server hosting), PlayFab manages OS updates automatically. So, you should answer this question based on your approach for updating the build(s) you host with PlayFab as regards your own code and third party software such as libraries that are packaged with your software. 

## Other Meta DPA questions 

We're unable to provide info for other Meta DPA questions that are unrelated to PlayFab services. We recommend reaching out to Meta if you have any questions about other DPA questions.

## Useful links

* [Meta DPA frequently asked questions](https://developers.facebook.com/docs/development/maintaining-data-access/data-protection-assessment/faq)
* [Meta DPA assessment questions](https://developers.facebook.com/docs/development/maintaining-data-access/data-protection-assessment/assessment-questions)

# Understanding how Azure PlayFab can be used by title to manage data

This article describes ways in which Azure PlayFab can be used in your title to handle data and manage data security.

Your titles have access to certain types of data on the platform that the title is on, such as Meta (formerly known as Facebook). From the platform’s perspective, they want to build trust with the people who use their platforms, especially in the ever-changing privacy regulatory landscape and continuously evolving threats to people’s privacy. This is why platform providers want to know how these data is being handled by you using the [Data Protection Assessment](https://developers.facebook.com/docs/development/maintaining-data-access/data-protection-assessment/faq) (DPA).

Unfortunately, PlayFab can’t advise you on how to answer the DPA questions because they’re your responsibility as a developer. PlayFab is also not responsible for how your title manages data security. But we want to make sure that you have the information about the portion of the services we provide. So, we have some information here that you may use for a few of those questions, if applicable.

It’s important to note that DPA questions encompass your entire title implementation, and this goes beyond the PlayFab service. **You are required to answer those questions accurately based on your actual implementation.**

## Protecting Backend Data at Rest With Encryption 

Do you enforce encryption at rest for all Platform Data stored in a cloud, server, or data center environment?

* If you use other backend services to store Platform Data from Meta, then answer this question according to your implementation.
* If you're using PlayFab exclusively (this means that PlayFab is your ONLY backend data storage solution), this is how backend data at rest is managed. 

  * Q: [Do you store Meta Platform Data] within a cloud, server, or data center environment, e.g., databases (primary storage, replicas, and backups), object storage buckets, or block storage”
  * A: PlayFab doesn't do this. Our answer is no.
    
  * Q: About data sharing
  * A: Since Playfab is provided by Microsoft, our answer is check the box for **To enable a person or business to provide a service to you (a service provider)**. Check the box for **Microsoft** in the follow up question. 



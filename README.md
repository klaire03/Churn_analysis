
**This project utilizes a randomly generated dataset in order to protect sensitive data. The main purpose is mainly to describe the process of identifying feature importance contributing to churn rather than producing a comprehensive report and recommendations**


**Background** 

Understanding the reasons behind customer churn is vital for businesses to maintain profitability and sustain growth. Factors such as poor user experience, lack of engagement, and competitive pressures contribute to churn. This study aims to analyze user experience survey responses, app usage data, support interactions, and marketing engagement to identify specific drivers of churn within the company's customer base. 

**Objective**

By uncovering these insights, the research seeks to inform strategic decision-making processes aimed at reducing churn rates and enhancing customer retention efforts.

**Indicators**

- Low number of upgrades and renewals
- Increase in customer support tickets

**RESEARCH QUESTIONS**

**1. What are the primary drivers of customer churn within the company's customer base?**

- How do user demographics (e.g. age, gender, location, digital fluency) influence churn rates?
- What are users’ attitudes regarding the product’s offerings in terms of Privacy, Protection and Performance? To what extent do satisfaction levels with our product offerings align with the importance users place on specific features?
- Are there any significant correlations between user behaviour as observed from in-app interaction activity and customer churn?
- What are the main reasons customers raise support tickets, and how do these reasons correlate with churn behaviour?

- What does a churn look like?
- Which customers churn?
- What are the main reasons?
- Which new customers or behaviours are expected to lead to churn?


**METHOD**

**PART I** 

<aside>
💡 Who are the customers who churned?

</aside>

**Marketing data**
We first queried the Marketing database to identify: customers that have churned (not renewed their contract or dropped after trial) **subscription:** **‘renewal’, ‘trial’, ‘basic’.**

<aside>
💡 What did churned customers complain about?

</aside>

**Customer Support**
We, then, joined the output from our Marketing database query with the Customer Support data on [Customer.ID](http://Customer.ID), in order to find possible tickets and log errors that those churned customers have sent during the timeframe in question. This way we could quickly uncover some qualitative data explaining the customers’ behaviour.  **competitorMention, supportTopics, supportTickets.**

<aside>
💡 Are there any particular in-app customer behaviour that might show concerning activity ?

</aside>

**In-app analytics**
We, then, joined the newly created table (from Marketing and Customer Support) with the database storing the in-app user interactions in order to get some indications of how these customers have interacted with the product through their CTA.  



1. For this particular part of the study we collaborated with the Data Engineering team to identify what are the Good Meeting Metrics, grouping the data points we were already tracking based on wider themes, separating them in positive, neutral **[notification_settings, privacy_settings, subscription_plan etc]**or concerning interactions **[uninstall, notification_dismissals, help, manual_scan, delete_falsepos, silent_mode]**. 
2. We created a joined table with the selected data from all three tables (Marketing, Customer Support and in-app analytics), cleaned and transformed data to prepare them for the analysis. The final output was a single table that includes the list of churned customers (rows) and information about: their subscription type, tenure duration, whether they have upgraded and/or renewed their subscription, the number and type of tickets that addressed to Support (if any), and the UI components they have interacted with.

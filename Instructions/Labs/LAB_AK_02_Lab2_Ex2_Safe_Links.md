# Module 2 - Lab 2 - Exercise 2 - Implement a Safe Links Policy

Now that you have created a Safe Attachments policy for Adatum, you want to create a Safe Links policy and then validate the policy to ensure that it works properly.


### Task 1 – Create a Safe Links Policy

In this task, you will add the **tailspintoys.com** URL to the company-wide list of blocked URLs, and you will create a Safe Links policy that applies to all users in your tenant.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **Admin** account, and you should still be logged into Microsoft 365 as **Holly Dickson**.

2. After finishing the previous task, you should still be in the **Microsoft 365 Security and Compliance center**. If not, in your browser, enter **https://protection.office.com.**

3. In the **Security &amp; Compliance center**, in the left-hand navigation pane, the **Threat Management** group should still be expanded from the prior task; if not, expand it now. Under this group, select **Policy**.

4. In the **Policy** window, double-click the **ATP Safe Links** tile. This initiates the **Create Safe Links Policy** wizard.

5. On the **Name your policy** page, enter **LinkPolicy1** in the **Name** field and then select **Next**.

6. On the **Settings** page, enter the following settings: 

    - Select the action for unknown or potentially malicious URLs in messages - **On**
    - Select the action for unknown or potentially malicious URLs within Microsoft Teams - **Off**
    - Apply real-time URL scanning for suspicious links and links that point to files - select this check box
    - Wait for URL scanning to complete before delivering the message - select this check box
    - Apply safe links to email messages sent within the organization - select this check box
    - Do not track user clicks - select this check box
    - Do not allow users to click through to original URL - select this check box
   
7. In the **Do not rewrite the following URLs** field, enter the following URL and then select the **plus sign (+)** button: **http://tailspintoys.com**

8. Select **Next**.

9. On the **Applied to** page, select **+Add a condition**. In the drop-down menu that appears, under the **Applied if...** section, select **The recipient domain is**

10. In **The recipient domain is** section, select the **Choose** link to choose a domain. 

11. In **The recipient domain is** window, select the **+Add** button. In the list of domains that appear, select the check box for the **xxxxxZZZZZZ.onmicrosoft.com** domain (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider), select **Add**, and then select **Done**.

12. On the **Applied to** page, select **Next**.

13. On the **Review your settings** page, review the options that you selected. If any need to be corrected, select the appropriate **Edit** option and make the correction. If they all appear correct, select **Finish**.

14. Once the **LinkPolicy1** policy is created, it will appear in the Safe links list. 

15. Leave the Office 365 Security &amp; Compliance tab open for the next task.

### Task 2 – Validate the Safe Links Policy

In this task, you will test the Safe Links Policy that you just created that blocks links to the http://tailspintoys.com URL.

1. You should still be logged into your Client 1 VM (LON-CL1) as the **Admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In your **Microsoft Edge** browser, select the **Microsoft Office Home** tab and then select **Outlook.**

3. In the top right corner of Outlook, verify that the user icon is **HD** (for Holly Dickson). If the user icon is **HD**, then open a new tab in Edge and proceed to the next step. <br/>

    If the user icon is not **HD** (for example, if it's **MA** for the MOD Administrator), then select the user icon circle, and in the **My account** pane that appears, select **Sign out**. After you are signed out of the account, a good best practice that you should follow when signing out as one user before signing in as another is to close all other open tabs in your browser so that you don't confuse those tabs (associated with the previous user) with the new tabs that you will open for the new user. Only the tab with the sign-out message should be open. 

4. Enter the following URL in the address bar: **https://outlook.office365.com**

5. In the **Pick an account** window, select **Holly@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider). In the **Enter password** window, enter **Pa55w.rd** and then select **Sign in**.

6. On the **Stay signed in?** dialog box, select the **Don't show this again** check box and then select **Yes.**

7. On the Outlook sign in page, select your **Language** and **Time zone** and then select **Save**.

8. In **Outlook on the web**, verify that **HD** is displayed in the user icon in the upper right corner of the form.

9. Select **New Message** in the upper left part of the screen.

10. In the email form in the right-hand pane, enter the following information:

    - To: You will be sending an email to the MOD Administrator, so enter **mod** in the **To** field and then select the **MOD Administrator** email address from the user list.

    - Add a subject: **Free stuff for Adatum users**

    - body of the message: **Please click on me for free toys from TailSpin Toys.**

11. Select the text that you added in the body of the message.

12. Below the body of the message is a long row of formatting icons. Select the **Insert hyperlink** icon, which depicts two overlapping circles.

13. In the **Insert link** window, the text that you highlighted in the body of the message should be displayed in the **Display as** field. In the **Web address (URL)** field, enter the following URL: **http://tailspintoys.com/aboutus/freetoys**.

14. Select **OK**.

15. In the body of the email, the message should still be selected. Click anywhere in the body of the message to remove the highlighting. The color of the text should now be blue, and it should be underlined, indicating that this message is hyperlinked to a URL.

16. Select either **Send** button (top or bottom of the form).

17. You now want to go the MOD Administrator&#39;s Inbox in Outlook and validate whether the ATP policy you created in the prior task worked on the email that you just sent from Holly to the MOD Administrator.<br/>

    To do this, you must first switch the Client 2 VM (**LON-CL2**). 

18. Log into the LON-CL2 VM as the **Admin** account by entering **Pa55w.rd** in the **Password** field.

19. Select the **Microsoft Edge** icon in the taskbar, maximize the window and then enter the following URL in the address bar: **https://outlook.office365.com**

20. In the **Sign-in** window, enter **admin@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**.

21. In the **Enter password** window, enter the tenant password provided by your lab hosting provider and select **Sign in**.

22. Close the **Let Microsoft Edge save and fill your password for this site next time?** banner by selecting **Never**.

23. On the **Stay signed in?** dialog box, select the **Don't show this again** check box and then select **Yes.**

24. You will have to navigate through a series of **Welcome** windows. Continue selecting the right arrow (**>**) until you reach the final window, and then select **Get started**.

25. In the MOD Administrator&#39;s **Inbox**, open the email that was sent by Holly.

26. When you hover over the blue link that appears in the body of the email, you can see a long URL in the bottom of the browser window; this URL starts with **https://namXX.safelinks.protection.outlook.com** (wehre XX is a number assigned to the policy) <br/>

27. Select the hyperlink in the body of the message to open it. A new tab should open in your **Edge** browser that takes you to the URL you just saw in the prior step. This site should display the following warning message: **This website has been blocked per your organization's URL policy.** This not only indicates that opening this website might not be safe, but it also verifies that the ATP Safe Links policy you just created is working properly.

28. Leave the Client 2 VM open and leave Outlook open to the MOD Administrator's Inbox for the next lab.


# End of Lab 2


# Module 7 - Lab 7 - Exercise 1 - Implement Sensitivity labels with Azure Information Protection Unified labels client


In your role as Holly Dickson, Adatum’s Enterprise Administrator, you have Microsoft 365 deployed in a virtualized lab environment. As you proceed with your Microsoft 365 pilot project, your next steps are to implement Sensitivity Labels with Azure Information Protection (AIP) and Windows Information Protection (WIP) at Adatum. You will begin by configuring AIP and then using AIP on a client and verifying an AIP policy. You will then perform similar steps for WIP by configuring it for Adatum and then implementing WIP.

### Task 1 – Install the Azure Information Protection Unified Labeling client

To implement Sensitivity labels as part of your pilot project at Adatum, you must first install the AIP client from the Microsoft Download Center.

1. Switch to LON-CL1, where you should still be logged in as the **admin** account, and you should be logged into Microsoft 365 as **Holly Dickson** with a password of **Pa55w.rd**. 

2. In **Microsoft Edge**, open a new tab and enter (or copy and paste) the following URL in the address bar: **https://www.microsoft.com/en-us/download/confirmation.aspx?id=53018** <br/>

	This will start the download for the AIP Unified label client.

3. In the Microsoft download center tab, a notification bar will appear at the bottom of the page asking whether you want to Run, Save, or Cancel. Select **Run**.

4. The Microsoft Azure Information Protection wizard will open. If the wizard does not display on the desktop, select the icon for the wizard on the taskbar to display the wizard.

5. In the wizard, on the **Install the Azure Information Protection client** page, clear (uncheck) the **Help improve Azure Information Protection by send usage statistics to Microsoft** check box and then select the **I agree** button.

6. If a **User Accont Control notification** dialog box appears that asks whether the app is allowed to make changes to this device, select **Yes**.

7. Once the installation is complete, select **Close**.

8. In your Edge browser, close the **Download** tab that you opened in this task to download the Azure Information Protection client.

You have successfully installed the AIP Unfied Label client on Client 1 VM.


### Task 2 – Configure Sensitivity Labels

In this exercise you will create an Sensitvity label and add it to the default policy so that it’s valid for all users of the Adatum tenant.

1. You should still be logged into LON-CL1 as the **Admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In **Microsoft Edge**, select the **Data loss prevention** tab that displays the **Office 365 Security & Complaince Admin center**.

3. In the **Office 365 Security & Complaince Admin center**, in the left-hand navigation pane, select **Classification**, and then select **Sensitivity labels.**

4. In the **Home > sebnsitivity** window, three tabs are displayed across the top of the page. The **Labels** tab is displayed by default. <br/>

	On the **Labels** tab, a warning message is displayed in the middle of the screen indicating **Your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint.** <br/>
	
	Select the **Turn on now** button that appears on the right side of this message. This will enable Adatum to apply the Sensitivity labels inisde its Micrsoft 365 enviroment.

5. On the **Labels** tab, select **+Create a label** that appears in the middle of the screen on the menu bar. This initiates the **New sensitivity label** wizard.

6. In the **New sensitivity label** wizard, on the **Name and create a tooltip for your label** page, enter the following information:

	- Name: **PII**

	- Description for users : **Documents, files, and emails with PII**

	- Description for admins : **Documents, files, and emails with PII**

7. Select **Next**.

8. On the **Define the scope for this label** page, confirm that the **Files & Emails** check box is selected and then select **Next**.

9. On the **Choose protection settings for files and emails** page, select both check boxes for **Encrypt files and emails** and **Mark the content of files**, then select **Next**.

10. On the **Encryption** page, select the **Remove encryption if the file is encrypted** option and then select **Next**.

11. On the **Content Marking** page, set the **Content Marking** toggle switch to **On** and then select all three check boxes. Under each setting, select **Customize text** and then enter the following information for each option (select **Save** after entering the settings for each option): <br/>

	- Add a watermark 
		- Watermark text - **Sensitive - Do Not Share** (Hint: after entering this value, copy it so that you can paste it in the other two settings)
		- Font size - **25**
		- Font Color - **Blue**
		- Text layout - **Diagonal**
			
	- Add a header 
		- Header text - **Sensitive - Do Not Share**
		- font size - **25**
		- Font Color - **Red**
		- Align text - **Center**
			
	- Add a footer 
		- Footer text - **Sensitive - Do Not Share**
		- font size - **25**
		- Font Color - **Red**
		- Align text - **Center**

12. On the **Content Marking** page, select **Next**. 

13. On the **Auto-abeling for Office apps** page, set the **Auto-abeling for Office apps** toggle switch to **On**. This enables a series of options that you will update in the next steps.

14. Under **Detect content that matches these conditions**, select **+Add condition** and then select **Content contains**.

15. In the **Content contains** window, select the **Add** drop-down arrow and then select **Sensitibve info types**.

16. In the **Sensitive info types** window, select the **Select all** check box and then select **Add**.

17. All of the sensitive information types will be displayed. Scroll to the bottom on the window and update the following settings:

	- When Contnent Matches these conditions - select **Automatically apply the Label**

	- Display this message to users when the label is applied - enter **Sensitivie content has been dectected and will be encrypted**.
		
18. Select **Next**.

19. On the **Define protection settings for groups and sites** page, do not select either check box. Select **Next**.

20. On the **Review your settings and finish** page, review the information you entered. If any settings need to be corrected, select the corresponding **Edit** option. When all information appears correct, select **Create label**.

21. An **Error** dialog box should appear that states the generated rule blob is too long. This is to show you the maxium amount selections you can make at one time per rule, which is **49152**. <br/>

	To correct this issue, select **OK**, and then on the **Review your settings and finish** page, scroll down to the **Auto-labeling for Office apps** section and select **Edit**.
	
22. On the **Choose protection settings for files and emails** page, select **Next** on the **Encryption** page, and then select **Next** on the **Content Marking** page. This will take you to the **Auto-labeling for Office apps** page. 

23. On the **Auto-labeling for Office apps** page, to the right of the **Content contains**, select the **trash can icon**. 

24. On the **Auto-labeling for Office apps** page, under **Detect content that matches these conditions**, select **+Add condition** and then select **Content contains**.

25. In the **Content contains** window, select the **Add** drop-down arrow and then select **Sensitibve info types**.

26. In the **Sensitive info types** window, in the list of sensitive information types, select the **ABA routing number** and the **U.S. Social security Number (SSN)** check boxes, select **Add**, and then select **Next**.

27. On the **Define protection settings for groups and sites** page, select **Next**.

28. On the **Review your settings and finish** page, select **Create label**.

29. On the **Your label was created** page, select **Done**.

30. Now its time to publish the **PII** label. On the **Labels** tab, the **PII** label that you just created is the only label in the list. Select **PII** label.

31. In the **PII** window that appears, select the **Publish label** button. This initiates a **Create policy** wizard.

32. In the **Create policy** wizard, on the **Choose sensitivity labels to publish** page, the **PII** label is already listed, so select **Next**.

33. On the **Sensitivity labels to publish** window, the **PII** check box is already selected, so select **Add**.





select **Publish Labels**.

23. In the **Sensitivity Labels policy** window, under **Choose sensitivty labels to publish** select choose **Choose sensitivty labels to publish**. Then select **PII** and select **Add**.

24. In the **Sensitivity Labels policy** window, under **Choose sensitivty labels to publish** select **Next**.

25. In the **Sensitivity Labels policy** window, under **Publish to users and groups** select **Choose users or groups**.

26. In the **Publish to users and groups** window, under **Edit Locations**  select **Add**. A new window will appear select **All company** and then select **Add**.

27. In the **Publish to users and groups** window, under **Edit Locations**  select **Done**

28. In the **Sensitivity Labels policy** window, under **Publish to users and groups** select **Next**.

29. In the **Sensitivity Labels policy** window, under **Policy settings** select **PII** under the **Apply this label by default to documents and emails** section. then select the **Users must provide justification to remove a label or lower classification label** checkbox. Then select **Next**.

30. In the **Sensitivity Labels policy** window, under **Name your policy** enter the following information:

	- Name : **PII Policy**

	- Description : **This policy is to detect and apply an encryption to emails and documents that have sensitive information such as ABA bank routing numbers and US social security numbers. The user must provide an explanation for removing the classification label.**

31. In the **Sensitivity Labels policy** window, under **Name your policy** select **Next**.

32. In the **Sensitivity Labels policy** window, under **Review your policy** select **Finish**.

33. Congratulations you have successfully added a New custom label Policy name PII policy, Select **Done**.

### Task 3 – Assign an Sensitivity label to a document

In this exercise you will use the Sensitivity label that you created in the previous task to classify a document. For this task, you will sign into Microsoft Apps as Alex Wilber, who is a regular user without any elevated privileges.

1. You should still be logged into LON-CL1 as the **Admin** account, and you should be logged into Microsoft 365 as **Holly Dickson**.

2. In **Microsoft Edge**, open a new tab and enter the following URL in the address bar: **https://portal.office.com/** 

3. then sign in as **AlexW@xxxxxZZZZZZ.onmicrosoft** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**.

4. On the **Enter password** window, enter **Pa55w.rd** and select **Sign in**.

5. Open **Word online,** select **Blank document**.

6. If the **Privacy** window appears, close it.

7. In the **Word** document, type **Testing personally identifiable information (PII).**

8. There are two new additions to Word that appear as a result of having Sensitivity labels enabledat the start of this exercise: <br/>

	- In the **Home** ribbon, locate the **Sensitivity** group. 
	
	- Below the **Home** ribbon, locate the **Sensitivity dropdown**tab Congratulations you have successfully added a New custom label name PII, (**Note:** you may not see it if it hasn't been 24 hours) Select **Search**.bar. then type **Sensitivity** the select the arrow to view the newly created a label titled **PII** in the prior task, **PII** will appear in the left side of the Sensitivity label bar. 
	
	Select the **PII** button on the **Sensitivity** bar.

9. In the **Justification Required** window appears, select the following options:

	- Select Other (explain): **Testing what happens when i remove the label**

10. In the **Justification Required** window appears, select  "Change".

11. Re-apply the Senstivity label by selecting the**Sensitivity** group and then selecting **PII**

12. Enter the following text: **111-11-1111**

13. Save the file by selecting **Docutment1** from the **Header** tab in the Middle of word online. 

14. Confirm the file **Location** says **Alex Wilber>Documents**. 

15. In the **Word Online** rename the file to **ProtectedDocument** as the name of the file and then select out of the **file name** section.

16. Select the **Share** option in the top right corner.

17. Select the Anyone with the link can edit. change this to **Specific people** then select **Apply**.

18. In the **Enter a name or Email address**, Enter **Joni Sherman** and select **Send**.

You have just successfully created an AIP protected Word document that is read-only protected, and is accessible only by its creator, Alex Wilber, and Joni Sherman (with Read-only permission).


### Task 4 – Verify Sensitivity label policy

In the prior task, you created a Word document and protected it with a Sensitivty label by inserting a watermark and restricted permissions. To verify whether the protection that you assigned to the document works, you will first email the document to Joni Sherman and to your own personal email address. You will then test what functionality is possible for both Joni and Alex Wilber.

1. You should still be logged into LON-CL1 as the **Admin** account, and you should be logged into Microsoft 365 as **Alex Wilber**. 

2. If you have **Outlook on the web** open in a tab in your **Edge** browser, then select it now and proceed to the next step; otherwise, if you have a tab with the **Microsoft Office Home** page, then select the tab, select **Outlook**, and then proceed to the next step. If you have neither tab open, then in a new tab enter **https://outlook.office365.com** and sign in as **AlexW@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider).

3. In **Outlook on the web**, select **New Message** in the upper left part of the screen.

4. In the right-hand pane, enter the following email information:

	- To: Enter **Joni** and then select **Joni Sherman** from the user list. 

	- CC: Enter your own personal email address (not Holly's; in this case, enter your own email address)

	- Add a subject: **Protected Document Test**

	- Add a message or drop a file here: **If you can open the protected and restricted document attached to this email, then try to change it.**

	- Select **Attach** from the top menu and under  **Suggested Attachments**.  select **ProtectedDocument.docx** file that you created in the prior task, and then select **Open.**

5. Select **Send**.

6. Switch to LON-CL2. 

7. In LON-CL2, you should be logged into **Outlook on the Web** as **Lynne Robbins** from a previous lab exercise. Sign out as Lynne and then navigate to **https://outlook.office365.com** and sign back in as Joni Sherman (**JoniS@xxxxxZZZZZZ.onmicrosoft.com**, where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) with a password of **Pa55w.rd**.

8. In Joni’s **Inbox** in **Outlook on the web**, select the email that Holly just sent her, and then select **Open** file to open it. 

9. You should receive an notification indicating that the file is protected 

10. This will return you to **Outlook on the web** with the email still displayed in the right-hand pane. In the body of the email, the document appears in a tile, with a drop-down arrow in the lower right corner of the tile. Select the drop-down arrow, and in the menu, select **Download**.

11. In the notification bar that appears at the bottom of the screen, select **Save.** 

12. Once the file has finished downloading, in the notification bar, select **Open.**

13. **Microsoft Word** should open along with a **Sign in** window (it may open behind the Outlook window, in which case select the **Word** icon on the taskbar to bring it forward). 

14. Because the file is RMS protected and no AIP unified labeling client is installed on LON-CL2, you need to use the native RMS features of Word Microsoft Apps and register this installation to Joni’s account. <br/>

	‎In the **Sign in** window, enter **JoniS@xxxxxZZZZZZ.onmicrosoft.com** and then select **Next.** 

15. In the **Enter password** window, enter **Pa55w.rd** and then select **Sign in.**

16. In the **Use this account everywhere on your device** window that appears, select **This app only** to register this Office 365 ProPlus installation to **Joni Sherman’s** Microsoft 365 account.

17. The file should open in Word, since you assigned Joni with Read-only permission. Review the three notification bars that appear above the document. 

18. Try to change the file. Word should not recognize any keystrokes, and it should display the following message above the taskbar: **This modification is not allowed because the document is open for viewing only.** <br/>  

	‎**Note:** You have just verified that the permissions assigned to the file are working properly. Joni can read the file (since she was assigned Read-only permission), but she is unable to change it (no one was assigned Edit permission).

19. Close Word.

20. You will now test what happens when you attempt to open the document that was sent to your personal email address. Use your phone or classroom PC to access your personal email address. Open the email that you (in the role of Holly) just sent to your personal email address, and then attempt to open the attached file. 

21. You should receive a messaging indicating that you are not signed into Office with an account that has permission to access the document. You can optionally sign in with an account that has permission to access the file, or request access from the **AlexW@xxxxxZZZZZZ.onmicrosoft.com** account, or Cancel out of the operation. Select **Cancel**.  <br/>

	‎Since only Joni was assigned permission to read the document, you just verified that Azure Information Protection protected the document based on the PII policy parameters that you configured.

22. Remain signed into LON-CL2 and signed into Outlook on the Web as Joni. Do not close your browser.


# Proceed to Lab 7 - Exercise 2

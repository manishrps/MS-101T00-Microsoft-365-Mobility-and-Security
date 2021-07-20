# Module 8 - Lab 8 - Exercise 1 - Implement a Data Subject Request 

Data subject requests (DSRs) are used to search for and extract all known information on a person of interest. A DSR can come from the person in question or from an authorized source. In this exercise you will configure and export a DSR from the Office 365 Security and Compliance center.

**IMPORTANT:** You should only run a DSR if the request is made by a Data Privacy officer or a Human Resources manager. Due to data privacy legal concerns, you should NEVER run a DSR unless instructed to do so.

### Task 1 – Create a GDPR Data Subject Request

Holly Dickson is Adatum’s Enterprise Administrator. In her role as the company’s Microsoft 365 Enterprise Administrator, she is responsible for implementing Adatum’s Microsoft 365 pilot project. Holly wants to use this project to test Microsoft 365 search functionality; specifically, by creating a search request for her own personal data. 

**Note:** To perform this task, Holly must be assigned to the eDiscovery Manager role group so that she has the necessary permissions. You added Holly to this role group in Lab 1 at the same time that you added Joni Sherman to the role group. The reason why you were instructed to add Holly to the eDiscovery Manager role group in Lab 1 rather than at the start of this lab is that it can sometimes take up to an hour or more for permissions to successfully propagate. If you had assigned Holly to this role group just prior to this query, you would have received error messages involving parameter fields because her permissions would not have completed propagating. By adding Holly to this role group at the start of this course, enough time will have elapsed between then and now for the propagation to complete. 

1. Switch to LON-CL1, where you should still be logged in as the **Admin** account, and you should be logged into Microsoft 365 as **Holly Dickson** (**holly@xxxxxZZZZZZ.onmicrosoft.com)** with a password of **Pa55w.rd**. 

2. In your **Microsoft Edge** browser, select the **Microsoft 365 admin center** tab, and then in the left-hand navigation pane under the **Admin centers** group, select **Security**.

3. In the **Office 365 Security and Compliance** center, in the left-hand navigation pane select **Data privacy**, and then under it select **Data subject requests**. 

4. In the **Data subject requests** window, select **+Create a case** on the menu bar. This initiates the **New DSR case** wizard.

5. In the **Name your case** page, enter the following information and then select **Next**:

	- Name: **Holly Dickson Subject Request**

	- Description: **This is a test of the DSR resource to pull info on Holly Dickson.**

6. In the **Request details** page, select the **Data subject (the person who filed this request)** field, which displays a list of users. Select **Holly Dickson** and then select **Next**.

7. In the **Confirm your case settings** page, review your settings. If necessary, select **Edit** next to either setting to change it. If everything looks correct, select **Save**.

8. In the **Successfully created new DSR case** window, select **Show me search results**.

9. A new **Search query** window will appear and begin the query. In the detail pane on the left, scroll to the bottom, where the **Status** of the query is displayed. Wait for the status to change from **running query...** to **Completed**.  <br/>

	‎**Note:** Depending on how much data is accrued, a query can take some time to complete. For Adatum’s pilot project, they have not accrued much in the way of data, so Holly Dickson’s query should only take a minute or so to complete.

10. While you wait for the query to complete, scroll down under **Search query** in the left-hand pane to review the default query parameters. You can modify any of the parameters and save the query for future use. If you modify any of the parameters, select **Save**.

11. Once the search query is complete, scroll through the search results and review them. <br/>

	Once you are done, select the **Home** tab at the top of the page. For Holly Dickson’s case, select **Close case** to the right of the **Active** status, and then select **Yes** on the **Warning** dialog box that appears. 

12. This automatically returns you to the **Searches** tab, which displays the saved search requests. Leave this window open as you resume testing in the next task from this point.

You have created a data subject request and you have searched for the personal information of Holly. At the end of your test, you have closed the DSR case again. 


### Task 2 – Export the DSR Search Query Results

When someone files a DSR, you typically must export the results for further processing, oftentimes by legal teams that must investigate a case. In this task, Holly will export the DSR report for the previous case.

1. This task will resume from where you left off previously, which was the **Searches** tab in the **Holly Dickson Data Subject Request > CoreED > Search** window. The only existing search request is the **Holly Dickson Subject Request** that you just created and ran. <br/>

	Select the check box to the left of this search; this will open the **Holly Dickson Subject Request** window.

2. In the **Holly Dickson Subject Request** window, scroll to the bottom of the window to view search statistics of the results as well as the search query syntax. After reviewing the statistics, scroll back to the top of the pane and select the **Export report** button. <br/>

	**Warning:** Do not select the **Export results** button. If you do not look close enough, you may accidentally select the **Export results** button rather than the **Export report** button, which will cause the export report process to fail in a later step. 

3. In the **Export report** pane that appears, select the option that states: **All items, including ones that have unrecognized format, are encrypted, or weren’t indexed for other reasons**.  <br/>

	**Note:** Be careful - At first glance, the first two options appear to be similar; however, the first one **excludes** items while the second one **includes** those same items. Select the second option.

4. At the bottom of the **Export report** pane, select the **Generate report** button.

5. If a **Client Error** dialog box appears, select **OK**. 

6. When the report finishes, scroll down through the **Holly Dickson Data Subject Request** pane to review the results, and then select the **Close** button at the bottom of the pane.

7. In the **Holly Dickson Data Subject Request > CoreED > Search** window, select the **Exports** tab from the top menu. In the list of export requests, select **Holly Dickson Subject Request_ReportsOnly** to open it.

8. In the **Holly Dickson Subject Request_ReportsOnly** pane that appears on the right, scroll down to the **Export key** section and select the **Copy to clipboard** option that appears below the export key. You will paste in this key in a few more steps.

9. At the top of the **Holly Dickson Subject Request_ReportsOnly** pane, select the **Download report** button. In the notification bar that appears at the bottom of the page, select **Open**.

10. An **Application Install – Security Warning** window will appear that wants to install the **Microsoft 365 Office 365 eDiscovery Export Tool**. Select the **Install** button.

11. When the **eDiscovery Export Tool** is installed, you need to paste in the export key that you just copied to the clipboard. In the **eDiscovery Export Tool** dialog box, select into the **Paste the export key that will be used to connect to the source** field and then press **Ctrl+V** to paste in the key. 

12. Select the **Browse** button next to the **Select the location that will be used to store downloaded files** field, and in the **Browse For Folder** window, select the **Documents** folder and then select **OK**.

13. In the **eDiscovery Export Tool** window, select **Start** to begin the export process.

14. As soon as the **eDiscovery Export Tool** shows three green checkmarks with a **The export completed successfully** message below them, the export is done. Select the link that appears next to **Export Location**.

15. This opens a **File Explorer** window. Double-click the **results.csv** file to open Excel and view the report data for all DSR case items found. When you're done, close the Excel spreadsheet and then close the **File Explorer** window.

16. Close the **eDiscovery Export Tool** by selecting the **Close** button, and then close the **Holly Dickson Subject Request_ReportsOnly** window.

17. In your browser, close all tabs EXCEPT for the **Microsoft Office Home** tab and the **Microsoft 365 admin center** tab. 

You have successfully exported a DSR case report to your local computer. Note: Because the report contains only a report and not the message or document content, you could not process this report to fulfill the DSR's legal requirements.


# Proceed to Lab 8 - Exercise 2

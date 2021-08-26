# Learning Path 10 - Lab 9 - Exercise 5 - Manage and Monitor a Device in Intune

Holly Dickson wants to make managing devices easier, so she has decided to implement Microsoft Intune device categories in her pilot project. Implementing device categories will enable her to automatically add devices to groups based on categories that she defines.

As part of managing devices in Intune, Holly will create dynamic groups in the Microsoft Endpoint Manager admin center, based on the device category and device category name. After you configure device groups, users who enroll their device will be presented with a list of the categories you configured. After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.

### Task 1: Create device categories

In this task, you're going to create two device categories, one for mobile devices and the other for desktop systems. These categories will then be assigned to devices in the next task.

1. You should still be logged into Microsoft 365 as Holly Dickson (**holly@xxxxxZZZZZZ.onmicrosoft.com)** with a password of **Pa55w.rd**.

2. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open. In the left-hand navigation pane, select **Devices**. 

3. In the **Devices | Overview** window, in the middle pane under the **Other** section, select **Device categories.**

4. In the **Devices | Device categories** window, select **+Create device category**.

	![](images/md1.png)

5. On the **Create device category** window, the top of the page shows the 3 steps involved in creating a device category. In step **1 - Basics**, enter **Desktop** in the **Name** field and then select **Next**.

	![](images/md19.png)

6. On the step **2 - Scope tags** window, you will not define any scope tags, so select **Next**. 

7. On the step **3 - Review + create** window, select **Create**.

8. Leave all browser tabs open for the next task.

### Task 2: Manage the enrolled devices

In this task, you're going to manage the Category property of the two devices that are joined to Azure AD and enrolled in Microsoft Intune. You will also review the properties and discovered apps on each device.

1. You should still be logged into Microsoft 365 as Holly Dickson (**holly@xxxxxZZZZZZ.onmicrosoft.com)** with a password of **Pa55w.rd**.

2. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open and it should be displaying the **Devices | Device categories** window after having completed the prior task.

3. In the **Devices | Device categories** window, scroll to the top of the middle pane and select **All devices**.

4. On the **Devices | All devices** window, select **Lab VM (VM-XXXXXX)**, which is the device that Holly joined to Azure AD, and which was automatically enrolled to Intune.

	![](images/md4.png)

5. On the **Lab VM** window, review the device details. Also review the actions available on the menu bar at the top of the page; these are the actions that you can perform against the device.

6. On the **Lab VM** window, in the left-hand pane under the **Manage** section, select **Properties**. 

7. In the **Lab VM | Properties** window, note the current value of the **Device category** field is **Unassigned**. Select the drop-down arrow for this field and in the menu, note the appearance of the Desktop device category that you created in the prior task. Select **Desktop**, and then on the menu bar at the top of the page, select **Save**.<br/>

	![](images/md5.png)

    **Note:** For Android or iOS devices, you must select the **Device category** during enrollment.

8. In the **Lab VM | Properties** window, in the left-hand pane under the **Monitor** section, select **Hardware.**

9. In the **Lab VM | Hardware** window, review the hardware information that synced from the device. Then scroll down and review the **Conditional access** section at the bottom of the page.

	![](images/md6.png)

10. In the left-hand pane under the **Monitor** section, select **Discovered apps** and review the list of apps that were discovered on the device.

	![](images/md7.png)

11. In the **Lab VM | Discovered apps** window, note the navigation thread at the top of the windows (**Dashboard > Devices > VM-XXXXXX**). Select **Devices** in this thread. This returns you to the **Devices | All devices** window.

12. Leave all browser tabs open for the next task.

### Task 3: Create dynamic groups for the device categories

1. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open. In the left-hand navigation pane, select **Groups**. 

2. In the **Groups** window, select **+New group** on the menu bar.

	![](images/md8.png)

3. In the **New Group** window, enter the following information:

    - Group type: **Security**
    - Group name: **Desktop Devices**
    - Membership type: **Dynamic Device**

4. Under the **Dynamic device members** section, select **Add dynamic query**.

	![](images/md9.png)

5. On the **Dynamic membership rules** window, hover your mouse over the row to display the rule fields, and then enter the following values:

    - Property:   **deviceCategory**
    - Operator: **Equals**
    - Value: enter **Desktop Devices** (Note: This must match the spelling of the corresponding category that you created, which in this case is Mobile Device)

6. Select in the **Rule syntax** field and the query syntax will appear.

7. Select **Save** on the menu bar at the top of the page.

	![](images/md10.png)

8. On the **New Group** window, select the **Create** button at the bottom of the page. The **Desktop Devices** group should now appear in the list of groups.

9. Leave all browser tabs open for the next task.

### Task 4: Create a conditional access policy

The modern security perimeter now extends beyond an organization's network to include user and device identity. Organizations can utilize these identity signals as part of their access control decisions.

Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational policies. Conditional Access is at the heart of the new identity-driven control plane.

In this task, you will create a conditional access policy that Holly plans to implement in her pilot project. 

1. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open. In the left-hand navigation pane, select **Endpoint Security**. 

2. In the **Endpoint security | Overview** window, in the middle pane under the **Manage** section, select **Conditional access**.

	![](images/md11.png)

3. In the **Conditional Access | Policies** window, select **+New policy** on the menu bar.

	![](images/md12.png)

4. On the **New** pane, in the **Name** field, enter **Conditional1** and then select the **Users and groups** section.

5. On the **Users and groups** pane, select the **All users** option.

	![](images/md13.png)

6. On the **New** pane, select the **Cloud apps or actions** section.

7. On the **Cloud apps or actions** pane, select the **Select apps** option.

8. In the **Select** pane that appears, enter **Exchange** in the Search field. In the list of search results, select the check box for **Office 365 Exchange Online**, and then select the **Select** button at the bottom of the pane.

	![](images/md14.png)

9. On the **New** pane, select the **Conditions** section.

10. On the **Conditions** pane, select the **Device platforms** section.

11. On the **Device platforms** pane that appears, in the **Configure** field, select **Yes**. In the **Include** tab, select the **Select device platforms** option and then select the **Windows** check box. Select **Done**.

	![](images/md15.png)

12. On the **New** pane, under **Access Controls**, select the **Grant** section.

13.  On the **Grant** pane that appears, select the **Require device to be marked as compliant** check box, and then select the **Select** button.

	![](images/md16.png)

14. On the **New** pane, under **Access Controls**, select the **Session** section.

15. In the **Session** pane that appears, review the explanation but do not select any option. Select the **X** in upper right corner to close the pane.

16. On the **New** pane, select the **Create** button at the bottom of the pane. The **Conditional1** policy now appears in the policy list.<br/>

	![](images/md17.png)

17. You created a conditional access policy to become familiar with the available options; however, the policy is not effective because you didn't enable it. To enable the policy, select the **Conditional1** policy in the policy list.  

18. In the **Conditional1** pane, the **Enable policy** setting appears at the bottom of the pane. By default, it's set to **Report-only**. Select **On** and then select **Save**.

	![](images/md18.png)

You have now created a conditional access policy and enabled it for Adatum's pilot project.


# End of Lab 10

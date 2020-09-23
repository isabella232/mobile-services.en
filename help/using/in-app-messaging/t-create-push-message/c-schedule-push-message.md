---
description: In the Adobe Mobile Services UI, you can schedule a push message to be delivered immediately, to be delivered later, and as a recurring event. These events can be scheduled on a daily, weekly, or monthly basis.
keywords: mobile
seo-description: In the Adobe Mobile Services UI, you can schedule a push message to be delivered immediately, to be delivered later, and as a recurring event. These events can be scheduled on a daily, weekly, or monthly basis.
seo-title: Schedule  Push Message
solution: Experience Cloud,Analytics
title: Schedule  Push Message
topic: Metrics
uuid: 6810e27a-016f-4286-8fe2-9972d85fa326
---

# Schedule: push messages{#schedule-push-message}

In the Adobe Mobile Services UI, you can schedule a push message to be delivered immediately, to be delivered later, and as a recurring event. These events can be scheduled on a daily, weekly, or monthly basis.

>[!TIP]
>
>Users can modify the scheduling settings for a push message job at any time. If there is no applicable date to send a recurring scheduled message, for example, a monthly recurring job every 31st day, on February 31st, or the 5th Tuesday of the month, no message is sent.

Remember the following information:

* The correct date and time format is `hh:mm` and `mm/dd/yyyy`.

* You can edit a scheduled message in the following ways:

  * Change the date to a later date.
  * Change the repeat interval to another interval.

    For example, if you originally had a message that was sent every day, you can switch the recurrence to weekly.

## Before scheduling recurring push messages

You **must** understand the following information before scheduling recurring push messages:

* The options that are displayed in the **[!UICONTROL Repeat]** drop-down list depend on the date you typed or selected.

  For example, if you typed `Saturday, October 7`, the following options are displayed:

  * **[!UICONTROL Never]**
  * **[!UICONTROL Every day]**
  * **[!UICONTROL Every Saturday]**
  * **[!UICONTROL Day 7 of Every Month]**
  * **[!UICONTROL 1st Saturday of Every Month]**

* Push messages are scheduled and sent based on Greenwich Mean Time (GMT).

  For example, if you scheduled a recurring message to be sent every Saturday at 12:00 pm (noon) **PST**, starting on October 7, the message will actually be sent on Saturday at 7 pm **GMT**.
* Messages are sent differently depending on whether you are located in the U.S., Europe, or Asia.

  For example, if you are located in San Jose, California, and you schedule a message to be sent on ***October 31*** at 5:30 pm **PST**, the message is actually sent on ***November 1*** at 12:30 am **GMT**. If you are located in Tokyo, and you schedule a message to be sent on ***January 1*** at 5:30 am, it will be sent on ***December 31*** at 8:30 pm **GMT**.
* Push messages are sent an hour earlier or later depending on when day light savings occurs.
* When you look at your push messages report, the message is displayed in the local time zone of your system.

  For example, if your start time is 12:00 pm **PST**, although the message will be sent at 7pm **GMT**, the message report will display the time sent as 12:00 pm **PST**.

## Schedule a recurring push message {#section_675BD754E5A04423A1751193698A978F}

1. On the Schedule page for a new push message, select **[!UICONTROL Scheduled]** or **[!UICONTROL Now]**.

   For more information, see [Create a push message](/help/using/in-app-messaging/t-create-push-message/t-create-push-message.md).

   If you selected **[!UICONTROL Now]**, the message is pushed immediately. To prevent the message from being scheduled immediately, click **[!UICONTROL Save as Draft]**.

   ![](assets/schedule-push-message.png)

1. If you selected **[!UICONTROL Scheduled]**, click the calendar icon and select or type a start date.
1. Type a time.&nbsp;
1. Under **[!UICONTROL Repeat]**, select one of the following options:

    * **[!UICONTROL Never]** 
    * **[!UICONTROL Every day]** 
    * **[!UICONTROL Every Tuesday]** 
    * **`<Day x>` of the month** 

      The displayed options change depending on the day you selected or typed as the start day.
    * **`<nth day>` of Every Month** 

      The displayed value changes depending on which date you selected or typed as the start date.

1. In **[!UICONTROL End Repeat]**, type an end date and time.
1. Click one of the following options:

    * **[!UICONTROL Save as Draft]**

      This option saves the message in a draft format. You can choose this option to save an unfinished message or to save the message so that someone else can edit and approve the message before activating it. 
  
      If you selected **[!UICONTROL Now]** in the previous step, the draft message is sent immediately on activation. If you selected a date and time to push the message, the message is pushed according to this schedule.

    * **[!UICONTROL Save & Schedule]**

      This option sends the message on the scheduled day and time.

To push the draft message later, complete one of the following tasks:

* Click **[!UICONTROL Manage Messages]**, select the check box next to the message, and click **[!UICONTROL Activate Selected]**.
* Click **[!UICONTROL Save & Send]** to save the message and send it.

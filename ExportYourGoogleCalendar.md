# Export Your Calendar Test Report

This task requires Testers follow the Testing Procecure and Reporting guidance here: [README.md](README.md).

# Guidance

F&CO's app "Export Your Calendar" (EGC) (see webpage: [https://freytag.us/export-google-calendar](https://freytag.us/export-google-calendar)) test results are reported here.

We want to hear particularly about _data_ errors.  If EGC returns: none, too-little, or more than expected events for the date-range or if the event data is incompelete or changed _we want to know:_
~~Every feature of the app needs to be tried multiple times various ways in an effort to break it.  If something is unclear or doesn't work as you expect we want to know:~~

1. what you did *exactly* to create the issue, 
2. what you expected the app to do, and 
3. what actually happened - with screenshots of the issue.  
4. we need access to a calendar with the events supporting the problem.  
  * for Google Calendar: grant our user ```teamfreytag@gmail.com``` access to the specially-created Google Calendar having the problematic events.
  * for Outlook Web Calendar: [export to ICS file from Outlook Web instuctions](export_to_ICS_file_from_Outlook_Web.md)
5. We also need to know the start and end times of the debugging session so we can look at what our backend system reports to make sure it is working properly.  

The usual version of EGC linked to from the website is *NOT* the version to be tested (though it is similar).  To Test EGC you must have [established a Tester relationship](README.md) with F&CO.  After that F&CO will ahve configured the Microsoft Store to grant you _specifically_ permission to download the latest version of EGC.  That permissions grant must be to an email address registered with, and used to log into, a copy of Windows 10 or Windows 11.  Our software is downloaded from the Microsoft Store hence the need for the valid Windows 10/11 login email address.  Your specific Microsoft Store email address will allow you, and only you, to be able to download the Tester version of EGC.

NOTE: do not be confused by EGC's several names in various documents:

- Google Calendar
- Google Calendar - Microsoft Edition
- Export Google Calendar
- Export Your Google Calendar

... they are all the same EGC whose name has been changed because Microsoft and Google have changed their naming rules over time.

# How To Do Testing

## Before Starting

We need:

1. your Windows 10 or Windows 11 email address to grant you access and
2. the fee you would require for the test.

Please pull down the older version of EGC and use its feature set to determine how much work it would take to test with screenshots.  Then please tell us the total cost for completing this task.  Thank you.

_Please do not pay for our app.  That would actually ruin the test._

The Test EGC is similar to the EGC already in the store so you can look at that app (you are not charged to download the app), to see roughly how complicated the task will be.

*Do not start this task until:*

1. we have your email address,
2. agreed to your fee, and
3. agreed to a delivery date.

## Reporting Results

We need test reports that give screenshots, and data, with explanations of what was done to reproduce the bug along with screenshots.  _Our being able to reproduce bugs is a condition of report acceptance._

1. Clone this repository to your github account and
  * insert your results to ExportYourGoogleCalendar.md, following the example for previous tests, at the bottom of this document in [GitHub Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
2. It will often be necessary to insert a picture to explain the bug setup and end conditions.  Put this picture in a folder in the same repository as the markdown file outlining your tests (see the [markdown guide](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for the corrrect syntax).
3. To submit your report (edits to this repo with screenshots) issue to pull request addressed to our GitHub account: ```fandco-public```  
   

Follow the example of previous tests seen in the *Tests and Results* section below when reporting your results.

The report will be in markdown (*.md) format and will consist of:

* bug setup condition,
* **name of calendar or an included ```.ics``` file with the data used to reproduce the bug** and
* failure condition screenshots,
* with text explaining how to reproduce the bug.  

_Please only document the setup conditions and result that is considered a bug with a screenshots of the setup and result._  ~~Bugs include behavior you did not expect, so open to your professional judgement.~~

Remember to **cover up all personal information in your submitted screenshots** leaving only the information needed to understand and reproduce the reported bug.

You may use markdown editors such as [Typhora](https://typora.io/) to produce your report.

## Goal

The detailed delivery requirements are [here](README.md).  It's short and repeats the introductory description we gave you during negotation so you don't need to dig through prior messages.

We want a test of: https://apps.microsoft.com/store/detail/export-your-gcalendar/9PNSMQ2SW74K

This will be be a test of of a Win10/11 desktop app "Export Your Google Calendar" (EGC) downloaded from the Microsoft Store from a special package flight only available to you (and other testers, this is why we need the email address you use when buying from the Microsoft Store).  This download will be tied to your Outlook/Hotmail email address that you use to buy things in the Microsoft Store.  You will not be expected to buy something but you will need to use this email to download the free app and the free 'test' addons in the app.  

The report will be public and delivered on GitHub.  Public bug reports show our customers the app is actively maintained and _give you, the Tester, a public example of your work._

The full test will use every feature multiple times with multiple types of data.  Bug are explicit exceptions, crashes, data error (incomplete, excessive, or mangled events).  ~~but also point where the app seems confusing to the tester in their professional opinion.~~

# Tests and Results

## rfreytag - 20240307

### BUG: 0000016 (Error calling ThankYouPage)
- When the user purchases the addon, the app throws an exception instead of opening the ThankYouPage.  

#### ANSWER

Fixed in 5.1.18.0.


### BUG: 0000015 (Indicate that processing is underway)
- When the user clicks the "Submit" button, the app should indicate that processing is underway.  This is especially important when the user has selected a large date range and the app is retrieving a large number of records.  The user should not be left wondering if the app is working or if it has crashed.

#### ANSWER

Use a 'busy' cursor in the application until the retrieval is complete.  Also provide a "percent retrieved" progress indicator.  Fixed in 5.1.18.0.


### BUG: 0000014 (Outlook limits to 1825 days)
- Outlook API refuses to return more than 1825 days of data.  This is a limitation of the Outlook API and not a bug in the application.  

#### ANSWER

Break retrieval into 1820 day chunks.  Fixed in 5.1.18.0.


### BUG: 0000013 (Clearer Purchase Status)
- Make it clearer that the app has not been purchased...

![Clearer purchase status notification](ExportYourGoogleCalendar_screenshots/Make_it_clearer_the_app_is_not_purchased.PNG)

#### ANSWER

Move the status text and purchase button to the top of the left panel.  Make the purchase button red.  Fixed in 5.1.18.0.


### BUG: 0000012 (Retrieving records is too subtle)
- When records are being retrieved there is no sense that a long task is waiting to complete.  
- Also, there is no sense of how many records are being retrieved.

![Retrieving records is too subtle](ExportYourGoogleCalendar_screenshots/Retrieving_records_is_too_subtle.PNG)

#### ANSWER

Use a 'busy' cursor in the application until the retrieval is complete.  


### BUG: 0000011 (Serviced Calendar Types as Radio Buttons)
- The list of calendars should be two radio buttons.  This way the user knows what types of calendars can be downloaded from.  Presently the drop-down listbox hides the alternative calendar download types.  

![EGC uses dropdown listbox for calendar lists](ExportYourGoogleCalendar_screenshots/EGC_uses_dropdown_listbox_for_calendar_lists.PNG)

#### ANSWER

Use radio buttons to display and select which cloud calendar from which the download is to be effected.  Fixed in 5.1.18.0.


## kamran1400aw - 20230918

### BUG: 0000010 (Total Entries after SignOut Error 9)
- when a user signout from the application and straight away signs in again and without selecting any dates they can see the previously viewed number of total entries label under the submit button. I think once they use is signout they should not be able to view how many entries they viewed previously.  Instead a completely new session should start.

![TotalEntriesafterSignout](ExportYourGoogleCalendar_screenshots/TotalEntriesafterSignout.png)

##### ANSWER

Fixeed in version 5.1.18.0.


### BUG: 000009 (Reset Purchase Error 8)
- when user press reset purchase button one time and for few seconds nothing happens and then i click again and nothing happened and after that, i clicked that button multiples times then all of sudden popup error message kept coming for the number of times i clicked that button.

![ResetPurchaseErrorMessage](ExportYourGoogleCalendar_screenshots/ResetPurchaseErrorMessage.png)

#### ANSWER

The "reset purchase button" is for testers only and not present in the live application.  There is a delay in calling the Microsoft Store API that is longer if your Internet service is slow.  The exception you see, while alarming, does not affect the "purchase reset" nor will it be seen by customers since the feature is removed in the live version, v5.1.18.0.


### BUG: 000008 (Abbreviations issues 7)
- In the help section you didn't mention all the abbreviations. In some places it's "dddd" and somewhere else it's just "d".  All teh abbreviations shoiuld be mentioned in the help popup.

  ![AbbrevationsMissing](ExportYourGoogleCalendar_screenshots/AbbrevationsMissing.png)

#### ANSWER

All allowable formats are now present in the pop-up help window.  Fixed in 5.1.18.0.


### BUG: 000007 (Recurrence and attendees data issues 6)
- Recurrence and attendees data appears more like a backend code. it should have been a plain text because there is just too much info and seems like one column is getting a lot of info. like comments, additional guests, email, ID, resources, and a lot more. I think if this column is just for attendees then the data should be attendees' name and not all this info appearing as a code.
- Also if you look at the screenshot and the column of Recurrencee then you will see two rows showing some sort of code and also if users wants to export a data then results should be plain test and there should be null written in each box if there is no data.

![screenshot RecurrenceandattendeesdataIssue](ExportYourGoogleCalendar_screenshots/RecurrenceandattendeesdataIssue.png)

#### ANSWER

Recurring and attendee records are saved in a relatively complex JSON record which is not consistent between Outlook (a new calendar we service) and Google Calendar.  

To handle the recurring events data there is now an "Expand recurring events" button which will replace the JSON stating the recurrence pattern with a new record for each date (please see screenshots 'RecurringEventsExpanded' and 'RecurringEventsNOTExpanded' below).

![screenshot 'RecurringEventsExpanded'](ExportYourGoogleCalendar_screenshots/RecurringEventsExpanded.PNG)

![screenshot 'RecurringEventsNOTExpanded'](ExportYourGoogleCalendar_screenshots/RecurringEventsNOTExpanded.PNG)

The attendees list is represented in plain text separated by ';'s in both the Outlook and Google Calendar results.  

Both issues fixed in 5.1.18.0.


### BUG: 000006 (Button Text Need Space Issue: 5)
- Help & Feedback, About Product and How to use the app? buttons need a few fixes. First of all the button width and height are fixed compared to the other buttons on the app.
  
- Secondly, there is no space before and after the test within the button as you can see it's almost touching the edges.
  
- The third Button design on the app is changing and All button designs should be Uniform throughout the application. Currently, on one page we can see Round edges buttons, Straight edges buttons, and buttons that have both round and straight edges.
  
- Help & Feedback button fonts are bold where as the other two buttons are not bold.

![screenshot ButtonTextNeedSpace](ExportYourGoogleCalendar_screenshots/ButtonTextNeedSpace.png)

#### ANSWER

The buttons have been moved to the bottom bar and now follow a conventional button format.  However, the "Support & Feedback" button remains distinct with a red font so as to attract the user's attention (see included image below).  Fixed in v5.1.18.0.  

![screentshot 'Answer_Help_buttons_uniform_and_at_bottom'](ExportYourGoogleCalendar_screenshots/Answer_Help_buttons_uniform_and_at_bottom.PNG)


### BUG: 000005 (GitHub Issue:4) 

When a user clicks on the change language option and selects any language. It logout users and then users have to sign in once again to see the changes.  This issue is still the same even on this version of the application.

#### ANSWER

When language button is clicked pop-up warning to user that changing the language will lose the user's unsaved work.

#### RETEST

Confirmed fixed in 5.1.18.0 - Pop-up warning appears that the application will retstart and the user must click 'ok' to continue and change the language.


### BUG: 000004 (GitHub Issue:3)

The total Entries label is hidden behind the Help & Feedback, About Product, and How to use app buttons. These three buttons should be moved slight down!

![screenshot 'Total_Entries.png'](ExportYourGoogleCalendar_screenshots/Total_Entries.png)

#### ANSWER

Change UI so compressing the app window stops at the point screen elements (including collapsed/hidden elements) might become obscured.

#### RETEST

Confirmed fixed - minimum frame and window sizes work to prevent this problem in 5.1.18.0


### BUG: 000003 (GitHub Issue:2)

Users are able to pick the custom date format first time without any issue but when the user tries to change it, it doesn't work.  Only way for users to change is either reset or close application and reopen everything.

![screenshot 'Custom_DateTime_Formate'](ExportYourGoogleCalendar_screenshots/Custom_DateTime_Formate_anonymized.png)

#### ANSWER

Fixed in version 5.1.18.0.  User can change the date format and then submit a new request.  The dates on the returned data are displayed in the requested new format.


### BUG: 000002 (GitHub Issue:1)

Submit Button is hidden behind the Export to CSV button. When users are in normal full-screen view they can't even see if there is a button there but if they drag the right panel toward the right side only then they know there is a button behind Export to CSV. This button should be placed either on top of Export to CSV or at the very bottom.

![screenshot 'Submit_Button.png'](ExportYourGoogleCalendar_screenshots/Submit_Button_anonymized.png)

#### ANSWER

The stackframe holding the bottom buttons should not be able to compress the frame/buttons above it when the app window bottom is moved upwards.  The whole app window should refuse to continue to compress beyond the point where content becomes hidden.  

### RETEST

Confirmed fixed - minimum frame and window sizes work to prevent this problem in 5.1.18.0


## Jakdevelop1 - 20230920

### BUG: 000001

The application "Export Your Google Calendar" (ECG) was tested multiple times with different screen interactions and input. However, the application behaves perfectly normally for all features except for one part. The "Change Language" feature is not working as it should work for a normal user. After opening the application, the system asks the user to sign in with email and password to import contacts as shown in the below screenshot # 1.

![screenshot # 1](ExportYourGoogleCalendar_screenshots/Screen1.png)

On the main screen, the user clicks on "Change Language" and the application shows different available languages for translation as shown in screenshot # 2.

![screenshot # 2](ExportYourGoogleCalendar_screenshots/Screen2.png)

After selecting a language (for eg; Arabic), the application asks the user to sign in again as shown in screenshot # 3. Instead, the application should translate without asking the user to sign in every time the user changes the language. After the change in language, the user has to do all the steps again like allowing contacts permissions to the application. (which was already done in start after sign in as shown in screenshot # 4) 

![screenshot # 3](ExportYourGoogleCalendar_screenshots/Screen3.png)

![screenshot # 4](ExportYourGoogleCalendar_screenshots/Screen4.png)

#### ANSWER

When language button is clicked pop-up warning to user that changing the language will lose the user's unsaved work.

#### RETEST

Confirmed fixed in 5.1.18.0



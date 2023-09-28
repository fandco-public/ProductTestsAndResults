# Export Your G-Calendar Test Report

This task requires Testers follow the Testing Procecure and Reporting guidance here: [README.md](README.md).

# Guidance

F&CO has a new version of our app "Export Your G-Calendar" (EGC) that needs testing (see webpage: https://freytag.us/export-google-calendar)

Every feature of the app needs to be tried multiple times various ways in an effort to break it.  If something is unclear or doesn't work as you expect we want to know: 

1. what you did *exactly* to create the issue, 
2. what you expected the app to do, and 
3. what actually happened - with screenshots of the issue.  
4. We also need to know the start and end times of the debugging session so we can look at what our backend system reports to make sure it is working properly.  

The usual version of EGC linked to from the website is *NOT* the version to be tested (though it is similar).  To Test EGC you must have [established a Tester relationship](README.md) with F&CO.  After that F&CO will ahve configured the Microsoft Store to grant you _specifically_ permission to download the latest version of EGC.  That permissions grant must be to an email address registered with, and used to log into, a copy of Windows 10 or Windows 11.  Our software is downloaded from the Microsoft Store hence the need for the valid Windows 10/11 login email address.  Your specific Microsoft Store email address will allow you, and only you, to be able to download the Tester version of EGC.

NOTE: do not be confused by EGC's several names in various documents:

- Google Calendar
- Google Calendar - Microsoft Edition
- Export Google Calendar
- Export Your Google Calendar

... they are all the same EGC whose name has been changed because Microsoft and Google have changed their naming rules over time.

# Onboarding and Doing the Task

## Permission 

We need:

1. your Win10 email address to grant you access and
2. the fee you would require for the test.

Please pull down the older version of EGC and use its feature set to determine how much work it would take to test with screenshots.  Then please tell us the total cost for completing this task.  Thank you.

_Please do not pay for our app.  That would actually ruin the test._

The Test EGC is similar to the EGC already in the store so you can look at that app to see roughly how complicated the task will be.

*Do not start this task until we have fully outlined the task, your fee, and agreed on a delivery date.*

## Results

In GitHub, we'd want a markdown file giving your tests. Where appropriate you would insert a reference to a picture in a folder in the same repository as the markdown file outlining your tests.

I think you need an example of the test results format.  Here is an app manual we wrote on GitHub: https://github.com/fandco-public/Freytag-and-Company-LLC-Docs/blob/main/HOWTO-App-Publisher-for-Microsoft-Store-Usage.md

We're looking for a test report that gives screenshots with explanations of what was done to reproduce the bug along with screenshots.  Our being able to reproduce bugs is a condition of report acceptance.

You may use markdown editors such as [Typhora](https://typora.io/) to produce your report.

*Please only document the setup conditions and result that is considered a bug with a screenshots of the setup and result.  Bugs include behavior you did not expect, so open to your professional judgement.*

## Goal

The actual delivery requirements are [here](README.md).  This is simply that introductory description we gave you during negotation so you don't need to dig through prior messages.

We want a test of: https://apps.microsoft.com/store/detail/export-your-gcalendar/9PNSMQ2SW74K?hl=en-us&gl=us&cid=egc-freytagwebsite-b5d1d7&rtc=1

This will be be a test of of a Win10/11 desktop app "Export Your Google Calendar" (EGC) downloaded from the Microsoft Store from a special package flight only available to you (and other testers).  This download will be tied to your Outlook/Hotmail email address that you use to buy things in the Microsoft Store.  You will not be expected to buy something but you will need to use this email to download the free app and the free 'test' addons in the app.  

The report will be private and delivered on GitHub and only shared with the GitHub account 'fandco-public'.  The report will be in markdown (*.md) format and will consist of: bug setup condition and failure condition screenshots, with text explaining how to reproduce the bug.  

The full test will use every feature multiple times with multiple types of data.  Bug are not only explicit exceptions and crashes but also point where the app seems confusing to the tester in their professional opinion.

# Tests and Results

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
A warning dialog has been inserted, confirming from user that he wants to continue with it.

## kamran1400aw - 20230918

### BUG: 000002 (GitHub Issue:1)

Submit Button is hidden behind the Export to CSV button. When users are in normal full-screen view they can't even see if there is a button there but if they drag the right panel toward the right side only then they know there is a button behind Export to CSV. This button should be placed either on top of Export to CSV or at the very bottom.

![screenshot 'Submit_Button.png'](ExportYourGoogleCalendar_screenshots/Submit_Button_anonymized.png)

#### ANSWER

The stackframe holding the bottom buttons should not be able to compress the frame/buttons above it when the app window bottom is moved upwards.  The whole app window should refuse to continue to compress beyond the point where content becomes hidden.  

### BUG: 000003 (GitHub Issue:2)

USers are able to pick the custom date formate first time without any issue but when they user the app and tries to change it. It doesn't work. Only way for users to change is either reset or close application and reopens every thing.

![screenshot 'Custom_DateTime_Formate'](ExportYourGoogleCalendar_screenshots/Custom_DateTime_Formate_anonymized.png)

#### ANSWER

As the user interacts with the custom date format input field, the system dynamically displays a dropdown menu, filtering its contents based on the user's input. Even when the user removes characters using the backspace key, the dropdown reappears, offering relevant options.

To enhance the user experience, we've added a convenient 'X' button next to the input field. Clicking this button instantly clears the contents of the custom date format input field, and the dropdown menu promptly reappears, ready to assist the user in selecting their preferred date format

### BUG: 000004 (GitHub Issue:3)

The total Entries label is hidden behind the Help & Feedback, About Product, and How to use app buttons. These three buttons should be moved slight down!

![screenshot 'Total_Entries.png'](ExportYourGoogleCalendar_screenshots/Total_Entries.png)

#### ANSWER

Change UI so compressing the app window stops at the point screen elements (including collapsed/hidden elements) might become obscured.

### BUG: 000005 (GitHub Issue:4)

When a user clicks on the change language option and selects any language. It logout users and then users have to signing once again to see the changes.

#### Answer

When language button is clicked pop-up warning to user that changing the language will lose the user's unsaved work.


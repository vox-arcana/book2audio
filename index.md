## Make Audiobook From Ebook

This is a guide on how to turn basically any ebook into an audiobook that doesn't sound like a robot. In this guide, I use amazon as my ebook source, a windows 10 PC, and an android phone. 

1. Install [Calibre](https://calibre-ebook.com/download)

2. Get **deDRM**, unzip it somewhere, and inside calibre go to **preferences > add plugin** and add **deDRM** 
-- [DeDRM](https://github.com/apprenticeharper/DeDRM_tools)
-- [DeDRM - Releases](https://github.com/apprenticeharper/DeDRM_tools/releases)

3. The next step depends on how you are exporting from amazon, which you can do from this link:
-- [Export books from Amazon](https://www.amazon.com/mn/dcw/myx.html/ref=kinw_myk_redirect#/home/content/booksAll/dateDsc/)
-- Click the **...** to get this menu.
-- Then select **Download & transfer via USB**
-- ![image](https://raw.githubusercontent.com/vox-arcana/book2audio/gh-pages/2020-05-03_18_21_41-Amazon.com__Manage_Your_Content_and_Devices.png)

4. Then you get a dropdown where you'll only be able to export to devices or kindle apps that are considered active. 
-- **This matters because the DRM encoding is based on the intended device.**
-- ![image](https://raw.githubusercontent.com/vox-arcana/book2audio/gh-pages/2020-05-03_18_23_02-Amazon.com__Manage_Your_Content_and_Devices.png)
  
5. Depending on what you output it for, **deDRM** might need a piece of information to decrypt it.
-- ![image](https://raw.githubusercontent.com/vox-arcana/book2audio/gh-pages/2020-05-03_18_25_34-calibre_-_Preferences_-_Plugins.png)
  
6. I exported for a Kindle Oasis. So, I put in the serial number from my device as an **EINK Kindle Serial number**

7. That's basically it for exporting & removing any DRM. You just click **Add books** in calibre and pick the file you downloaded.
-- If you set it up right, it will decrypt it automatically on import and let you convert & export it to any format you want, **DRM-free.**
-- If you did something wrong, Calibre will fail when you try to convert. 
-- In the event you fucked up, there are tons of little faqs and links they give you to try and figure out what you did wrong here:
-- [DeDRM - FAQs](https://github.com/apprenticeharper/DeDRM_tools/blob/master/FAQs.md)
-- Example: You might need to put in a key for Kindle for MAC/PC if you exported for that platform from Amazon.
-- **Note: it decrypts only on import, so you need to go to preferences > adding books > adding actions and enable auto-merge and set it to overwrite existing.**
-- **This way if you fucked up, you can fix ur keys or w/e, try importing again, and it will just overwrite the initial import with the hopefully now DRM-free one.**

8. Get an ebook reader that does TTS!
-- On your android device, I found this app works well because it will open any epub & supports advanced Text-to-Speech options:
-- [@Voice Reader](https://play.google.com/store/apps/details?id=com.hyperionics.avar)
-- **Note: I paid the $10 for the pro version.**

9. Setup Google Cloud Wavenet service. 
-- **Note: This is technically not free, but the $300 trial is at least 1 million words.**
-- If you don't have a Google Cloud account, go here to make one: [Google Cloud](https://cloud.google.com/)
-- **Add billing info to get the $300 trial**

10. Create a project & get a wavenet API key
-- Go to the API & Services dashboard: [Google Cloud - APIs & Services](https://console.cloud.google.com/apis/dashboard)
-- Create a new project. 
-- Inside the project, go to the Cloud Text-to-Speech API [Google Cloud - Cloud TTS/wavenet](https://console.cloud.google.com/apis/api/texttospeech.googleapis.com)
-- On the wavenet page, go to the Credentials section.
-- Hit the **+ Create Credentials** button near the top of the page and select a **Service Account.**
-- Create the credentials. 
-- Go to the Service Accounts page to get the email & Key ID [Google Cloud - Service Accounts](https://console.cloud.google.com/iam-admin/serviceaccounts)
-- **Send the email & key to yourself on your phone.**

10. Open up the @Voice reader on your android device. 
-- Hit the settings cog in the top right.
-- Scroll to the bottom and hit the Google API Key option.
-- Put your wavenet API key in here

11. Go to Settings & Change voice or language option.
-- Pick any of the Google voice options.

### Congrats, you can now make your own audiobooks from any ebook.

# auto-gmail-responder
Auto respond to gmail/emails with openai/chatgpt and python

This tool:

1. It runs with a click of a button. No coding is required to set it up. 
2. It will listen on your Gmail account and auto reply to emails (live). 
3. It will auto reply based on ChatGPT prompts that you set into a text file.
4. It will only reply to specific emails that you have set rules or filters for.
5. It will move auto replied emails to a separate inbox so you can keep track of the results. 
6. It DOES NOT collect any of your data. The tool runs locally on your PC. Once you stop the program, it disappears with along with any email/data it has read. 
7. It only works on Windows but if you know basic python you can easily copy over the source code to Mac or Linux. All the source code can be found on <>github

Instructions: No Coding Required

Requirements:

1. Windows PC. The no-code tool will only work on Windows. 
2. Gmail Account: You will need a gmail account/address. It is free to make. 
3. Gmail Account App Password: This is not your usual email password, you will need to setup a specific “App” password to get this to work. Follow this quick video tutorial on how to set it up. Just make sure to select the “Other (Custom Name)” option at the end instead of “Iphone”
4. OpenAI Account & API Secret Key: If you have used ChatGPT then you will already have an OpenAI account. Sign up if not. The next step it easy, head over to https://platform.openai.com/account/api-keys to generate a secret key. Copy it out and keep it safe as this key lets the took access their text models programmatically. If you forget or lose your key, you can delete the old and generate a new one.

Steps to use:

1. Download this folder and extract the zip. 
2. Log into your Gmail account and create a new label/folder called gpt-auto-replied if you don’t do this, the tool will respond to the same email in a never ending loop!
3. Configure your settings and prompts! Here is where you need to be a little be careful. Try to follow the template formats exactly as they are but with your own values
4. Configuring “settings.env”

    * Double click into the file to open it up with notepad.
    * openai_secret_key, gmail_address, gmail_app_password are pretty straight forward. Refer to the requirements section above to retrieve this info
    * check_every_n_seconds refers to how often you want the tool to check your inbox. I’ve set the default to 300 seconds which equates to 5 minutes. The lower the amount of time the more intensive the application will run
    * how_many_days_ago refers to how far back you want the tool to be reading your emails. The default is set to 0, meaning it will only check emails received today. If you set it to 1, it will check 1-day ago, if you set it to 2, it will check 2 days ago and so on.

5. Configuring “prompt_settings.csv”

    * filter_type column: refers to the email rules the script will check. Input the values of either 1, 2 or 3. The are explained below:

    1: Filter by email address only. It will respond to all emails from that specific email address
    2: Filter by subject only. It will respond to all subjects/email titles containing the phrase you described.
    3: Filter by both email and subject. It will respond to emails sent by a specific address while containing that specific subject title.

    * filters column: Enter the email address or subject header in the column. If you have set filter_type to 3, please enter the following with the “;” symbol like this:

            john.doe@example.com; Example Email Subject

    * chatgpt_prompt column: This is where you type out your prompt for each of your filters. An example would be:

    Your name is <insert your name> and you are a customer service representative working for <insert company name> which sells <insert product> . Please respond to the to the following email in a polite and attentive tone. Make sure to keep you response short and succinct without repeating your message or promising anything you can’t deliver as an AI. Please direct them to <insert URL> for more information and promise that I will get back to them as soon as possible. 

6. Run the auto_gmail_responder application and witness the magic!


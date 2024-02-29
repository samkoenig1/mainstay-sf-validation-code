# mainstay-sf-validation-code
Code to scrape and validate two datasources, one from Mainstay and Salesforce to support our product team in auditing, ensuring data is up to date before sending out messages to users. 


**Context**: What does this process solve?

-   The purpose of this process is to run a script to automatically do the data validation process outlined in the slide deck here → [FY24: Mainstay Manual](https://docs.google.com/presentation/d/1ynXz0JAxdOyb4eUpPNcQLI3RuK-BtIZ10Zxc-M9RwvU/edit#slide=id.g28c517bb68a_5_13). This script will check info such as: 

-   College/university type

-   Phone number

-   Direct support staff 

-   Afterwards, it's important to (1) Update any records in Mainstay that are off (2) Add any records from Salesforce in the middle of the year

-   The following documentation will demonstrate how to run a python script to do this validation work on your behalf after downloading the relevant data.

**Setup instructions**: Note - Steps 1-3 only need to be done once. If you already have access, download the following packages, then proceed to Step 4.

-   Step 1 - Ensure that you have access to the [sharepoint folder](https://onegoal.sharepoint.com/sites/NPTDigitalAdvisingChatbot/Shared%20Documents/Forms/AllItems.aspx) where we store the data, and the code. If you don't have access you can submit an IT ticket to [freshdesk here](https://onegoal.freshdesk.com/support/login).

-   Step 2 - Ensure that you have python installed in your local machine. You can install python on the [website here](https://www.python.org/downloads/), similar to any other website application. 

-   Step 3 - Install two packages onto your computer:

        -   Navigate to the application "Command Prompt" on your computer
        
        -   Type in the code "pip install pandas", hit enter
        
        -   Type in the code "pip install xlsxwriter", hit enter.

-   Step 4 - Export the Mainstay Report [here](https://app.mainstay.com/audiences/?apage=1): 

      -   Type in "Hou: class of 2023" to the search bar
      
      -   Hit the three dots on the right and hit export. 

-   ![](https://lh7-us.googleusercontent.com/ESLClExUVgWgdBbxNHF_Vq_WalpvtrDa7Dg_m-aaKDxG2UQ5oO9bKHtccKCaHvw42q-VSPXfFvl-sEUbkk3WMAlNZzsGOhO4WPyHX7X6AF-2XS1wH1el5Ek9szjGaEJEHzUj4u4fX-TdCo3wpb1cZzo)

-   Select All fields on the report and hit "Download Report"

-   Rename your file "ms" and drop your file in the sharepoint folder [here](https://onegoal.sharepoint.com/sites/NPTDigitalAdvisingChatbot/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2FNPTDigitalAdvisingChatbot%2FShared%20Documents%2Fmainstay%5Ffiles&viewid=b18e862e%2D3e82%2D4f50%2D8830%2D391f4b24f0a6). Select "Replace" when the popup comes up. We want to overwrite the older report. 

-   ![](https://lh7-us.googleusercontent.com/DbzwcunxXfxN-DF1ZaOEOM7F5tXUkyV-AtgbmI4H5XZJoHBThOTO4Xwl8FeFZRd8Zfy9EjUC3Excvork_6GO7tblcvfwJ74W09atn4ui6i3KlJQ4P6D9fvxekUTF7qX4xJXCuv-tQknhbGtBTAD8qMQ) 

-   Step 5 - Export the Salesforce report [here](https://onegoalgraduation.lightning.force.com/lightning/r/Report/00OVL0000007SM92AM/view?queryScope=userFolders)

-   Click the down arrow in the upper right corner and click "export"

-   ![](https://lh7-us.googleusercontent.com/v8FsuZi62awuS7U3Iaji7EPKqbpG_08ktXTXUMwDxUw3BOjKXIpoyFaixsQreyMWiYljq3ANTh0r_BgzMFGHpZnAnfNEs12-Rc8YuEk_VjorpSSVSkP-lxk6YlGBZ1kqA9fOiJqGlCKfvQOzQqPhnjE)

-   Select "Details Only" and then select "csv" as the export type![](https://lh7-us.googleusercontent.com/BHkvZM70OlwyncZ7Gei07nQWG_Yhdi-A6oRUa0Dm330pWpOR3iBIZfNyYJJK7HuPYAOLm9Rzf_a7U1z1BQIslxttZw08koWW7KxDtlbxlVYvgoXF0CS-Arsger_cxStjuoDB6k0AQJkXDvKMAyRCk4I)

-   Rename your file "sf" and drop your file in the sharepoint folder [here](https://onegoal.sharepoint.com/sites/NPTDigitalAdvisingChatbot/Shared%20Documents/Forms/AllItems.aspx?id=%2Fsites%2FNPTDigitalAdvisingChatbot%2FShared%20Documents%2Fmainstay%5Ffiles&viewid=b18e862e%2D3e82%2D4f50%2D8830%2D391f4b24f0a6). Select "Replace" when the popup comes up. We want to overwrite the older report.

Step 6 - Run Code:

-   Open up command prompt on your local machine:  type in: "cd OneGoal/NPT Digital Advising Chatbot - Documents/data_validation_code" → hit enter

-   Type in "python validate_data.py" → hit enter

-   Type in your username when prompted as the one in your file directory here

-   ![](https://lh7-us.googleusercontent.com/sOUWl_C0BLhfCq6Gh_vD2K-uNI9B_y3-WKIeQjKlHdyWUfvQ7-AgZlcHGO1bGjfvABcr8e1dfchlFxLLsMHiyZcMB89b-8Prr7VGoniNsiqfN-Kd2OIYcpA97emtTmrOxZZALa-DCWvKCIvJIncQASk)

-   The validated file will populate in the folder [here](https://onegoal.sharepoint.com/sites/NPTDigitalAdvisingChatbot/Shared%20Documents/Forms/AllItems.aspx?newTargetListUrl=%2Fsites%2FNPTDigitalAdvisingChatbot%2FShared%20Documents&viewpath=%2Fsites%2FNPTDigitalAdvisingChatbot%2FShared%20Documents%2FForms%2FAllItems%2Easpx&id=%2Fsites%2FNPTDigitalAdvisingChatbot%2FShared%20Documents%2Fvalidate%5Fdata&viewid=b18e862e%2D3e82%2D4f50%2D8830%2D391f4b24f0a6)

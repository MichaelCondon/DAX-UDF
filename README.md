# DAX-UDF
A small collection of my personal DAX User Defined Functions, free for all to use.

###Testing Stage SVG

<img width="271" height="248" alt="image" src="https://github.com/user-attachments/assets/33b84990-d1a9-4e08-99b0-ce8ef27b0a2a" />

After spending endless days thinking about CD/CD in Power BI, I realised there was no easy and automated way to indicate to users what deployment stage a report is in when they are viewing it. I've drawn up some simple "chip" style SVG images using figma, with icons courtesy of the the incredible Open Source Fluent Icons created by microsoft, , through the [Fluenticons](https://fluenticons.co/) website. This solution comes in two parts. First, a DAX UDF that takes a string argument "stage". The accepted arguments are:
* "DEV" - Report is in active development
* "UAT" - User Acceptance Testing - Report is in testing
* 'PROD" - Production, this report is running on live data
This function returns an SVG Image that can be used in a Card, Table, or Custom SVG visual. To keep things native, I recomend using the "Card (New)" visual. Simply place any field into the new card and disable values, titles, borders, and background. Under "Images" select the measure that you are calling the DAX UDF in as the image itself and resize accordingly.

To maximise use of this UDF, you can feed the UDF an argument from a Power Query Parameter. The reason this is useful is that Power BI parameters can be automatically changed using deployment rules in either DevOps or Power BI deployment pipelines. If your measure references a parameter directly, this can automate the chip swapping from DEV, to UAT, To PROD without any manual intervention required.
<img width="754" height="821" alt="image" src="https://github.com/user-attachments/assets/1298beb9-d16b-4ebd-b321-7d2a46b2f945" />
<img width="846" height="45" alt="image" src="https://github.com/user-attachments/assets/5c7f1cf5-9294-4c61-ab15-ca7d095bc781" />

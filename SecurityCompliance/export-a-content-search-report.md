---
title: "Export a Content Search report"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'ms.o365.cc.CustomizeExportReport'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: "Instead of exporting the actual results of a Content Search in the Office 365 Security &amp; Compliance Center, you can just export a search results report. The report contains a summary of the search results and a document with detailed information about each item that would be exported."
---

# Export a Content Search report

Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.
  
When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).

## Before you begin

- To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).
    
- When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created. 
    
- The computer you use to export the search results has to meet the following system requirements:
    
  - 32- or 64-bit versions of Windows 7 and later versions
    
  - Microsoft .NET Framework 4.7
    
  - A supported browser:
    
    - Microsoft Edge
    
      or
    
    - Microsoft Internet Explorer 10 and later versions
    
    **Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported. 

- If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail. To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.

## Generate and download a Content Search report

The steps to generate and download a Content Search report are very similar to actually exporting search results.
  
## Step 1: Generate the report for export

The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.
  
1. Go to [https://protection.office.com](https://protection.office.com).
    
2. Sign in to Office 365 using your work or school account.
    
3. In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.
    
4. On the **Content search** page, select a search. 
    
5. In the details pane, under **Export report to a computer**, click **Generate report**.
    
    > [!NOTE]
    > If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated. 
  
6. On the **Export a report** page, under **Include these items from the search**, choose one of the following options:
    
    - Export only indexed items
    
    - Export indexed and unindexed items
    
    - Export only unindexed items
    
    For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).
    
7. Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.
    
8. Click **Generate report**.
    
    The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane. 
    
> [!NOTE]
> You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**. 
  
## Step 2: Download the report

The next step is to download the report from the Azure storage area to your local computer.
  
1. In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.
    
    The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer. 
    
    - The number of items that will be downloaded.
    
    - The estimated total size of the items that will be downloaded.
    
    - Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.
    
    - Whether or not versions of SharePoint documents will be downloaded.
    
    - The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.
    
2. Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.
    
    > [!IMPORTANT]
    > Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information. 
  
3. Click **Download report**.
    
4. If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.
    
5. In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.
    
6. Click **Browse** to specify the location where you want to download the report. 
    
7. Click **Start** to download the search results to your computer. 
    
    The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded. 
    
> [!NOTE]
> You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane. 
  
## What's included in the report

When you generate and export a report about the results of a Content Search, the following documents are downloaded:
  
- **Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported. 
    
    > [!NOTE]
    > If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items. 
  
- **Manifest** - A manifest file (in XML format) that contains information about each item included in the search results. 
    
- **Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including: 
    
  - The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).
    
  - The date the message was sent or received.
    
  - The Subject line from the message.
    
  - The sender and recipients of the message.
    
    For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:
    
  - The URL for the document.
    
  - The URL for the site collection where the document is located.
    
  - The date that the document was last modified.
    
  - The name of the document (which is located in the Subject column in the result log).
    
    > [!NOTE]
    > The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report. 
  
- **Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.

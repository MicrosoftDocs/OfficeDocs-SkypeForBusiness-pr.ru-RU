---
title: Экспорт архивных данных в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Сводка: Узнайте, как Экспорт архивированных данных для Скайп для Business Server 2015.'
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a><span data-ttu-id="fedd0-103">Экспорт архивных данных в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="fedd0-103">Export archived data in Skype for Business Server 2015</span></span>

<span data-ttu-id="fedd0-104">**Сводка:** Узнайте, как Экспорт архивированных данных для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="fedd0-104">**Summary:** Learn how to export archived data for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fedd0-105">Данные, заархивированные в архивных базах данных, не доступны для поиска или чтения, но можно использовать командлет **Export-CsArchivingData** для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="fedd0-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="fedd0-106">Если включить интеграцию с Microsoft Exchange данных архивации в хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="fedd0-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="fedd0-107">Данных архивации в Exchange для поиска и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fedd0-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="fedd0-108">Для получения дополнительных сведений о доступе к данным, архивируются в Exchange обратитесь к документации Exchange.</span><span class="sxs-lookup"><span data-stu-id="fedd0-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fedd0-109">Экспорт архивированных данных с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fedd0-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fedd0-110">Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="fedd0-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="fedd0-p102">Следующая команда экспортирует все данные atl-sql-001.contoso.com, архивированные с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="fedd0-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="fedd0-113">Следующая команда экспортирует архивированных данных для одного пользователя: kenmyer@contoso.com. Для этого, включив параметр UserUri, а затем адрес SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="fedd0-113">The following command exports archiving data for a single user: kenmyer@contoso.com. This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="fedd0-114">Например:</span><span class="sxs-lookup"><span data-stu-id="fedd0-114">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="fedd0-115">Для получения дополнительных сведений см раздел справки для командлета [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="fedd0-115">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  


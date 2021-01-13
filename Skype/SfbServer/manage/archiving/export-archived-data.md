---
title: Экспорт архивных данных в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: Сводка. Узнайте, как экспортировать архивные данные для Skype для бизнеса Server.
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817569"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="e2cf5-103">Экспорт архивных данных в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e2cf5-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="e2cf5-104">**Сводка:** Узнайте, как экспортировать архивные данные для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="e2cf5-105">Данные, архивируемые в базах данных архива, недоступны для поиска или в формате, который можно читать, но можно использовать для извлечения записей из базы данных и сохранения записей в виде **EML-файла** Outlook.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="e2cf5-106">Если включить интеграцию с Microsoft Exchange, данные будут архивироваться в хранилищах Exchange.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="e2cf5-107">Данные, архивируемые в Exchange, можно искать и обнаруживать.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="e2cf5-108">Подробные сведения о доступе к данным, архивным в Exchange, см. в документации Exchange.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2cf5-109">Экспорт данных архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2cf5-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e2cf5-110">Вы можете экспортировать архивные данные с помощью Export-CSArchivingData управления.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="e2cf5-111">Следующая команда экспортирует все данные архива, написанные в базу данных atl-sql-001.contoso.com с 1 июня 2012 г.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="e2cf5-112">Файл результатов будет сохранен в папке C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="e2cf5-113">Следующая команда экспортирует данные архива для одного пользователя: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="e2cf5-114">Это делается путем включив параметр UserUri, за которым следует SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2cf5-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="e2cf5-115">Например:</span><span class="sxs-lookup"><span data-stu-id="e2cf5-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="e2cf5-116">Дополнительные сведения см. в разделе справки по [cmdlet Export-CsArchivingData.](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e2cf5-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  


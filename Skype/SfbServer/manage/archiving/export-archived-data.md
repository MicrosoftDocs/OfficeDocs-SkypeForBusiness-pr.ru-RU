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
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095383"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="78119-103">Экспорт архивных данных в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="78119-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="78119-104">**Сводка:** Узнайте, как экспортировать архивные данные для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="78119-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="78119-105">Данные, архивируемые в базах данных архива, не являются для поиска или в читаемом формате, но вы можете использовать кодлет **Export-CsArchivingData** для извлечения записей из базы данных и сохранения их в виде файла электронной почты Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="78119-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="78119-106">Если включить интеграцию Microsoft Exchange, данные будут архивироваться в магазинах Exchange.</span><span class="sxs-lookup"><span data-stu-id="78119-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="78119-107">Данные, архивируемые в Exchange, можно искать и обнаруживать.</span><span class="sxs-lookup"><span data-stu-id="78119-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="78119-108">Сведения о доступе к данным, архивуемой в Exchange, см. в документации Exchange.</span><span class="sxs-lookup"><span data-stu-id="78119-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="78119-109">Экспорт данных архива с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="78119-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="78119-110">Вы можете экспортировать архивные данные с помощью Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="78119-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="78119-111">Следующая команда экспортирует все архивные данные, написанные в базу данных архива, atl-sql-001.contoso.com с 1 июня 2012 г.</span><span class="sxs-lookup"><span data-stu-id="78119-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="78119-112">Файл результатов будет сохранен в папке C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="78119-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="78119-113">Следующая команда экспортирует данные архива для одного пользователя: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="78119-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="78119-114">Это делается путем включив параметр UserUri, за которым следует SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="78119-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="78119-115">Например:</span><span class="sxs-lookup"><span data-stu-id="78119-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="78119-116">Дополнительные сведения см. в разделе Справка для [cmdlet Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="78119-116">For more information, see the help topic for the [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>

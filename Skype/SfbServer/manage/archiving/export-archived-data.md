---
title: Экспорт архивных данных в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Общие сведения: экспорт архивных данных для Skype для бизнеса Server.'
ms.openlocfilehash: 12ba59ff11a988fd95eb2207cd826a4399db2779
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818911"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="769c2-103">Экспорт архивных данных в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="769c2-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="769c2-104">**Сводка:** Сведения о том, как экспортировать архивные данные для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="769c2-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="769c2-105">Данные, заархивированные в архивных базах данных, не доступны для поиска или чтения, но можно использовать командлет **Export-CsArchivingData** для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="769c2-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="769c2-106">При включении интеграции с Microsoft Exchange данные архивируются в хранилищах Exchange.</span><span class="sxs-lookup"><span data-stu-id="769c2-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="769c2-107">Данные, архивированные в Exchange, можно искать и находить.</span><span class="sxs-lookup"><span data-stu-id="769c2-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="769c2-108">Подробные сведения о доступе к данным, архивированным в Exchange, можно найти в документации по Exchange.</span><span class="sxs-lookup"><span data-stu-id="769c2-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="769c2-109">Экспорт данных архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="769c2-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="769c2-110">Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="769c2-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="769c2-p102">Следующая команда экспортирует все данные atl-sql-001.contoso.com, архивированные с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="769c2-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="769c2-113">Следующая команда экспортирует архивированные данные для одного пользователя: kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="769c2-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="769c2-114">Это можно сделать, добавив параметр Усерури, а затем — адрес SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="769c2-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="769c2-115">Например:</span><span class="sxs-lookup"><span data-stu-id="769c2-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="769c2-116">Дополнительные сведения можно найти в разделе справки по командлету [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="769c2-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  


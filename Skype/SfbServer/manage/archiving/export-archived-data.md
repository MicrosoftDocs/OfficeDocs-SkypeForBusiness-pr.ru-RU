---
title: Экспорт архивированных данных в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Сводка: Узнайте, как Экспорт архивированных данных для Скайп для Business Server.'
ms.openlocfilehash: 9b03ea23fd907a386b15005f18c3c0becdb79589
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975769"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Экспорт архивированных данных в Скайп для Business Server

**Сводка:** Узнайте, как Экспорт архивированных данных для Скайп для Business Server.
  
Данные, заархивированные в архивных базах данных, не доступны для поиска или чтения, но можно использовать командлет **Export-CsArchivingData** для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail).
  
Если включить интеграцию с Microsoft Exchange данных архивации в хранилище Exchange. Данных архивации в Exchange для поиска и обнаружения. Для получения дополнительных сведений о доступе к данным, архивируются в Exchange обратитесь к документации Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Экспорт архивированных данных с помощью командлетов Windows PowerShell

Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData. 
  
Следующая команда экспортирует все данные atl-sql-001.contoso.com, архивированные с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Следующая команда экспортирует архивированные данные для одного пользователя: kenmyer@contoso.com. Для этого, включив параметр UserUri, а затем адрес SIP пользователя. Например: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Для получения дополнительных сведений см раздел справки для командлета [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  


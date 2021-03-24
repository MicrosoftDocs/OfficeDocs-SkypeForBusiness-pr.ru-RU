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
# <a name="export-archived-data-in-skype-for-business-server"></a>Экспорт архивных данных в Skype для бизнеса Server

**Сводка:** Узнайте, как экспортировать архивные данные для Skype для бизнеса Server.
  
Данные, архивируемые в базах данных архива, не являются для поиска или в читаемом формате, но вы можете использовать кодлет **Export-CsArchivingData** для извлечения записей из базы данных и сохранения их в виде файла электронной почты Outlook (EML).
  
Если включить интеграцию Microsoft Exchange, данные будут архивироваться в магазинах Exchange. Данные, архивируемые в Exchange, можно искать и обнаруживать. Сведения о доступе к данным, архивуемой в Exchange, см. в документации Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Экспорт данных архива с помощью Windows PowerShell cmdlets

Вы можете экспортировать архивные данные с помощью Export-CSArchivingData. 
  
Следующая команда экспортирует все архивные данные, написанные в базу данных архива, atl-sql-001.contoso.com с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Следующая команда экспортирует данные архива для одного пользователя: kenmyer@contoso.com. Это делается путем включив параметр UserUri, за которым следует SIP-адрес пользователя. Например: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Дополнительные сведения см. в разделе Справка для [cmdlet Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)

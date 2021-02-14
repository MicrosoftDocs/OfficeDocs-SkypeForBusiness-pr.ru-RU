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
# <a name="export-archived-data-in-skype-for-business-server"></a>Экспорт архивных данных в Skype для бизнеса Server

**Сводка:** Узнайте, как экспортировать архивные данные для Skype для бизнеса Server.
  
Данные, архивируемые в базах данных архива, недоступны для поиска или в формате, который можно читать, но можно использовать для извлечения записей из базы данных и сохранения записей в виде **EML-файла** Outlook.
  
Если включить интеграцию с Microsoft Exchange, данные будут архивироваться в хранилищах Exchange. Данные, архивируемые в Exchange, можно искать и обнаруживать. Подробные сведения о доступе к данным, архивным в Exchange, см. в документации Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Экспорт данных архива с помощью Windows PowerShell

Вы можете экспортировать архивные данные с помощью Export-CSArchivingData управления. 
  
Следующая команда экспортирует все данные архива, которые были записаны в базу данных atl-sql-001.contoso.com с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Следующая команда экспортирует данные архива для одного пользователя: kenmyer@contoso.com. Это делается путем включив параметр UserUri, за которым следует SIP-адрес пользователя. Пример: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Дополнительные сведения см. в разделе справки по [cmdlet Export-CsArchivingData.](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)
  


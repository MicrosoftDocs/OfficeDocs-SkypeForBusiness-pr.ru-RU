---
title: Экспорт архивных данных в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Общие сведения: экспорт архивных данных для Skype для бизнеса Server.'
ms.openlocfilehash: 0d48441290eda49ad6b7fecd63d15d74b25148fe
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991574"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Экспорт архивных данных в Skype для бизнеса Server

**Сводка:** Сведения о том, как экспортировать архивные данные для Skype для бизнеса Server.
  
Данные, заархивированные в архивных базах данных, не доступны для поиска или чтения, но можно использовать командлет **Export-CsArchivingData** для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail).
  
При включении интеграции с Microsoft Exchange данные архивируются в хранилищах Exchange. Данные, архивированные в Exchange, можно искать и находить. Подробные сведения о доступе к данным, архивированным в Exchange, можно найти в документации по Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Экспорт данных архивации с помощью командлетов Windows PowerShell

Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData. 
  
Следующая команда экспортирует все данные atl-sql-001.contoso.com, архивированные с 1 июня 2012 г. Файл результатов будет сохранен в папке C:\ArchivingExports.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Следующая команда экспортирует архивированные данные для одного пользователя: kenmyer@contoso.com. Это можно сделать, добавив параметр Усерури, а затем — адрес SIP пользователя. Например: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Дополнительные сведения можно найти в разделе справки по командлету [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  


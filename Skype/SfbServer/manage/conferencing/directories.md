---
title: Создание каталогов конференций в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Сводка: сведения о создании каталогов конференций в Skype для бизнеса Server.'
ms.openlocfilehash: 0ed141b743d436ca2082b8a4f5010011a0256479
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991854"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Создание каталогов конференций в Skype для бизнеса Server
 
**Сводка:** Сведения о создании каталогов конференций в Skype для бизнеса Server.
  
В каталогах конференций поддерживается соответствие между буквенно-цифровым ИДЕНТИФИКАТОРом собрания, который используется участником для присоединения к Конференции при использовании Skype для бизнеса, а также идентификационный код, который используется участниками конференц-связи с телефонным подключением для присоединения к Конференции. 
  
## <a name="create-a-conference-directory"></a>Создание каталога конференции

Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. 
  
В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. Это правило позволит сохранить короткие идентификаторы конференций. Однако когда количество каталогов конференций (по пулам) превышает 9, длина идентификатора конференции будет увеличиваться для поддержки дополнительных конференций.
  
Формат идентификатора конференции: 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Для создания каталога конференций воспользуйтесь командлетом **New-CsConferenceDirectory**. Например, следующая команда создает каталог конференции с идентификатором 42, размещенный в пуле atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Дополнительные сведения можно найти в разделе [New-ксконференцедиректори](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  


---
title: Создание каталогов конференций в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Сводка: Узнайте, как для создания каталогов конференций в Скайп для Business Server.'
ms.openlocfilehash: 9e79ca7e1b2f896746db998cc53983c04c6724ef
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883516"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Создание каталогов конференций в Скайп для Business Server
 
**Сводка:** Узнайте, как для создания каталогов конференций в Скайп для Business Server.
  
Каталоги конференций Ведение сопоставления между собрания буквенно-цифровой идентификатор, который использует участника присоединиться к конференции, при использовании Скайп для бизнеса и конференции цифровой идентификатор, который использует телефонных конференций участника присоединиться к конференции. 
  
## <a name="create-a-conference-directory"></a>Создание каталога конференции

Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. 
  
В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. Это правило позволит сохранить короткие идентификаторы конференций. Однако когда количество каталогов конференций (по пулам) превышает 9, длина идентификатора конференции будет увеличиваться для поддержки дополнительных конференций.
  
Формат идентификатора конференции: 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Для создания каталога конференций воспользуйтесь командлетом **New-CsConferenceDirectory**. Например, следующая команда создает каталог конференции с идентификатором 42, размещенный в пуле atl-cs-001.litwareinc.com:
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Дополнительные сведения содержатся в разделе [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  


---
title: Создание каталогов конференций в Skype для бизнеса Server
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
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: Сводка. Узнайте, как создавать каталоги конференций в Skype для бизнеса Server.
ms.openlocfilehash: 6a7b8d110f06b089f166fc6ff2eb35ae35632370
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828139"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Создание каталогов конференций в Skype для бизнеса Server
 
**Сводка:** Узнайте, как создавать каталоги конференций в Skype для бизнеса Server.
  
Каталоги конференций поддерживают сопоставление между букво-цифровой ИД собрания, который участник использует для join a conference when using Skype for Business, и числовом ИД конференции, который участник конференции с телефонной связью использует, чтобы присоединиться к конференции. 
  
## <a name="create-a-conference-directory"></a>Создание каталога конференции

Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. 
  
В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. С помощью этого руководства, как правило, можно сохранить небольшие ИД конференции. Однако когда количество каталогов конференций (в пулах) превысит 9, длина ИД конференции будет увеличиваться для поддержки дополнительных конференций.
  
Формат ИД конференции: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Чтобы создать каталог конференции, используйте **cmdlet New-CsConferenceDirectory.** Например, следующая команда создает каталог конференции с идентификатором 42, который будет atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Дополнительные сведения см. в [new-CsConferenceDirectory.](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)
  


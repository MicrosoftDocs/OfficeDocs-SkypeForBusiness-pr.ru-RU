---
title: Создание каталогов конференций в Skype для бизнеса Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: Сводка. Сведения о создании каталогов конференций в Skype для бизнеса Server.
---

# <a name="create-conference-directories-in-skype-for-business-server"></a>Создание каталогов конференций в Skype для бизнеса Server
 
**Сводка:** Узнайте, как создать каталоги конференций в Skype для бизнеса Server.
  
Каталоги конференций поддерживают сопоставление между ИД альфа-числимого собрания, который участник использует для присоединиться к конференции при использовании Skype для бизнеса, и ИД конференции, используемой только для числов, который участник конференц-связи с диалогом использует, чтобы присоединиться к конференции. 
  
## <a name="create-a-conference-directory"></a>Создание каталога конференций

Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. 
  
В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. С помощью этого руководства, как правило, можно хранить небольшие ID конференции. Однако, как только количество каталогов конференций (в пулах) превысит 9, длина ID конференции будет увеличиваться для поддержки дополнительных конференций.
  
Формат ID конференции: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Чтобы создать каталог конференций, используйте **кодлет New-CsConferenceDirectory** . Например, следующая команда создает каталог конференций с идентификатором 42, который будет atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Дополнительные сведения см. [в new-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).

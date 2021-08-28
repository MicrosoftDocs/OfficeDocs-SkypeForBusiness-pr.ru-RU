---
title: Восстановление баз данных сохраняемой системы чата в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: Сводка. Сведения о том, как восстановить базы данных сохраняемой системы чат-сервера в Skype для бизнеса Server 2015 г.
ms.openlocfilehash: aba6ead1d666f9f257e9cd7bfa1e7d2343049b9d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622251"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Восстановление баз данных сохраняемой системы чата в Skype для бизнеса Server 2015 г.
 
**Сводка:** Узнайте, как восстановить базы данных сохраняемой системы чат-сервера в Skype для бизнеса Server 2015 г.
  
Для сохраняемого сервера SQL Server базы данных для хранения данных комнат чата, таких как история и содержимое, конфигурация, подготовка пользователей и другие соответствующие метаданные. Кроме того, если в вашей организации есть правила, которые требуют архивировать действия сохраняемой беседы и включена необязательная служба соответствия требованиям, SQL Server базы данных используется для хранения данных соответствия требованиям, включая содержимое чата и события, такие как присоединение и выход из комнат. Содержимое комнаты чата хранится в базе данных persistent Chat (mgc). Данные соответствия требованиям хранятся в базе данных соответствия требованиям (mgccomp). Это критически важные для бизнеса данные, которые необходимо регулярно обновлять. 
  
> [!NOTE]
> Постоянный чат доступен в Skype для бизнеса Server 2015 г., но больше не поддерживается Skype для бизнеса Server 2019 г. Такая же функциональность доступна в Teams. Дополнительные сведения см. в ссылке Начало работы [с обновлением Microsoft Teams обновления.](/microsoftteams/upgrade-start-here) Если вам нужно использовать постоянный чат, вы можете либо перенести пользователей, требующих Teams, либо продолжить использование Skype для бизнеса Server 2015 г. 

## <a name="back-up-the-databases"></a>Back up the databases

Существует два способа хранения данных сохраняемого чата. 
  
- SQL Server Резервное копирование
    
- The **Export-CsPersistentChatData cmdlet,** which exports Persistent Chat data as a file
    
Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше дискового пространства , возможно, в 20 раз больше, чем в созданном в результате использования **cmdlet Export-CsPersistentChatData,** но SQL Server резервное копирование, скорее всего, будет процедурой, с которой вы знакомы.
  
Если вы хотите использовать SQL Server процедуры резервного копирования, дополнительные сведения см. в SQL документации. 
  
Если вы хотите использовать командлет **Export-CsPersistentChatData,** можно указать команду следующим образом:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

или
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Например, следующая команда экспортирует данные сохраняемой беседы из базы данных persistent Chat, расположенной на сервере atl-sql-001.contoso.com; экспортируемая информация будет храниться в файле C:\Logs\PersistentChatData.zip. Так как параметр Level не указан, команда будет полностью экспортировать сведения о сохраняемом чате:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Восстановление баз данных

Восстановление данных сохраняемого чата зависит от метода, используемого для их восстановления. Если вы SQL Server процедуры резервного копирования, необходимо использовать SQL Server процедуры восстановления. Если для хранения данных сохраняемого чата используется комлет **Export-CsPersistentChatData,** для восстановления данных необходимо использовать комлет **Import-CsPersistentChatData:**
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

или
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```

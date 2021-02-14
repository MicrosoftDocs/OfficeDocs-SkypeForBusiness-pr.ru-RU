---
title: Back up and restore Persistent Chat databases in Skype for Business Server 2015
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
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: Сводка. Узнайте, как с помощью Skype для бизнеса Server 2015 восстанавливать базы данных сервера сохраняемой беседы.
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826379"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Back up and restore Persistent Chat databases in Skype for Business Server 2015
 
**Сводка:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.
  
Серверу сохраняемого чата требуется SQL Server базы данных для хранения данных комнат чата, таких как история и содержимое, конфигурация, подготовка пользователей и другие соответствующие метаданные. Кроме того, если в организации имеются нормативы, которые требуют архивировать действия сохраняемой беседы и включена необязательная служба соответствия, программное обеспечение базы данных SQL Server используется для хранения данных соответствия требованиям, включая содержимое чата и события, такие как присоединение и выход из комнат. Содержимое комнаты чата хранится в базе данных сохраняемой беседы (mgc). Данные соответствия требованиям хранятся в базе данных соответствия (mgccomp). Это критически важные для бизнеса данные, которые следует регулярно обновлять. 
  
> [!NOTE]
> Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams. Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015. 

## <a name="back-up-the-databases"></a>Back up the databases

Существует два способа сохраняемого чата. 
  
- SQL Server резервного копирования
    
- The **Export-CsPersistentChatData cmdlet,** which exports Persistent Chat data as a file
    
Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше места на диске (возможно, в 20 раз больше), чем для создания с помощью cmdlet **Export-CsPersistentChatData,** но резервное копирование SQL Server, скорее всего, является процедурой, с которой вы знакомы.
  
Если вы хотите использовать SQL Server резервного копирования, см. SQL документации по резервному копированию. 
  
Чтобы использовать командлет **Export-CsPersistentChatData,** можно указать команду следующим образом:
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

или
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Например, следующая команда экспортирует данные Persistent Chat из базы данных Persistent Chat, расположенной на сервере atl-sql-001.contoso.com; экспортные данные будут сохранены в файле C:\Logs\PersistentChatData.zip. Так как параметр Level не указан, команда будет полностью экспортировать сведения о сохраняемом чате:
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Восстановление баз данных

Способ восстановления данных сохраняемого чата зависит от метода, который использовался для их восстановления. Если вы использовали SQL Server резервного копирования, необходимо использовать SQL Server восстановления. Если для восстановления данных сохраняемого чата использовался cmdlet **Export-CsPersistentChatData,** то для восстановления данных необходимо использовать его с помощью **import-CsPersistentChatData:**
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

или
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```

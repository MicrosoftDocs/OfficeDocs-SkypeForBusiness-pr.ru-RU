---
title: Разрешение пользователям группового ответа на вызовы и назначение группового номера в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Предоставление пользователям для отправки вызовов группы в Скайп Business Server корпоративной голосовой связи и назначьте номер группы.
ms.openlocfilehash: aaacf080f9e7f7ae7f9bad3f8b13201972d7a72f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a>Разрешение пользователям группового ответа на вызовы и назначение группового номера в Skype для бизнеса 2015
 
Предоставление пользователям для отправки вызовов группы в Скайп Business Server корпоративной голосовой связи и назначьте номер группы.
  
После добавления номеров раскладки групповой звонок в таблице орбит парковки вызовов воспользоваться средством SEFAUtil нумерации группы пользователей и включить раскладки вызывать группу для них.
  
> [!NOTE]
> В гибридном развертывании не Назначение группы вызова раскладки группы пользователей, которые размещаются в Интернете. Пользователи, которые размещаются в Интернете не может участвовать в группы вызова раскладки. То есть другим пользователям не удается ответить на их звонки, и они не могут отвечать на звонки другим пользователям. 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Чтобы назначить номер группы и включения раскладки вызывать группу для пользователя

1. Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.
    
2. В командной строке выполните следующую команду:
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Например, чтобы назначить пользователю групповой номер 199, введите:
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a>См. также

#### 

[Отключить группы раскладки для пользователей](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


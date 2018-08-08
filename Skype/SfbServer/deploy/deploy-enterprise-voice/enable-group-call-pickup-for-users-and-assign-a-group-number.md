---
title: Включение раскладки вызова группа для пользователей и назначение номер группы в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Предоставление пользователям для отправки вызовов группы в Скайп Business Server корпоративной голосовой связи и назначьте номер группы.
ms.openlocfilehash: 5a4173a16a40557742a7cdbd47edb917f89b4737
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006522"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Включение раскладки вызова группа для пользователей и назначение номер группы в Скайп для бизнеса 
 
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

[Отключить группы раскладки для пользователей](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)


---
title: Включить или отключить в Skype для бизнеса Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: Сводка. Узнайте, как использовать панель управления или панель управления, чтобы включить или отключить диалоговое телефонное Skype для бизнеса Server.
ms.openlocfilehash: 335252904ea015046e9caf5689fe31e4b0a9b8c3569b6c7d233fb8c4e74857ec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297295"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Включить или отключить в Skype для бизнеса Server
 
**Сводка:** Узнайте, как использовать панель управления или панель управления, чтобы включить или отключить диалоговое телефонное Skype для бизнеса Server.
  
Вы можете включить диалоговое видеоконференцию с помощью Skype для бизнеса Server панели управления или Skype для бизнеса Server диспетчерской оболочки.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Включить или отключить диалоговое видеоконференцию с помощью Skype для бизнеса Server панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
4. В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Подробнее**. 
    
5. Чтобы разрешить пользователям присоединяться к собранием по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).
    
6. Нажмите кнопку **Сохранить**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Включить или отключить диалоговое конференцию с помощью Skype для бизнеса Server shell

Чтобы включить или отключить диалоговое видеоконференцию, используйте комлет **Set-CsConferencingPolicy** с параметром EnableDialInConferencing следующим образом:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Дополнительные сведения см. в дополнительных сведениях [в set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)

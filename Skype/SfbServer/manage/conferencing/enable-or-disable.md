---
title: Enable or disable dial-in conferencing in Skype for Business Server
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
description: Сводка. Узнайте, как включить или отключить в Skype для бизнеса Server использование панели управления или оболочки управления для отключения звонков по телефонной сети.
ms.openlocfilehash: 99691540306ba0cccf9c63af2e2188e839367bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828129"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Enable or disable dial-in conferencing in Skype for Business Server
 
**Сводка:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.
  
You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Enable or disable dial-in conferencing by using Skype for Business Server Control Panel

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем выберите **"Conferencing Policy" (Политика).**
    
4. В списке политик конференции выберите политику, для которой следует включить конференцию с подключением по телефону, щелкните **Изменить**, затем **Подробнее**. 
    
5. Чтобы разрешить пользователям присоединяться к собранием по телефону, установите флажок **Разрешить конференц-связь с подключением к ТСОП**. По умолчанию пользователи могут присоединяться к собраниям по телефону через телефонную сеть общего пользования (ТСОП).
    
6. Нажмите кнопку **Сохранить**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Enable or disable dial-in conferencing by using Skype for Business Server Management Shell

Чтобы включить или отключить функцию телефонной связи, используйте с параметром EnableDialInConferencing в качестве параметра **Set-CsConferencing:**
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Дополнительные сведения [см. в подстроке Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
  


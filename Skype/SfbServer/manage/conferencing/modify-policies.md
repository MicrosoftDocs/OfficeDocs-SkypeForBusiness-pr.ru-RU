---
title: Изменение политик в Skype для бизнеса Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: Сводка. Узнайте, как изменить политики в Skype для бизнеса Server.
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828009"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Изменение политик в Skype для бизнеса Server
 
**Сводка:** Learn how to modify conferencing policies in Skype for Business Server.
  
Политики можно изменять с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modify conferencing policies by using Skype for Business Server Control Panel

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем выберите **"Conferencing Policy" (Политика).**
    
4. В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.
    
6. Нажмите кнопку **Зафиксировать**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modify conferencing policies by using Skype for Business Server Management Shell

Для изменения политик conferencing используется cmdlet **Set-CsConferencingPolicy.**
  
В следующем примере изменяется значение свойства политики conferencing SalesConferencingPolicy. Команда задает для свойства AllowConferenceRecording значение False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в подстроке [Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
  


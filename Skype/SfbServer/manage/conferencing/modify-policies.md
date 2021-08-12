---
title: Изменение политик conferencing в Skype для бизнеса Server
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
description: Сводка. Узнайте, как изменить политики конференций в Skype для бизнеса Server.
ms.openlocfilehash: 5676a6bc0970a98fa76357deb1403c6b2337920273262c0a76a465b33d5d18c4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290357"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Изменение политик conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как изменить политики conferencing в Skype для бизнеса Server.
  
Политики конференций можно изменить с помощью панели Skype для бизнеса Server или с помощью Skype для бизнеса Server management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Изменение политик conferencing с помощью Skype для бизнеса Server панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
4. В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.
    
6. Нажмите кнопку **Зафиксировать**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Изменение политик conferencing с помощью Skype для бизнеса Server Management Shell

Чтобы изменить политики conferencing, используйте кодлет **Set-CsConferencingPolicy.**
  
В следующем примере изменяется значение свойства политики conferencing SalesConferencingPolicy. Команда задает значение свойства AllowConferenceRecording false:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)

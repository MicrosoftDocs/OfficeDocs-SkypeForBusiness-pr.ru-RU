---
title: Изменение политик conferencing в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: Сводка. Узнайте, как изменить политики конференций в Skype для бизнеса Server.
ms.openlocfilehash: f7f32d227ca33a62ed389a2638f3d784839be8d9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385707"
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

Чтобы изменить политики conferencing, используйте кодлет **Set-CsConferencingPolicy** .
  
В следующем примере изменяется значение свойства политики conferencing SalesConferencingPolicy. Команда задает значение свойства AllowConferenceRecording false:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).

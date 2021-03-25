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
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119428"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Изменение политик conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как изменить политики конференций в Skype для бизнеса Server.
  
Политики конференциинга можно изменить с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Изменение политик конференциинга с помощью панели управления Skype для бизнес-серверов

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнес-серверов.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
4. В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.
    
6. Нажмите кнопку **Зафиксировать**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Изменение политик конференций с помощью оболочки управления Skype для бизнес-серверов

Чтобы изменить политики conferencing, используйте кодлет **Set-CsConferencingPolicy.**
  
В следующем примере изменяется значение свойства политики conferencing SalesConferencingPolicy. Команда задает значение свойства AllowConferenceRecording false:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Дополнительные сведения, включая полный синтаксис и список параметров, см. в [обзоре Set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)

---
title: Изменение политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Сводка: сведения о том, как изменять политики конференц-связи в Skype для бизнеса Server.'
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991814"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Изменение политик конференц-связи в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как изменять политики конференц-связи в Skype для бизнеса Server.
  
Вы можете изменять политики конференц-связи с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Изменение политик конференц-связи с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.
    
6. Нажмите **Исполнить**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Изменение политик конференц-связи с помощью командной консоли Skype для бизнеса Server

Чтобы изменить политики Конференции, используйте командлет **Set-ксконференЦингполици** .
  
В следующем примере показано изменение значения свойства политики конференц-связи SalesConferencingPolicy. Команда присваивает свойству AllowConferenceRecording значение False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Дополнительные сведения, в том числе полный синтаксис и список параметров, приведены в разделе [Set-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  


---
title: Изменение политики конференц-связи в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Сводка: Узнайте, как для изменения политики конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 5883af04310f671e536460dbd466ce583cb52ebd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970242"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Изменение политики конференц-связи в Скайп для Business Server
 
**Сводка:** Узнайте, как для изменения политики конференц-связи в Скайп для Business Server.
  
Политики конференц-связи можно изменить с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Изменение политик конференц-связи с помощью Скайп для панели управления Business Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. В списке политик конференций выберите политику, которую нужно изменить, нажмите кнопку **Изменить**, а затем **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** измените любые параметры политики за исключением имени, которое нельзя изменить.
    
6. Нажмите **Исполнить**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Изменение политик конференц-связи с помощью Скайп для консоли Business Server

Для изменения политики конференц-связи, используйте командлет **Set-CsConferencingPolicy** .
  
В следующем примере показано изменение значения свойства политики конференц-связи SalesConferencingPolicy. Команда присваивает свойству AllowConferenceRecording значение False:
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Дополнительные сведения, включая полный синтаксис и список параметров [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)см.
  


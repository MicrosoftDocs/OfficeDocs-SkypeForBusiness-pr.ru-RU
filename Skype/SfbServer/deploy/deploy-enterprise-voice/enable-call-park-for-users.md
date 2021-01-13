---
title: Включить парковку вызовов для пользователей в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включить для пользователей парковку вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830959"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Включить парковку вызовов для пользователей в Skype для бизнеса
 
Включить для пользователей парковку вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
  
По умолчанию парковка вызовов отключена для всех пользователей. Пользователи не могут припарковать вызовы или получать припаркованные вызовы, пока они не будут включены для парковки вызовов в политике голосовой почты.
  
Парковку вызовов можно включить на глобальном уровне, на уровне сайта или пользователя. Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь — перед глобальным уровнем. Если у вас несколько политик голосовой почты, просмотрите все политики, чтобы включить парковку вызовов, а не только глобальную политику.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>To Use Skype for Business Server Control Panel to Enable Call Park for Users

1. Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.
    
2. Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.
    
4. Перейдите на вкладку **Политика голосовой связи**.
    
5. Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.
    
6. В разделе **Функции звонков** установите флажок **Включить Парковку вызовов**.
    
7. Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Использование cmdlets для обеспечения парковки вызовов для пользователей

1. Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Запустите:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Например, чтобы включить парковку вызовов для глобальной политики голосовой почты по умолчанию:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>См. также



[Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)


---
title: Включить парк вызовов для пользователей в Skype для бизнеса
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включить пользователей для call Park в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 84a37ad9e3b77042c1c2c04d1d6562b3bb780ee2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386348"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Включить парк вызовов для пользователей в Skype для бизнеса
 
Включить пользователей для call Park в Skype для бизнеса Server Корпоративная голосовая связь.
  
По умолчанию call-парк отключен для всех пользователей. Пользователи не могут припарковать вызовы или получить припаркованные вызовы до тех пор, пока они не будут включены для Call Park в голосовой политике.
  
Вы можете включить Call Park в глобальном масштабе или в области сайта или области пользователей. Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь — перед глобальным уровнем. Если у вас несколько голосовых политик, просмотрите все политики, чтобы включить Call Park, а не только глобальную политику.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Использование панели Skype для бизнеса Server, чтобы включить парк вызовов для пользователей

1. Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.
    
2. Откройте панель Skype для бизнеса Server управления.
    
3. В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.
    
4. Перейдите на вкладку **Политика голосовой связи**.
    
5. Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.
    
6. В разделе **Функции звонков** установите флажок **Включить Парковку вызовов**.
    
7. Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Использование cmdlets для включить парк вызовов для пользователей

1. Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
3. Запуск:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Например, чтобы включить Call Park для глобальной голосовой политики по умолчанию:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>См. также



[Создание или изменение голосовой политики и настройка записей использования PSTN в Skype для бизнеса](voice-policy-and-pstn-usage-records.md)


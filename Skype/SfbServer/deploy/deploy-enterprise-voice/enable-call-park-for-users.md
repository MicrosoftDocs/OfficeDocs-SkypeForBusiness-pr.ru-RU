---
title: Включение приостановки звонков для пользователей в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Включение пользователей на приостановку звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: c3ad2bcf70c7b175ba372ba2834e56209de9f664
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002559"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Включение приостановки звонков для пользователей в Skype для бизнеса
 
Включение пользователей на приостановку звонков в Skype для бизнеса Server Enterprise.
  
По умолчанию приостановление звонков для всех пользователей отключено. Пользователи не могут приостановить звонки или получить припаркованные звонки, пока они не будут включены в политику голосовой связи.
  
Вы можете включить приостановку звонков в глобальной области или в области действия сайта или пользователя. Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь – перед глобальным уровнем. Если у вас несколько политик голосовой связи, проверьте все политики, чтобы включить приостановку звонков, а не только глобальную политику.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Использование панели управления Skype для бизнеса Server для поддержки приостановки звонков для пользователей

1. Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.
    
2. Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.
    
4. Перейдите на вкладку **Политика голосовой связи**.
    
5. Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.
    
6. В разделе **Функции звонков** установите флажок **Разрешить парковку вызовов**.
    
7. Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Использование командлетов для поддержки приостановки звонков для пользователей

1. Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Например, чтобы включить приостановку звонков для глобальной политики голосовой связи по умолчанию:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>См. также



[Создание или изменение политики голосовой связи и настройка записей использования PSTN в Skype для бизнеса](voice-policy-and-pstn-usage-records.md)


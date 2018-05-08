---
title: Настройка параметров парковки вызовов в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Изменение параметров парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 8f4aa5025cbe364a44a45632ebcdf852ad6a65bc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a>Настройка параметров парковки вызовов в Skype для бизнеса 2015
 
Изменение параметров парковки вызовов в Скайп Business Server корпоративной голосовой связи.
  
Если не хотите использовать параметры по умолчанию парковка вызовов, можно настроить их. При установке приложения приостановки звонков по умолчанию настраиваются глобальные параметры. Можно изменять глобальные параметры, а также можно указать параметры узла. Командлет **New-CsCpsConfiguration** для создания новых параметров сайта. Командлет **Set-CsCpsConfiguration** используется для изменения существующих параметров.
  
> [!NOTE]
> Мы рекомендуем настроить хотя бы параметр **OnTimeoutURI** для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.
  
Используйте командлет **New-CsCpsConfiguration** или командлета **Set-CsCpsConfiguration** для настройки любых из следующих параметров:
  
|**Данный параметр:**|**Указывает следующее:**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.  <br/> Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.  <br/> |
|**EnableMusicOnHold** <br/> |Воспроизводится ли музыка для звонящего при парковке вызова.  <br/> Доступны значения True и False. Значение по умолчанию — True.  <br/> |
|**Значения MaxCallPickupAttempts** <br/> |Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для **OnTimeoutURI**. Значение по умолчанию — 1.<br/> |
|**OnTimeoutURI** <br/> |SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения **MaxCallPickupAttempts**. <br/> Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.<br/> |
   
### <a name="to-configure-call-park-settings"></a>Настройка параметров парковки вызовов

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Выполните следующую команду:
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Командлет **Get-CsSite** для определения сайта. Для получения дополнительных сведений Командная консоль Lync Server см.
  
    Например:
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>См. также

#### 

[Настройка парковки вызовов музыку при удержании inSkype для бизнеса 2015](customize-call-park-music-on-hold.md)
#### 

[Новый CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[SET-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[Командлет Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)


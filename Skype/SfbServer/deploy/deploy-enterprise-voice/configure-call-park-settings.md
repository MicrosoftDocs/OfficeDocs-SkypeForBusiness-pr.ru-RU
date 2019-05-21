---
title: Настройка параметров парковки звонков в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Изменение параметров парковки звонков в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: c456a519fc9f567bdef812adc533adaf03c4360a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303392"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Настройка параметров парковки звонков в Skype для бизнеса

Изменение параметров парковки звонков в Skype для бизнеса Server Enterprise.

Если вы не хотите использовать настройки по умолчанию для приостановки звонка, вы можете настроить их. При установке приложения для парковки по умолчанию устанавливаются глобальные параметры. Вы можете изменять глобальные параметры, а также задавать параметры для определенного сайта. С помощью командлета **New-кскпсконфигуратион** можно создавать новые параметры для определенного сайта. Используйте командлет **Set-кскпсконфигуратион** для изменения существующих параметров.

> [!NOTE]
> Мы рекомендуем настроить хотя бы параметр **OnTimeoutURI** для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.

Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:


| **Данный параметр:**                     | **Указывает следующее:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.  <br/> Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Воспроизводится ли музыка для звонящего при парковке вызова.  <br/> Доступны значения True и False. Значение по умолчанию — True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для **OnTimeoutURI**. Значение по умолчанию — 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения **MaxCallPickupAttempts**. <br/> Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Настройка параметров парковки для звонков

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Выполните следующую команду:

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Используйте командлет **Get-CsSite** для идентификации сайта. Подробности можно найти в документации по среде управления в Skype для бизнеса Server.

    Например:

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>См. также

[Настройка функции воспроизведения музыки для режима удержания при парковке вызова в Skype для бизнеса 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

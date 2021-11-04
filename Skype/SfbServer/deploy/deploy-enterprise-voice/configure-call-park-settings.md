---
title: Настройка параметров парка вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Изменение параметров парка вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 81d523991f1df5d9bc24f19d212ae63fa5b0beb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759141"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Настройка параметров парка вызовов в Skype для бизнеса

Изменение параметров парка вызовов в Skype для бизнеса Server Корпоративная голосовая связь.

Если вы не хотите использовать параметры Call Park по умолчанию, их можно настроить. При установке приложения Call Park глобальные параметры настраиваются по умолчанию. Можно изменить глобальные параметры, а также указать параметры, определенные для сайта. Для создания новых параметров, определенных для сайта, используйте комлет **New-CsCpsConfiguration.** Чтобы изменить существующие параметры, используйте комлет **Set-CsCpsConfiguration.**

> [!NOTE]
> Мы рекомендуем вам настроить хотя бы параметр **OnTimeoutURI** для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.

Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:


| **Данный параметр:**                     | **Указывает следующее:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.  <br/> Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Воспроизводится ли музыка для звонящего при парковке вызова.  <br/> Доступны значения True и False. Значение по умолчанию — True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для **OnTimeoutURI**. Значение по умолчанию — 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения **MaxCallPickupAttempts**. <br/> Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Настройка параметров парка вызовов

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Запустите: 

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Используйте командлет **Get-CsSite** для идентификации сайта. Подробные сведения см. в Skype для бизнеса Server документации по management Shell.

    Пример:

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>См. также

[Настройка музыки Call Park для удержания вSkype для бизнеса 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)
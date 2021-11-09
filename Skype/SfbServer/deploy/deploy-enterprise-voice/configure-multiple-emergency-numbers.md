---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Ознакомьтесь с этой темой, чтобы узнать, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.
ms.openlocfilehash: d79a57e64d52bfc6b0f1d8ee9a9bd9c3c1509658
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833915"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Настройка нескольких номеров экстренных служб в Skype для бизнеса

Ознакомьтесь с этой темой, чтобы узнать, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.

Skype для бизнеса Server поддерживает несколько номеров экстренных служб для клиента. Несколько номеров экстренных служб — это новая функция, представленная в накопительном обновлении за июнь 2016 г. Перед настройкой среды для поддержки нескольких номеров экстренных служб обязательно ознакомьтесь с планом для нескольких номеров экстренных служб в [Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> Если вы еще не обновили накопительное обновление за ноябрь 2016 г., см. в Skype для бизнеса Server [обновления 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)г. С накопительным обновлением за ноябрь 2016 г. число номеров экстренных служб поддержки увеличивается с 5 до 100.

## <a name="configure-multiple-emergency-numbers"></a>Настройка нескольких номеров экстренных служб

Чтобы настроить несколько номеров аварийной ситуации, используйте New-CsEmergencyNumber, а затем укажите параметр EmergencyNumbers с помощью cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Полное описание всех параметров политики расположения, таких как использование PSTN и требуемое расположение, см. [в инструкции Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)

Следующая команда создает новый номер аварийной ситуации со строкой 911 с помощью командлета New-CsEmergency:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Следующая команда связывает номер с указанной политикой расположения, указав параметр EmergencyNumbers в командлете Set-CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

В следующем примере создается номер аварийной ситуации с одной маской набора 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Следующая команда создает аварийный номер с несколькими масками набора:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

В следующем примере добавляется несколько номеров экстренных служб с несколькими масками на циферблате, а затем сопопосается номера экстренных служб с указанной политикой расположения:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для поставщиков медицинских услуг, которые используют как 911, так и 450:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для города Лондона:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько экстренных номеров для Индии:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

В следующем примере удаляется существующая запись со строкой Dial 911 и масками Dial 112 и 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
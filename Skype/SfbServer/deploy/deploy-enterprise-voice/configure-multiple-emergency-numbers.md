---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: В этом разделе вы узнаете, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804109"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Настройка нескольких номеров экстренных служб в Skype для бизнеса

В этом разделе вы узнаете, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.

Skype для бизнеса Server теперь поддерживает несколько номеров экстренных служб для клиента. Несколько номеров экстренных служб — это новая функция, представленная в накопительном обновлении за июнь 2016 г. Прежде чем настраивать среду для поддержки нескольких номеров экстренных служб, ознакомьтесь с планом для нескольких номеров экстренных служб [в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). С накопительным обновлением за ноябрь 2016 г. количество номеров экстренных служб поддержки увеличивается с 5 до 100.

## <a name="configure-multiple-emergency-numbers"></a>Настройка нескольких номеров экстренных служб

Чтобы настроить несколько номеров экстренных служб, используйте New-CsEmergencyNumber, а затем укажите параметр EmergencyNumbers с помощью cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Полное описание всех параметров политики расположения, таких как требуемое использование PSTN и расположение, см. в описании [Set-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)

Следующая команда создает новый номер экстренной службы со строкой набора 911 с помощью New-CsEmergency командлета:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Следующая команда связывает номер с указанной политикой расположения, указав параметр EmergencyNumbers в Set-CsLocationPolicy командлета:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

В следующем примере создается номер экстренной службы с одной маской набора номера 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Следующая команда создает номер экстренной службы с несколькими масками набора номера:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

В следующем примере добавляется несколько номеров экстренных служб с несколькими масками набора номера, а затем эти номера связывается с указанной политикой расположения:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для поставщиков услуг здравоохранения, которые используют номера 911 и 450:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для города Лондон:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для Индии:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

В следующем примере удаляется существующая запись со строками Dial 911 и Dial masks 112 и 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```

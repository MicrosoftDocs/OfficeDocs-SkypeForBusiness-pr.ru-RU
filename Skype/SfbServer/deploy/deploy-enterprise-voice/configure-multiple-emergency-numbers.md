---
title: Настройка нескольких номеров экстренной помощи в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: В этой статье рассказывается о том, как настроить несколько номеров для экстренного реагирования в Skype для бизнеса Server.
ms.openlocfilehash: a0a16536799024085afcce07d6a2a9a0e4c899e1
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001319"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Настройка нескольких номеров экстренной помощи в Skype для бизнеса

В этой статье рассказывается о том, как настроить несколько номеров для экстренного реагирования в Skype для бизнеса Server.

Skype для бизнеса Server теперь поддерживает несколько номеров экстренного реагирования для клиента. Несколько номеров для экстренного реагирования — это новая функция, представленная в накопительном обновлении за июнь 2016. Перед настройкой среды для поддержки нескольких номеров для экстренного реагирования прочтите [план для нескольких номеров экстренной помощи в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Если вы еще не обновили накопительный пакет обновления за ноябрь 2016 ноября, ознакомьтесь с [обновлением для Skype для бизнеса Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Благодаря накопительному обновлению за ноябрь 2016 ноября количество номеров экстренных случаев поддержки возрастает от 5 до 100. 

## <a name="configure-multiple-emergency-numbers"></a>Настройка нескольких номеров экстренных служб

Чтобы настроить несколько номеров для экстренного реагирования, используйте командлет New-Ксемерженцинумбер, а затем укажите параметр Емерженцинумберс с помощью командлетов [New-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Полное описание всех параметров политики местоположения (например, использование PSTN и расположение) можно найти в разделе [Set-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Следующая команда создает новый номер экстренной службы со строкой набора 911 с помощью командлета New-CsEmergency:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

Следующая команда связывает номер с указанной политикой расположения путем задания параметра EmergencyNumbers в командлете Set-CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

В следующем примере создается номер экстренной службы с одной маской номера — 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

Следующая команда создает номер для экстренного реагирования с несколькими масками набора номера:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

В следующем примере добавляется несколько номеров экстренных служб с несколькими масками номера, а затем эти номера связываются с выбранной политикой расположения:

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

В следующем примере настраивается несколько номеров экстренных служб для Лондона:

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

В следующем примере выполняется удаление существующей записи со строкой набора 911 и масками номеров 112 и 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```



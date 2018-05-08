---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: В этой статье описываются способы настройки нескольких номеров экстренных служб в Skype для бизнеса Server 2015.
ms.openlocfilehash: ad2f048294b7eeef6d675fdf80884ae13cc75a61
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a>Настройка нескольких номеров экстренных служб в Skype для бизнеса 2015
 
В этой статье описываются способы настройки нескольких номеров экстренных служб в Skype для бизнеса Server 2015.
  
Скайп для Business Server теперь поддерживает несколько аварийного номера для клиента. Несколько аварийного номера — это новая возможность, введенные в 2016 июня накопительного обновления. Прежде чем настраивать среду для поддержки нескольких аварийного номера, обязательно прочитайте [Планирование нескольких аварийного номера в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).
  
> [!NOTE]
> Если вы еще не был обновлен для 2016 ноября накопительные пакеты обновления, посетите страницу [обновления для Скайп для Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). С помощью 2016 ноября накопительные пакеты обновления, количество номеров экстренные службы поддержки увеличивается от 5 до 100. 
  
## <a name="configure-multiple-emergency-numbers"></a>Настройка нескольких номеров экстренных служб

Чтобы настроить несколько аварийного номера, используйте командлет New-CsEmergencyNumber и укажите параметр EmergencyNumbers с помощью командлетов [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Полное описание всех расположение параметры политики, такие как режим работы с ТСОП и необходимости расположение в разделе [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).
  
Следующая команда создает новый номер экстренной службы со строкой набора 911 с помощью командлета New-CsEmergency:
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

Следующая команда связывает номер с указанной политикой расположения путем задания параметра EmergencyNumbers в командлете Set-CsLocationPolicy:
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

В следующем примере создается номер экстренной службы с одной маской номера — 112:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

Далее команда создает аварийного номера с несколько масок телефонных:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

В следующем примере добавляется несколько номеров экстренных служб с несколькими масками номера, а затем эти номера связываются с выбранной политикой расположения:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

В следующем примере настраивается несколько номеров экстренных служб для поставщиков услуг здравоохранения, которые используют номера 911 и 450:  
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для Лондона:
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

В следующем примере настраивается несколько номеров экстренных служб для Индии:
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

В следующем примере выполняется удаление существующей записи со строкой набора 911 и масками номеров 112 и 999:
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```



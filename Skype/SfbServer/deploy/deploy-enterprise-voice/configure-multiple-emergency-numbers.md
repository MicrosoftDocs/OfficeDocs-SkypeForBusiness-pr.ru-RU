---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этом разделе рассказывается, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027800"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Настройка нескольких номеров экстренных служб в Skype для бизнеса

В этом разделе рассказывается, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.

Skype для бизнеса Server теперь поддерживает несколько номеров экстренных служб для клиента. Несколько номеров для экстренных служб — это новая функция, появившаяся в накопительном пакете обновления за июнь 2016 года. Прежде чем настраивать среду для поддержки нескольких номеров экстренных служб, ознакомьтесь со сведениями [о планировании нескольких номеров экстренных служб в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Если вы еще не обновили накопительный пакет обновления 2016 для системы, ознакомьтесь со статьей [Updates to Skype для бизнеса Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). С накопительным пакетом обновления за ноябрь 2016 ноября количество номеров экстренных служб поддержки возрастает от 5 до 100.

## <a name="configure-multiple-emergency-numbers"></a>Настройка нескольких номеров экстренных служб

Чтобы настроить несколько номеров экстренных служб, используйте командлет New – Ксемерженцинумбер, а затем укажите параметр EmergencyNumbers с помощью командлетов [New — CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set + CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Полное описание всех параметров политики расположения, таких как использование PSTN и требуемое расположение, приведено в разделе [Set – CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Следующая команда создает новый номер для экстренного реагирования с набором строк 911 с помощью командлета New – Ксемерженци:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Следующая команда связывает номер с указанной политикой расположения, указывая параметр EmergencyNumbers в командлете Set – CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

В следующем примере создается номер для экстренного реагирования с одной маской набора номера 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Следующая команда создает номер для экстренного реагирования с несколькими масками набора номера:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

В следующем примере показано, как добавить несколько номеров экстренных служб с несколькими масками набора номера, а затем связать номера экстренных служб с указанной политикой расположения:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

В следующем примере настраивается несколько номеров экстренных служб для поставщиков услуг здравоохранения, использующих как 911, так и 450:

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

В следующем примере настраивается несколько номеров экстренных служб для Индии:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

В следующем примере удаляется существующая запись с набором номера 911 и масками набора 112 и 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```

---
title: Маскировка номеров телефонов Microsoft Teams собраниях
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как маскировать номера телефонов Microsoft Teams собраниях
ms.openlocfilehash: afdbaa4f2f437728aad14e3731ab3e26ba90f36d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828432"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Маскировка номеров телефонов Microsoft Teams собраниях

Для обеспечения конфиденциальности номера телефонов участников, которые используют Teams аудиоконференцию, полностью отображаются внутренним участникам. Эти числа маскироваться от участников за пределами вашей организации. Этот параметр по умолчанию для всех организаций. Маскировка отображается, как показано на рисунке ниже.

![пример маскировки номера телефона.](media/hiddenPhoneNum.png)

В определенных случаях использования в отрасли администраторы могут выбрать, как номера телефонов участников аудиоконференции будут отображаться на собраниях, организованных в их клиенте. Администраторы могут выбрать один из трех вариантов:

- Телефон маскироваться только от внешних участников. Участники, которые входят в клиент организатора собрания, по-прежнему видят полный номер телефона.
- Телефон всех в собрании, кроме организатора, в масках.
- Телефон будут отсвечены, что делает их видимыми для всех на собрании.

Этот параметр применяется во всех поверхностях собрания, где вы можете получить номера телефонов.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Настройка маски для номеров телефонов с помощью Microsoft PowerShell

Чтобы изменить параметр маскировки телефонной сети общего перейти на другой телефон (ОКП), задате один из доступных параметров для параметра **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

Чтобы скрыть телефонные номера только внешних участников, запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Чтобы скрыть телефонные номера всех участников собрания (кроме организатора), запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Чтобы отключить маску номеров телефонов, запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
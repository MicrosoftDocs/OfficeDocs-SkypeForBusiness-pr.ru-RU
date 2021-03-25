---
title: Маскировка номеров телефонов в собраниях Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как скрыть номера телефонов в собраниях Microsoft Teams
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117717"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Маскировка номеров телефонов в собраниях Microsoft Teams

Для обеспечения конфиденциальности номера телефонов участников, которые используют аудиоконференцию, полностью отображаются для внутренних участников. Эти номера маскироваться от участников за пределами вашей организации. Этот параметр по умолчанию для всех организаций. Маскировка отображается, как показано на рисунке ниже.

![Пример маскировки номера телефона](media/hiddenPhoneNum.png)

В определенных отраслевых случаях использования администраторы могут выбирать, как номера телефонов участников аудиоконференции отображаются в собраниях, организованных в их клиенте. Администраторы могут выбрать один из трех вариантов:

- Номера телефонов маскируется только от внешних участников. Участники, в которых состоит клиент организатора собрания, по-прежнему видят полный номер телефона.
- Номера телефонов маскироваться от всех в собрании, кроме организатора.
- При этом будут отсвечены номера телефонов, что делает их видимыми для всех в собрании.

Этот параметр применяется на всех поверхностях собрания, где вы можете получить телефонные номера.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Настройка маскровки номеров телефонов с помощью Microsoft PowerShell

Чтобы изменить параметр маскровки телефонной сети общего перейти на другой телефонную сеть (STN), задате один из доступных параметров для параметра **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

Чтобы скрыть номера телефонов только от внешних участников, запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Чтобы скрыть номера телефонов от всех участников собрания (кроме организатора), запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Чтобы отключить маскировку номеров телефонов, запустите следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
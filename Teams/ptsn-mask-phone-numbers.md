---
title: Маскировка номеров телефонов на собраниях Microsoft Teams
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как маскировать номера телефонов на собраниях Microsoft Teams
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270824"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Маскировка номеров телефонов на собраниях Microsoft Teams

Для обеспечения конфиденциальности номера телефонов участников, которые присоединяются к собранию Teams с помощью аудиоконференций, полностью отображаются внутренним участникам. Номера маскируются от участников за пределами организации. Этот параметр используется по умолчанию для всех организаций. Маскированные числа отображаются, как показано на следующем рисунке:

![пример маскируемого номера телефона.](media/hiddenPhoneNum.png)

В определенных отраслевых случаях администраторы могут выбирать, как номера телефонов участников аудиоконференций отображаются на собраниях, организованных в клиенте. Администраторы могут выбрать один из трех вариантов:

- Номера телефонов маскируются только от внешних участников. Участники, принадлежащие клиенту организатора собрания, по-прежнему видят полный номер телефона.
- Номера телефонов маскируются от всех участников собрания, кроме организатора.
- Номера телефонов не маскируются, что делает их видимыми для всех участников собрания.

Этот параметр применяется ко всем поверхностям собрания, где предоставляются номера телефонов.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Настройка маскирования номеров телефонов с помощью Microsoft PowerShell

Чтобы изменить параметр маскирования ТСОП, **`MaskPstnNumbersType`** задайте для параметра [командлета Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) один из доступных параметров.

Чтобы маскировать номера телефонов только от внешних участников, выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Чтобы маскировать номера телефонов всех участников собрания (кроме организатора), выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Чтобы отключить маскирование номеров телефонов, выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```

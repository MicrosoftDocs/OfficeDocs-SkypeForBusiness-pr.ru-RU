---
title: Маскирование номеров телефонов в собраниях Microsoft Teams
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
description: Узнайте, как маскировать телефонные номера в собраниях Microsoft Teams
ms.openlocfilehash: cad28ad446c39a45b865fd24767347fdf11bb9c8
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801770"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Маскирование номеров телефонов в собраниях Microsoft Teams

Для обеспечения конфиденциальности номера телефонов участников, которые входят в собрание Teams с помощью аудиоконференций, полностью отображаются для внутренних участников. Номера маскируются от участников за пределами вашей организации. Этот параметр используется по умолчанию для всех организаций. Замаскированное число отображается, как показано на следующем рисунке:

![пример номера телефона в маске.](media/hiddenPhoneNum.png)

Для конкретных отраслевых вариантов использования администраторы могут выбирать, как номера телефонов участников аудиоконференций отображаются на собраниях, организованных в их клиенте. Администраторы могут выбрать один из трех вариантов:

- Номера телефонов маскируются только от внешних участников. Участники, принадлежащие клиенту организатора собрания, по-прежнему видят полный номер телефона.
- Номера телефонов маскируются от всех участников собрания, кроме организатора.
- Номера телефонов распакуются, что делает их видимыми для всех участников собрания.

Этот параметр применяется ко всем поверхностям собрания, где предоставляются номера телефонов.

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>Использование Центра администрирования Teams для настройки маскирования номеров телефонов

Чтобы изменить параметр маскировки телефонной сети общего пользования (ТСОП) в Центре администрирования Teams, войдите в Центр администрирования Teams с правами администратора, выберите **Мосты** > **конференц-связи** собраний на панели навигации слева, а затем выберите **Параметры моста**. **Идентификаторы вызывающего объекта в маске** отображаются в раскрывающемся списке в нижней части области параметров моста и позволяют выбрать следующее:

- Участникам за пределами вашей организации
- Всем участникам собрания
- Отключено

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Использование Microsoft PowerShell для настройки маскировки номера телефона

Чтобы изменить параметр маскирования ТСОП в PowerShell, задайте **`MaskPstnNumbersType`** для параметра [командлета Set-CsOnlineDialInConferencingTenantSettings один из доступных](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) параметров.

Чтобы скрыть номера телефонов только от внешних участников, выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Чтобы замаскировать номера телефонов от всех участников собрания (кроме организатора), выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Чтобы отключить маскирование номеров телефонов, выполните следующую команду:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```

---
title: Маскировка номеров телефонов в собраниях Майкрософт Teams
author: heidip
ms.author: heidip
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
description: Узнайте, как маскировать телефонные номера в собраниях Майкрософт Teams
ms.openlocfilehash: 7072d1853a49d9e7ebc59e360c971874ed6549a3
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242273"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Маскировка номеров телефонов в собраниях Майкрософт Teams

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

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Использование Майкрософт PowerShell для настройки маскировки номера телефона

Чтобы изменить параметр маскирования ТСОП в PowerShell, задайте **`MaskPstnNumbersType`** для параметра [командлета Set-CsOnlineDialInConferencingTenantSettings один из доступных](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) параметров.

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

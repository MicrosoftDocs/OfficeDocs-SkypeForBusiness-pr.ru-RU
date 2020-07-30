---
title: Помощник по голосовым сообщениям кортаны в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Сведения об использовании голосового помощника Кортаны с командами
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522325"
---
# <a name="cortana-voice-assistance-in-teams"></a>Помощь по голосовой связи кортаны в Teams

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> Поддержка голосовой почты кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android только для пользователей из Соединенных Штатов. В настоящее время она недоступна для клиентов GCC, GCC-High, DoD, и для них. В будущих выпусках будут вычислены дополнительные языки и регионы.

Голосовая служба кортаны в мобильном приложении Teams позволяет пользователям Microsoft 365 предприятия ускорить взаимодействие, совместную работу и задачи, связанные с собраниями, с помощью голосового языка. Пользователи могут поговорить с Кортаной, нажав кнопку микрофона, расположенную в правом верхнем углу приложения Teams Mobile. Чтобы быстро подключаться к группе в пути, пользователи могут сказать запросы, например "позвонить Megan" или "отправить сообщение на мое приглашение на собрание". Пользователи также могут присоединяться к собраниям, нажимая "присоединиться к следующему собранию", и использовать голосовую помощь для предоставления доступа к файлам, проверки календаря и других возможностей. Эти возможности голосовой связи доставляются с использованием [служб кортаны Enterprise](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) , которые полностью соответствуют требованиям к конфиденциальности, безопасности и соблюдению требований в Office 365 в [терминах Интернет-служб (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

На этом рисунке показано, как отправить чат в Кортана на мобильном устройстве.

![На рисунке показана последовательность на мобильных экранах с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Элементы управления администрированием и ограничениями

Помощь по голосовой связи кортаны в Teams осуществляется с помощью служб, которые полностью соответствуют требованиям Office 365, а также о том, как это было отражено в терминах Интернет-служб (OST). Эта функция будет включена по умолчанию для клиентов.

Администраторы клиентов могут управлять тем, кто в своем клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy). Этот параметр политики можно задать либо на уровне учетной записи пользователя, либо в клиенте. Администраторы могут использовать поле CortanaVoiceInvocationMode в рамках этого элемента управления политики, чтобы определить, отключено ли Кортана, включено с помощью кнопки "Отправить", а также с вызовом Word (применимо к устройствам, поддерживающим эту функцию).

Администраторы могут использовать следующие командлеты PowerShell для управления этой политикой (в настоящее время эта политика недоступна в центре администрирования Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Например, в приведенной ниже команде создается новая политика с именем "EmployeeCortanaPolicy", в которой отключен голосовой помощник Кортаны в Microsoft Teams.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

В этом примере показано, как обновить существующую политику с именем "EmployeeCortanaPolicy" и включить голосовой помощник Кортаны в Microsoft Teams с помощью кнопки "Отправить". Пользователи смогут вызвать Кортана, нажав на кнопку "микрофон Кортаны" в Teams. Вызов функции пробуждения Word (Привет, Кортана!) будет отключен.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

В этом примере показано, как обновить политику и включить голосовой помощник Кортаны с помощью кнопки и вызова пробуждения по словам.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> На момент первоначального выпуска для пользователей Microsoft 365 Enterprise в США на английском языке приложение Teams не будет поддерживать функцию активации Word, но будет поддерживаться в будущем.

## <a name="user-control"></a>Пользовательский элемент управления

Отдельные пользователи могут опробовать голосовую справку Кортаны в мобильном приложении Teams, нажав кнопку "микрофон". Кроме того, они могут управлять включением Кортаны в Teams для устройства с помощью параметра в мобильном приложении Teams.

1. Откройте мобильное приложение Teams.

2. Перейдите в раздел **Параметры**.

3. Выберите **Кортана**.

4. Установите переключатель в положение **вкл** . **, в**зависимости от того, хотите ли вы использовать голосовую поддержку кортаны на устройстве.

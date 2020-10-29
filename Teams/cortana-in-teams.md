---
title: Помощь по голосовой связи кортаны в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Инструкции по использованию голосовой поддержки Кортаны в Teams
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785393"
---
# <a name="cortana-voice-assistance-in-teams"></a>Помощь по голосовой связи кортаны в Teams

> [!Note]
> Поддержка голосовой почты кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android, а в Microsoft Teams — только для пользователей из Соединенных Штатов. В настоящее время она недоступна для клиентов GCC, GCC-High, DoD, и для них. В будущих выпусках будут вычислены дополнительные языки и регионы.

Голосовая помощь кортаны в приложении Teams и на устройствах отображения в Microsoft Teams позволяет пользователям Microsoft 365 предприятия ускорить взаимодействие, совместную работу и задачи, связанные с собраниями, с помощью голосового языка. Пользователи могут говорить с Кортаной, выбирая кнопку микрофона, расположенную в правом верхнем углу приложения Teams, или произнося &#8220;Кортаны&#8221; на экране Microsoft Teams. Чтобы быстро подключаться с помощью своей команды и во время работы, пользователи могут сказать такие запросы, как &#8220;позвонить Megan&#8221; или &#8220;отправить сообщение на свое следующее собрание&#8221;. Пользователи также могут присоединяться к собраниям, выполняя &#8220;присоединиться к следующему собранию&#8221; и выполнив помощь по голосовой связи для совместного использования файлов, проверки календаря и других возможностей. Эти возможности голосовой связи доставляются с использованием [служб кортаны Enterprise](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) , которые полностью соответствуют требованиям к конфиденциальности, безопасности и соблюдению требований в Office 365 в [терминах Интернет-служб (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

На этом рисунке показано, как отправить чат с помощью Кортаны на мобильном устройстве.

![На рисунке показана последовательность на мобильных экранах с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Элементы управления администрированием и ограничениями

Помощь по голосовой связи кортаны в Teams осуществляется с помощью служб, которые полностью соответствуют требованиям Office 365, а также о том, как это было отражено в терминах Интернет-служб (OST). Эта функция будет включена по умолчанию для клиентов.

Администраторы клиентов могут управлять тем, кто в своем клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy). Этот параметр политики можно задать либо на уровне учетной записи пользователя, либо в клиенте. Администраторы могут использовать поле CortanaVoiceInvocationMode в этом элементе управления политики, чтобы определить, отключено ли Кортана, включить с помощью кнопки "Отправить", а также использовать вызов Word (применимо только к устройствам, поддерживающим эту функцию, например в Microsoft Teams).

Администраторы могут использовать следующие командлеты PowerShell для управления этой политикой (в настоящее время эта политика недоступна в центре администрирования Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Например, приведенная ниже команда создает новую политику с именем &#8220;EmployeeCortanaPolicy&#8221;, в которой служба поддержки голосовой связи Кортаны в Microsoft Teams отключена.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

В этом примере показано обновление существующей политики с именем &#8220;EmployeeCortanaPolicy&#8221; и включение голосовой поддержки Кортаны в Microsoft Teams с помощью кнопки "Отправить". Пользователи смогут вызвать Кортана, нажав кнопку "микрофон Кортаны" в Teams. Вызов функции пробуждения Word (&#8220;Привет, Кортана&#8221; или &#8220;Кортаны&#8221;) будет отключена.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

В этом примере показано, как обновить политику и включить голосовую помощь Кортаны с помощью кнопки и вызова пробуждения по словам.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> На момент первоначального выпуска для пользователей Microsoft 365 Enterprise в США на английском языке приложение Teams не будет поддерживать функцию активации Word, но будет поддерживаться в будущем. Активация Word в автономном выпуске будет работать на устройствах с интерфейсом Microsoft Teams.

## <a name="user-control"></a>Пользовательский элемент управления

Отдельные пользователи могут опробовать голосовую справку Кортаны в мобильном приложении Teams, нажав кнопку "микрофон". Они могут попытаться использовать голосовые команды Кортаны в Microsoft Teams, просто произнося &#8220;Кортану. &#8221; они также могут управлять включением Кортаны в Teams для устройства с помощью параметра в мобильном приложении Teams или на экране Microsoft Teams.

1. Откройте мобильное приложение Teams или перейдите на экран внешний вид экрана в Microsoft Teams.

2. В мобильном приложении Teams перейдите в раздел **Параметры** . На экране Microsoft Teams выберите аватар пользователя и нажмите кнопку Параметры. Если Кортана включена, скажем, &#8220;Кортана, перейдите к разделу Параметры. &#8221;

3. Выберите **Кортана** .

4. Установите переключатель в положение **вкл** . **, в** зависимости от того, хотите ли вы использовать голосовую поддержку кортаны на устройстве.

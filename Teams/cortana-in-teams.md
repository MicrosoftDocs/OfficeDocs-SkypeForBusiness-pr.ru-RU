---
title: Кортана голосовой помощи в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Узнайте, как использовать Кортана голосовой помощи Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10d42d2cd2f876f27153336695e4639830c5bb91
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726148"
---
# <a name="cortana-voice-assistance-in-teams"></a>Кортана голосовой помощи в Teams

> [!Note]
> Кортана поддерживается в мобильных приложениях Microsoft Teams для iOS, Android и Microsoft Teams для пользователей в США, Соединенном Королевстве, Канаде, Индии и Австралии. Комнаты Microsoft Teams на Windows поддерживается только для пользователей в США. Кортана в настоящее время голосовая помощь недоступна для клиентов GCC, GCC high, DoD и других клиентов EDU. Кортана голосовая помощь в мобильном приложении Teams теперь доступна для клиентов с EDU в EN-US. Расширение до дополнительных языков и регионов будет происходить в рамках будущих выпусков.

> [!Note]
> Кортана в Комнаты Microsoft Teams выпущена предварительная версия. В предварительной версии Кортана поддерживаются только в США с en-US на устройствах, которые подключили микрофоны Microphone.

Кортана голосовой помощи в мобильном приложении Teams, в Комнаты Microsoft Teams в Windows и на устройствах Microsoft Teams позволяет пользователям Microsoft 365 корпоративный оптимизировать взаимодействие, совместную работу и задачи, связанные с собраниями, с использованием естественного языка речи. Чтобы говорить с Кортана, можно нажать кнопку микрофона в правом верхнем верхнем месте мобильного приложения Teams или сказать &#8220;Кортана&#8221; в комнате Microsoft Teams или при использовании Microsoft Teams экрана. Чтобы быстро общаться с командой, находясь в путь, пользователи могут отправлять запросы, например &#8220;позвонить&#8221;&#8221; или &#8220;отправить сообщение на мое следующее собрание&#8221;. Пользователи также могут присоединяться к собраниям, &#8220;присоединиться к следующему собранию&#8221; и использовать голосовую помощь для обмена файлами, проверки календаря и многого другого. Эти голосовые помощники оказания Кортана корпоративного уровня, которые полностью соответствуют требованиям Office 365 конфиденциальности, безопасности и соответствии требованиям, указанным в Условиях [онлайн-услуг](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Управление администратором и ограничения

Кортана голосовая помощь в Teams выполняется с помощью служб, которые полностью соответствуют требованиям Office 365 конфиденциальности, безопасности и соответствия требованиям на уровне предприятия, как отражено в Условиях онлайн-услуг (OST). Эта функция будет включена по умолчанию для клиентов.

Администраторы клиентов могут управлять тем, кто в своем клиенте может Кортана голосовую помощь Teams с помощью политики (TeamsCortanaPolicy). Эта политика задается на уровне учетной записи пользователя или клиента. Администраторы могут использовать поле CortanaVoiceInvocationMode в этом средстве управления политикой, чтобы определить, отключена ли Кортана, включена ли только нажатие кнопки вызова или включено ли оно (применимо к устройствам, которые его поддерживают, например Microsoft Teams дисплею).

Для управления этой политикой администраторы могут использовать следующие Microsoft Teams PowerShell.

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Например, с помощью приведенной ниже команды создается новая политика с именем &#8220;EmployeeCortanaPolicy&#8221; где Кортана голосовая помощь в Microsoft Teams отключена.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

В этом примере показано обновление существующей политики с использованием имен &#8220;EmployeeCortanaPolicy&#8221; и включение Кортана голосовой помощи в Microsoft Teams с помощью push-кнопки вызова. Пользователи смогут вызывать Кортана с помощью кнопки Кортана микрофона в Teams. Выключить слово (&#8220;отключена Кортана&#8221; или &#8220;Кортана&#8221;)  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

В этом примере показано обновление политики и включение Кортана голосовой помощи с помощью push-кнопки и включения вызова word.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

На момент первоначального выпуска для пользователей Microsoft 365 корпоративный в США на английском языке доступны следующие функции:

- Мобильное Teams не поддерживает активацию word, но в будущем оно будет поддерживаться.  

- Комнаты Microsoft Teams на Windows и Microsoft Teams устройствах с дисплеем поддерживают активацию word.

## <a name="user-control"></a>Пользовательский контроль

Отдельные пользователи могут попробовать Кортана голосовой помощи на разных устройствах:

- В мобильном приложении Teams кнопку микрофона.

- Выберите кнопку микрофона или скажите "Кортана" в Комнаты Microsoft Teams.

- Скажите "Кортана" на Microsoft Teams отображает устройства.

Вы можете управлять тем, Кортана включена ли Teams на вашем устройстве, с помощью параметра устройства.

![отображает развитие мобильных окон, когда вы включаете Кортана.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Комнаты Microsoft Teams на Windows

Внесение изменений на уровне устройства Кортана на уровне клиента. Кортана будет выключено по умолчанию.

Чтобы Кортана на уровне устройства, эти атрибуты XML должны быть добавлены в XML-файл SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Внесение изменений на уровне собрания Кортана на уровне устройства.

Чтобы включить Кортана голосовую помощь во время собрания,  переключите или включите или **выключите**. После окончания собрания Кортана к настройкам уровня устройства.

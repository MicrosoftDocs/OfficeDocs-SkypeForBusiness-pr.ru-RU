---
title: Голосовая помощь Кортаны в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Узнайте, как использовать голосовую помощь Кортаны для Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886738"
---
# <a name="cortana-voice-assistance-in-teams"></a>Голосовая помощь Кортаны в Teams

> [!Note]
> Голосовая помощь Кортаны поддерживается в Microsoft Teams мобильных приложениях для iOS и Android и Microsoft Teams для пользователей в США, Соединенном Королевстве, Канаде, Индии и Австралии.  Комнаты Microsoft Teams на Windows поддерживается только для пользователей в США. Голосовая помощь Кортаны в настоящее время недоступна для клиентов GCC, GCC High, DoD и EDU. Расширение до дополнительных языков и регионов будет происходить в рамках будущих выпусков.

> [!Note]
> Голосовая помощь Кортаны в Microsoft Teams Rooms выпущена в предварительной версии. В предварительной версии Кортана поддерживается только в США на устройствах, на которые подключены микрофоны Изумительного.

Голосовая помощь Кортаны в мобильном приложении Teams, Комнаты Microsoft Teams в Windows и на устройствах Microsoft Teams позволяет пользователям Microsoft 365 корпоративный оптимизировать взаимодействие, совместную работу и задачи, связанные с собраниями, с использованием естественного языка речи. Пользователи могут говорить с Кортаной, нажав кнопку микрофона в правом верхнем верхнем месте мобильного приложения Teams или нажав &#8220;Кортана&#8221; в комнате Microsoft Teams или при использовании Microsoft Teams дисплея. Чтобы быстро общаться с командой, находясь в путь, пользователи могут отправлять запросы, например &#8220;позвонить&#8221; или &#8220;отправить сообщение на мое следующее собрание&#8221;. Пользователи также могут присоединяться к собраниям, &#8220;присоединиться к следующему собранию&#8221; и использовать голосовую помощь для обмена файлами, проверки календаря и многого другого. Эти голосовые помощники ставляются с помощью служб корпоративного уровня Кортаны, которые полностью соответствуют Office 365 конфиденциальности, безопасности и соблюдению требований, указанных в Условиях [онлайн-услуг](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

На изображении показана отправка чата с помощью Кортаны на мобильном устройстве.

![Последовательность мобильных экранов с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Управление администратором и ограничения

Голосовая помощь Кортаны в Teams выполняется с помощью служб, которые полностью соответствуют требованиям Office 365 конфиденциальности, безопасности и соответствии требованиям на уровне предприятия, как отражено в Условиях онлайн-услуг (OST). Эта функция будет включена по умолчанию для клиентов.

Администраторы клиента могут управлять тем, кто в своем клиенте может использовать голосовую помощь Кортаны Teams с помощью политики (TeamsCortanaPolicy). Эту политику можно настроить на уровне учетной записи пользователя или клиента. Администраторы могут использовать поле CortanaVoiceInvocationMode в этом средстве управления политикой, чтобы определить, отключена ли Кортана, включена ли она только с помощью кнопки вызова или с отключением слова (применимо к устройствам, которые ее поддерживают, например Microsoft Teams дисплею).

Для управления этой политикой администраторы могут использовать следующие Microsoft Teams PowerShell.

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Например, с помощью приведенной ниже команды создается новая политика с именем &#8220;EmployeeCortanaPolicy&#8221; где голосовая помощь Кортаны в Microsoft Teams отключена.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

В этом примере показано обновление существующей политики с использованием имен &#8220;EmployeeCortanaPolicy&#8221; и включение голосовой помощи Кортаны в Microsoft Teams с помощью кнопки вызова. Пользователи смогут вызвать Кортану, нажав кнопку "Микрофон Кортаны" в Teams. Выключив слово (&#8220;привет, Кортана&#8221; или &#8220;Кортана&#8221;) будет отключена.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

В этом примере показано обновление политики и включение голосовой помощи Кортаны с помощью push-кнопки и включения вызова слова.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

На момент первоначального выпуска для пользователей Microsoft 365 корпоративный в США на английском языке доступны следующие функции:

- Мобильное Teams не поддерживает активацию word, но в будущем оно будет поддерживаться.  

- Комнаты Microsoft Teams на Windows и Microsoft Teams поддерживают активацию word.

## <a name="user-control"></a>Пользовательский контроль

Отдельные пользователи могут попробовать голосовую помощь Кортаны на разных устройствах:

- В мобильном приложении Teams кнопку микрофона.

- Выберите кнопку микрофона или скажите "Кортана" в Комнаты Microsoft Teams.

- Скажите "Кортана" на Microsoft Teams дисплеях.

Вы можете управлять тем, включена ли Кортана в Teams для вашего устройства, используя параметр на устройстве.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams мобильного приложения или Microsoft Teams экрана

  1. Откройте мобильное Teams.

  2. Выберите **Параметры**  >  **Кортану**.

  3. Переместить **вкл.** или **Выкл.**

### <a name="microsoft-teams-display"></a>Microsoft Teams экрана

  1. Перейдите к экрану окружающего (домашнего) Microsoft Teams экрана.

  2. Выберите аватар пользователя, а затем **—** Параметры . Если Кортана включена, скажите "Кортана, Параметры".

  3. Переместить **вкл.** или **Выкл.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Комнаты Microsoft Teams Windows

Внесение изменений на уровне устройства доступно, если Кортана включена на уровне клиента. Кортана будет выключена по умолчанию.

Чтобы включить Кортану на уровне устройства, эти атрибуты XML должны быть добавлены в XML-файл SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Внесение изменений на уровне собрания доступно, если Кортана включена на уровне устройства.

Чтобы включить голосовую помощь Кортаны во время собрания, переместите в нее или **Выкл.** После окончания собрания Кортана вернется к настройкам уровня устройства.

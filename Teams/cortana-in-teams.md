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
description: Узнайте, как использовать голосовую помощь Кортаны в Teams
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
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686445"
---
# <a name="cortana-voice-assistance-in-teams"></a>Голосовая помощь Кортаны в Teams

> [!Note]
> Голосовая помощь Кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android, в комнатах Microsoft Teams для Windows и в Microsoft Teams отображается только для пользователей в США. В настоящее время она недоступна для клиентов GCC, GCC-High, DoD и EDU. Расширение до дополнительных языков и регионов будет происходить в будущих выпусках.

> [!Note]
> Голосовая помощь Кортаны в комнатах Microsoft Teams выпущена в режиме предварительной версии. В предварительной версии Кортана поддерживается только в США с языком EN-US на устройствах, на которые подключены микрофоны В этом режиме.

Голосовая помощь Кортаны в мобильном приложении Teams, в комнатах Microsoft Teams для Windows и устройствах отображения Microsoft Teams позволяет пользователям Microsoft 365 корпоративный оптимизировать взаимодействие, совместную работу и задачи, связанные с собраниями, с использованием естественного языка речи. Пользователи могут говорить с Кортаной, нажав кнопку микрофона в правом верхнем верхнем приложении Teams или нажав &#8220;Кортана&#8221; в комнате Microsoft Teams или при использовании дисплея Microsoft Teams. Чтобы быстро общаться с командой без рук и в путь, пользователи могут делать запросы, например &#8220;позвонить&#8221; или &#8220;отправить сообщение на мое следующее собрание&#8221;. Пользователи также могут присоединиться к собранию, &#8220;присоединиться к следующему собранию и&#8221; использовать голосовую помощь для обмена файлами, проверки календаря и многого другого. Эти голосовые помощники оказания услуг, которые полностью соответствуют требованиям конфиденциальности, безопасности и соответствия требованиям Office 365, отражаются в Условиях использования [веб-служб](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

На изображении показана отправка чата с помощью Кортаны на мобильном устройстве.

![Последовательность мобильных экранов с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Администрирование и ограничения

Голосовая помощь Кортаны в Teams выполняется с помощью служб, которые полностью соответствуют требованиям конфиденциальности, безопасности и соответствия требованиям Office 365, как это отражается в Условиях использования веб-служб (OST). Эта функция будет включена по умолчанию для клиентов.

Администраторы клиентов могут управлять тем, кто в клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy). Эту политику можно настроить как на уровне учетной записи пользователя, так и на уровне клиента. Администраторы могут использовать поле CortanaVoiceInvocationMode в этом средстве управления политикой, чтобы определить, отключена ли Кортана, включена ли она только при нажатии кнопки или при подавке wake word (применимо к устройствам, которые ее поддерживают, например, интерфейс Microsoft Teams).

Администраторы могут использовать для управления этой политикой следующие командлеты PowerShell (в настоящее время политика недоступна в Центре администрирования Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Например, с помощью приведенной ниже команды создается новая политика с именем &#8220;EmployeeCortanaPolicy&#8221; где отключена голосовая помощь Кортаны в Microsoft Teams.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

В этом примере показано обновление существующей политики с использованием имен &#8220;EmployeeCortanaPolicy&#8221; и включение голосовой помощи Кортаны в Microsoft Teams с помощью кнопки вызова. Пользователи смогут вызвать Кортану, нажав кнопку микрофона Кортаны в Teams. Пробуждает слово (&#8220;"Привет, Кортана&#8221;" или &#8220;Кортана&#8221;) будет отключена.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

В этом примере показано обновление политики и включение голосовой помощи Кортаны с помощью кнопки и вызова word.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

На момент первоначального выпуска для пользователей Microsoft 365 корпоративный в США на английском языке доступны следующие функции:

- Мобильное приложение Teams не поддерживает активацию Word, но в будущем оно будет поддерживаться.  

- Комнаты Microsoft Teams в Windows и Microsoft Teams поддерживают активацию Word.

## <a name="user-control"></a>Контроль пользователей

Отдельные пользователи могут попробовать голосовую помощь Кортаны на разных устройствах:

- В мобильном приложении Teams выберите кнопку "Микрофон".

- В комнатах Microsoft Teams выберите кнопку микрофона или скажите "Кортана".

- Скажите "Кортана" в Microsoft Teams для отображения устройств.

Вы можете управлять тем, включена ли Кортана в Teams для вашего устройства, с помощью параметра устройства.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Мобильное приложение Teams или отображение Microsoft Teams

  1. Откройте мобильное приложение Teams.

  2. Выберите **"Параметры**  >  **Кортаны".**

  3. Включите или **выключите** **его.**

### <a name="microsoft-teams-display"></a>Отображение Microsoft Teams

  1. Перейдите на экран окружающего (домашнего) экрана Microsoft Teams.

  2. Выберите аватар пользователя, а затем — **"Параметры".** Если Кортана включена, скажите "Кортана, перейдите в "Параметры".

  3. Включите или **выключите** **его.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Комнаты Microsoft Teams в Windows

Внесение изменений на уровне устройства доступно, если Кортана включена на уровне клиента. Кортана будет выключена по умолчанию.

Чтобы включить Кортану на уровне устройства, в XML-файл SkypeSettings необходимо добавить указанные ниже XML-атрибуты.

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Внесение изменений на уровне собрания доступно, если Кортана включена на уровне устройства.

Чтобы включить голосовую поддержку Кортаны во время  собрания, переместите или выключите **ее.** После окончания собрания Кортана возвращается к установленным настройкам уровня устройства.

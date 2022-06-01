---
title: Изменение настроек для моста аудиоконференций
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Измените параметры моста аудиоконференций, включая уведомления о входе и выходе, имена воспроизведения или номера телефонов, звуковые сигналы и запрос на запись их имени.
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823048"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Изменение настроек для моста аудиоконференций

При настройке Аудиоконференции в Microsoft 365 или Office 365 вы получите номера телефонов для пользователей из так называемого моста аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров. Эти номера телефонов используются при входе абонентов на собрание. Номер телефона включается в нижнюю часть Skype для бизнеса или Microsoft Teams приглашения на собрание.
  
Мост конференц-связи отвечает на звонок и запрашивает у вызывающего абонента голосовые запросы с помощью автосекретаря собрания, а затем, в зависимости от параметров, может воспроизводить уведомления, запрашивать у абонентов запись имени и управлять параметрами ПИН-кода. Пин-коды перечислены организаторам собраний, чтобы разрешить им начинать собрание, если они не используют Skype для бизнеса или Microsoft Teams приложения.

  > [!IMPORTANT]
  > ПИН-код требуется только для организатора собрания, Skype для бизнеса или Microsoft Teams еще не начал собрание. Если все абоненты впускаются на собрание, для начала собрания организатору собрания требуется ПИН-код.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации перейдите к **мостам конференций собраний** > .

2. В верхней части страницы " **Мосты** конференций" щелкните **"Параметры моста"**.

3. В области **параметров моста** выберите:
   - **Уведомления о входе и выходе из собрания** Если вы отключите эту функцию, пользователи, которые уже присоединились к собранию, не будут получать уведомления, когда кто-то входит в собрание или покидает его.

     При включении **уведомлений о входе и выходе** из собрания можно выбрать следующие параметры:

   - **Имена или номера телефонов** Когда пользователи присоединяются к собранию, при присоединении к собранию будет воспроизводиться их номер телефона.

   - **Тонах** Когда пользователи присоединяются к собранию, при присоединении к собранию будет воспроизводиться звуковой сигнал.

   - **Попросите абонентов записать свое имя перед присоединением к собранию** Если отключить эту функцию, абонентам не будет предложено записать свое имя перед присоединением к собранию.

4. Чтобы задать длину ПИН-кода для собраний, выберите нужное число цифр в списке длины **ПИН-кода** .

5. Чтобы указать, следует ли отправлять пользователям электронную почту, включите или отключите автоматическую отправку сообщений электронной почты пользователям при изменении конфигурации **аудиоконференций**.
    [Дополнительные сведения](emails-sent-to-users-when-their-settings-change-in-teams.md) см. в сообщениях электронной почты, автоматически отправляемых пользователям при изменении параметров Аудиоконференции в Microsoft Teams или сообщениях электронной почты, отправляемых пользователям при изменении их параметров в [Skype для бизнеса Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change).

6. Нажмите кнопку **Сохранить**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время или автоматизировать этот процесс, можно использовать командлет [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) .

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell имеет множество преимуществ в скорости, простоте и производительности по сравнению с использованием только Центр администрирования Microsoft 365, например при одновременном изменении параметров для многих пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1).
  
## <a name="related-topics"></a>См. также

[Настройка аудиоконференций для Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Настройка Аудиоконференции для Skype для бизнеса Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

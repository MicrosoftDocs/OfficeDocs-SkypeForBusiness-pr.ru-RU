---
title: Изменение настроек для моста аудиоконференций
ms.author: tonysmit
author: tonysmit
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
description: Изменение параметров моста аудиоконференций, включая уведомления о входе и выходе, воспроизведения имен и номеров телефонов, тонов и запрос на запись имени.
ms.openlocfilehash: 434142eb0e7d8cd4759eec180e903eaecad47525
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607856"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Изменение настроек для моста аудиоконференций

При настройке аудиоконференций в Microsoft 365 или Office 365 вы будете получать телефонные номера пользователей от так называемого моста аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров. Эти номера телефонов используются, когда звонят на собрание по телефону. Номер телефона будет включен в нижнюю часть Skype для бизнеса или Microsoft Teams приглашения на собрание.
  
Мост для проведения собраний отвечает на звонок и выводит звоняку голосовые подсказки с помощью автозавершена, а затем (в зависимости от параметров) может получать уведомления, просить звонив записывать свое имя и управлять настройками ПИН-кода. ПИН-ны даются организаторам собраний, чтобы они могли начинать собрания, если они не используют Skype для бизнеса или Microsoft Teams приложение.

  > [!IMPORTANT]
  > ПИН-код требуется только организатору собрания, Skype для бизнеса или Microsoft Teams еще не начал собрание. Если кто-то звонит на собрание, организатору собрания требуется ПИН-код, чтобы начать собрание. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. В левой области навигации перейдите к **мосту Конференц-связь**  >  **собраний**. 

2. В верхней части страницы Мост **конференции** щелкните **Параметры моста**. 

3. В области **Параметры моста** выберите: 
   - **Уведомления о входе и выходе из собрания** Если отключить эту возможность, пользователи, которые уже присоединились к собранию, не будут уведомлены о том, что кто-то входит в собрание или покидает его.
    
     Включив уведомления о **входе и выходе** из собрания, вы можете выбрать указанные здесь параметры.
    
   - **Имена или номера телефонов** Когда пользователь присоединяется к собранию по телефону, его номер телефона будет разыт.
    
   - **Тоны** Когда пользователи присоединяются к собранию по телефонной сети, при их подзвучит звуковой сигнал.
      
   - **Попросите звоняющих записать свое имя перед присоединением к собранию** Если отключить эту возможность, перед тем как присоединяться к собранию, вызывателям не будет предложено записать свое имя.

4. Чтобы установить длину ПИН-кода для собраний, в списке Длина  ПИН-кода выберите нужное число цифр.

5. Чтобы указать, отправлять ли пользователям электронную почту, включите или отключите функцию Автоматическое отправка сообщений пользователям в случае изменения конфигурации **аудиоконференции.**
    Дополнительные сведения см. в сообщениях электронной почты, которые автоматически отправляются пользователям при изменении их параметров аудиоконференции в Microsoft Teams или Сообщения электронной почты, отправленные пользователям при изменении их параметров в [Skype для бизнеса Online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) [](emails-sent-to-users-when-their-settings-change-in-teams.md)
 
6. Нажмите кнопку **Сохранить**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время или автоматизировать этот процесс, можно использовать [cmdlet Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Настройка аудиоконференций для Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Настройка аудиоконференций для Skype для бизнеса Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
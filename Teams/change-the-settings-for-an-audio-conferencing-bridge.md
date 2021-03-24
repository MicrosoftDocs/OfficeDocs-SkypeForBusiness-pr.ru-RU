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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Изменение параметров моста аудиоконференций, включая уведомления о входе и выходе, воспроизведения имен и номеров телефонов, мелодии звука и запрос на запись имени.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102646"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Изменение настроек для моста аудиоконференций

При настройке аудиоконференций в Microsoft 365 или Office 365 вы будете получать номера телефонов пользователей с моста аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров. Эти номера телефонов используются для звонков на собрание. Номер телефона будет включен в нижнюю часть приглашения на собрание Skype для бизнеса или Microsoft Teams.
  
Мост для conferencing отвечает на звонок и просит вызывающего человека голосовые подсказки с помощью автозавершенного помощника, а затем в зависимости от параметров может играть в уведомления, просить вызывающего человека записать свое имя и управлять настройками ПИН-кода. ПИН-записи даются организаторам собраний, чтобы они могли начинать собрания, если они не используют приложение Skype для бизнеса или Microsoft Teams.

  > [!IMPORTANT]
  > ПИН-код требуется только организатору собрания, если пользователь приложения Skype для бизнеса или Microsoft Teams еще не начал собрание. Если кто-то звонит на собрание, организатору собрания необходим ПИН-код, чтобы начать собрание. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к мостам  >  **конференц-залов собраний.** 

2. В верхней части страницы **"Конференц-мосты"** нажмите кнопку **"Параметры моста".** 

3. В области **параметров моста** выберите: 
   - **Уведомления о входе и выходе из собрания** Если отключить эту возможность, пользователи, уже присоединившиеся к собранию, не будут уведомлены о том, что кто-то присоединился к собранию или покинул его.
    
     Включив уведомления **о входе и выходе** из собрания, вы можете выбрать указанные здесь параметры.
    
   - **Имена или номера телефонов** Когда пользователи присоединяются к собранию по телефону, их номера телефонов будут играть, когда они присоединятся к нему.
    
   - **Мелодии** Когда пользователи присоединяются к собранию по телефонной сети, при его подзвучии звуковой сигнал будет разыт.
      
   - **Попросите звоняющих записать свое имя перед присоединением к собранию** Если отключить эту возможность, то перед тем как присоединяться к собранию, не будет предложено записывать свое имя.

4. Чтобы установить длину ПИН-кода для собраний, выберите нужное количество цифр в списке длины **ПИН-кода.**

5. Чтобы указать, нужно ли отправлять пользователям электронную почту, включите или отключите функцию автоматической отправки электронных писем пользователям в случае изменения конфигурации **аудиоконференции.**
    Дополнительные сведения см. в сообщениях электронной почты, которые автоматически отправляются пользователям при изменении настроек аудиоконференции в [Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) или сообщений электронной почты, отправленных пользователям при изменении их параметров в Skype для бизнеса [Online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)
 
6. Нажмите кнопку **Сохранить**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Чтобы сэкономить время и автоматизировать этот процесс, можно воспользоваться [cmdlet Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Статьи по теме

[Настройка аудиоконференций для Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Настройка аудиоконференций в Skype для бизнеса Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
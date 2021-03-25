---
title: Начало аудиоконференции по телефону без ПИН-кода в Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Узнайте, как включить или отключить присоединение анонимных звонков к собранию из Центра администрирования Teams. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116967"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Начало аудиоконференции по телефону без ПИН-кода в Microsoft Teams

Пользователи, которые могут звонить на собрание по телефонной связи, могут слушать музыку в "вестибюле" собрания, так как организатор собрания Microsoft Teams не начал собрание. 
  
Если организатор собрания звонит на собрание, по умолчанию для его начала требуется ПИН-код. Вы можете настроить его таким образом, чтобы любой человек мог позвонить на собрание, а пин-код не выводиться, чтобы начать собрание. С помощью Центра администрирования можно включить или отключить этот параметр для одного пользователя.
  
ПИН-код не требуется организатору собрания, если кто-то начал собрание из приложения Microsoft Teams. ПИН-код требуется только в том случае, если организатор собрания присоединяется к собранию по телефону. ПИН-код для собраний отправляется пользователю, когда  ему назначена лицензия на аудиоконференцию и для них включена аудиоконференция. См. [статью](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) "Отправка пользователю сообщения электронной почты с информацией об аудиоконференции и электронными письмами, которые автоматически отправляются пользователям при изменении параметров аудиоконференции". [](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Разрешение и запрет присоединения анонимных абонентов к собранию

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В области навигации слева выберите **"Пользователи".** 

2. Выберите пользователя в списке и  нажмите кнопку "Изменить" в верхней части страницы. 

3. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

4. В области **аудиоконференций** включите или отключите функцию телефонного звонка, включив или отключив звонок на собрание.
    
4. Нажмите кнопку **Применить**. 

**Использование Windows PowerShell**
  
Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Дополнительные сведения

- Если вы хотите сбросить [](reset-the-audio-conferencing-pin-in-teams.md)ПИН-код, см. его.
    
- Если анонимный доступ или требование ПИН-кода для начала собрания отключено:
    
  - Если собрание не началось (в собрании пока нет ни одного организатора), вызываемому звоня будет предложено, является ли он организатором; Если он отвечает "да", ему будет предложено ввести ПИН-код, а после ввода ПИН-кода начнется собрание, и пользователь присоединится к нему.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.
    
- Если включен анонимный доступ или не требуется ПИН-код для начала собрания:
    
  - Если собрание еще не началось (никто не присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Так как параметр организатора отключен, собрание начнется, и анонимные звоняки присоединятся к нему.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Связанные разделы

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
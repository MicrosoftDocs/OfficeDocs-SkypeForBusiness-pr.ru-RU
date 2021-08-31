---
title: Запуск аудиоконференции по телефону без ПИН-кода в Teams
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Узнайте, как включить или отключить присоединение анонимных звонков к собранию из Teams администрирования. '
ms.openlocfilehash: 5a2abd84514e46a19f3f698650d3acf1ec931410
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732748"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Начало аудиоконференции по телефону без ПИН-кода в Microsoft Teams

Пользователям, которые будут проходить собрание по телефонной связи, может быть сложно слушать музыку в "Microsoft Teams, так как организатор собрания еще не начал собрание. 
  
Если организатор собрания звонит на собрание, по умолчанию для начала собрания требуется ПИН-код. Вы можете настроить его таким образом, чтобы любой человек мог звонить на собрание, а пин-код не выводиться для начала собрания. С помощью Центра администрирования можно включить или отключить этот параметр для одного пользователя.
  
ПИН-код не требуется организатору собрания, если кто-то начал собрание из Microsoft Teams приложения. ПИН-код требуется только в том случае, если организатор собрания присоединяется к собранию по телефону. ПИН-код для собраний отправляется пользователю аудиоконференции, если ему назначена лицензия на аудиоконференцию и включена аудиоконференция.  [См.](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) статью Отправка электронной почты пользователю со сведениями об аудиоконференциях и Электронные письма, которые автоматически отправляются пользователям при изменении их параметров аудиоконференции. [](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Разрешение и запрет присоединения анонимных абонентов к собранию

![Значок с логотипом Microsoft Teams.](media/teams-logo-30x30.png) **С помощью Центра администрирования Microsoft Teams**

1. В области навигации слева щелкните **Пользователи**. 

2. Выберите пользователя в списке и нажмите кнопку **Изменить** в верхней части страницы. 

3. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

4. В области **Аудиоконференция** включите или отключите вызывающих телефонную звонок может быть первым лицом на **собрании**.
    
4. Нажмите кнопку **Применить**. 

**Использование Windows PowerShell**
  
Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-else-should-you-know"></a>Дополнительные сведения

- Если вы хотите сбросить ПИН-код, см. сброс ПИН-кода [аудиоконференции.](reset-the-audio-conferencing-pin-in-teams.md)
    
- Если анонимный доступ или требование ПИН-кода для начала собрания отключено:
    
  - Если собрание еще не началось (в собрании пока нет ни одного из них), вызываемой будет предложено, является ли он организатором; Если он даст ответ "Да", ему будет предложено ввести ПИН-код, а после ввода ПИН-кода начнется собрание, и пользователь присоединится к собранию.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.
    
- Если включен анонимный доступ или не требуется ПИН-код для начала собрания:
    
  - Если собрание еще не началось (никто не присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Так как параметр организатора отключен, собрание начнется, и анонимные звонители присоединятся к собранию.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Связанные разделы

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
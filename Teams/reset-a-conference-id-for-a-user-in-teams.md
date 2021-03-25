---
title: Сброс идентификатора конференции для пользователя в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: Узнайте, как сбросить ИД конференции пользователя в Microsoft Teams и получить ссылки на средства обновления собраний и миграции.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117647"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Сброс идентификатора конференции для пользователя в Microsoft Teams

Динамический ИД конференции содержится в нижней части приглашений на собрание, а также номера телефонов для телефонного звонка, которые могут использоваться звонителями для звонков на собрание. Когда пользователь наберет номер телефона, автозаводщик собрания попросит вызывающего пользователя ввести этот номер конференции, чтобы он принял участие в собрании.
  
> [!NOTE]
> Коды конференций создаются автоматически, от 7 до 9 цифр и задаются при включке аудиоконференции для пользователя. **Статические ИД конференции не поддерживаются.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Сброс ИД конференции для пользователя

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В области навигации слева **щелкните**"Пользователи" и выберите пользователя в списке доступных пользователей.

2. Нажмите **кнопку "Изменить".**

3. В **области аудиоконференции нажмите** кнопку **"Сбросить ИД конференции".**

2. В **окне "Сброс ИД конференции"** нажмите кнопку **"Сброс".** A conference ID will be automatically created and an email sent to the user with the new conference ID. По умолчанию электронные письма отправляются пользователям, но это можно отключить.   

    
> [!NOTE]
> После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. Во многих случаях это сообщение электронной почты отправляется на основной адрес электронной почты их почтового ящика Microsoft 365 или Office 365. Сообщение электронной почты содержит новый ИД конференции, номера телефонов для телефонного звонка по умолчанию и инструкции по обновлению существующих собраний. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Дополнительные сведения

- Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и  номера телефонов для телефонного  звонка, нажав кнопку "Отправить сведения о конференции" по электронной почте для пользователя в разделе "Аудиоконференции". ПИН-код не отправляется.
    
- Код конференции из 7–9 цифр создается службой Teams. Его длину изменить нельзя.
    
- После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.
    
- После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Связанные разделы

[Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md)
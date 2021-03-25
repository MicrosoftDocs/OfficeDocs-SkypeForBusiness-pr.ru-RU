---
title: Просмотр, изменение и сброс ИД конференции пользователя
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: Узнайте, как назначить пользователю в Microsoft Teams ИД конференции и какие параметры должны быть заданы.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117212"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Просмотр и сброс назначенного пользователю ИД конференции в Microsoft Teams

Когда пользователь Microsoft Teams настроил аудиоконференцию в Microsoft 365 или Office 365 и в качестве поставщика услуг аудиоконференции использует Майкрософт, пользователь автоматически получает соответствующий ИД. Присвоенный ему ИД конференции отправляется в приглашении на собрание при его запланированном собрании. Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции. 
  
Хотя пользовательский ИД конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать этот номер и хочет установить для него определенный номер, а также когда пользователи не могут вспомнить или потеряли свой ИД конференции. Вы можете использовать Центр администрирования Microsoft Teams или Windows PowerShell для просмотра, изменения и сброса их ИД конференции.
  
Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код. Дополнительные [сведения о сбросе ПИН-кода](reset-a-conference-id-for-a-user-in-teams.md) организатора конференции см. в сведениях о сбросе пользователем кода конференции в Microsoft Teams. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Просмотр и сброс идентификатора конференции

### <a name="to-view-the-conference-id"></a>Просмотр ИД конференции

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В области навигации слева **щелкните**"Пользователи" и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы нажмите кнопку **"Изменить".**

3. В **области "Аудиоконференции" посмотрите** на **ИД конференции.**

    > [!TIP]
    > Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и номера аудиоконференции, щелкнув ссылку "Отправить сведения о конференции" по электронной **почте.**
  
**Использование Windows PowerShell**

Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)
    
  
### <a name="to-reset-the-conference-id"></a>Сброс ИД конференции

Если, например, пользователь забыл идентификатор конференции, его можно сбросить.
  
![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В области навигации слева **щелкните**"Пользователи" и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы нажмите кнопку **"Изменить".**

3. В **области аудиоконференции нажмите** кнопку **"Сбросить ИД конференции".**

4. В **окне "Сброс ИД конференции"** нажмите кнопку **"Сброс".** A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Использование Windows PowerShell**

Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)


## <a name="what-else-should-you-know"></a>Дополнительные сведения

   > [!IMPORTANT]
   >  После создания нового или сброса нового ИД конференции звоня не смогут использовать старый. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 
  
    
- Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции. В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Связанные разделы

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
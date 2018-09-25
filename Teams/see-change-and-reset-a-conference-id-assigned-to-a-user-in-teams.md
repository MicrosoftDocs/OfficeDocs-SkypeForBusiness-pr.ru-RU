---
title: Просмотр, изменение и сброс назначенного пользователю идентификатора конференции в Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, как назначить идентификатор конференции пользователю в Microsoft Teams и какими должны быть его параметры. '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017087"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Просмотр и сброс назначенного пользователю идентификатора конференции в Microsoft Teams

Идентификатор конференц-связь автоматически назначается пользователю группами Майкрософт, если они зависят от выбора звукового конференц-связи в Office 365 и использовать Microsoft в качестве поставщика аудиоконференций. Идентификатор конференции, назначенный отправляется в приглашении на собрание, при планировании собрания. Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции. 
  
Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или при пользователи не могут не забудьте или теряют их идентификатор конференции. Центр администрирования группами Майкрософт или Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.
  
Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код. Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user-in-teams.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Просмотр и сброс идентификатора конференции

### <a name="to-view-the-conference-id"></a>Просмотр идентификатора конференции

![teams-logo-30x30.png](media/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**

1. В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы щелкните на элементе **Изменить**.

3. В области **Аудиоконференции** просмотрите значение **Идентификатор конференции**.

    > [!TIP]
    > Всю информацию о конференц-связи, включая идентификатор конференции и телефонные номера для аудиоконференции, можно отправить пользователю по электронной почте, щелкнув ссылку **Отправить сведения о конференции по эл. почте**.
  
**Использование Windows PowerShell**

Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
### <a name="to-reset-the-conference-id"></a>Сброс идентификатора конференции

вы можете сбросить идентификатор конференции для пользователя, например, если он забыл его.
  
![teams-logo-30x30.png](media/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**

1. В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.

2. В верхней части страницы щелкните на элементе **Изменить**.

3. В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.

4. В окне **сбросить идентификатор конференции** нажмите кнопку **Сброс**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Использование Windows PowerShell**

Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="what-else-should-you-know"></a>Что еще вам нужно знать?

   > [!IMPORTANT]
   >  После создания новый идентификатор или один сбрасывается, старый идентификатор конференции не может использоваться с абонентов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 
  
    
- Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции. В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.
    
- Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Связанные разделы

[Оцените или приобретите аудиоконференции в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)


---
title: Просмотр, изменение и сброс идентификатора конференции пользователя
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Узнайте, как назначить идентификатор конференции пользователю в Microsoft Teams и какими должны быть параметры идентификаторов конференции.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642120"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Просмотр и сброс идентификатора конференции, назначенного пользователю в Microsoft Teams

Идентификатор конференции автоматически назначается пользователю Microsoft Teams, если он настроен для аудиоконференций в Microsoft 365 или Office 365 и использует Майкрософт в качестве поставщика аудиоконференций. Назначенный идентификатор конференции отправляется в приглашении на собрание, когда собрание запланировано. Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.
  
Несмотря на то, что идентификатор конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать его и вы хотите задать для него определенное число, или когда пользователи не могут запомнить или потерять свой идентификатор конференции. Вы можете использовать Центр администрирования Microsoft Teams или Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.
  
Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код. Дополнительные сведения о сбросе ПИН-кода организатора конференции см. в статье "Сброс идентификатора конференции для пользователя [в Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) ".

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Просмотр и сброс идентификатора конференции

### <a name="to-view-the-conference-id"></a>Просмотр идентификатора конференции

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Просмотр идентификатора конференции с помощью Центра администрирования Microsoft Teams

1. В области навигации слева **щелкните "** Пользователи", а затем выберите пользователя из списка доступных пользователей.

2. В верхней части страницы нажмите кнопку "Изменить **"**.

3. В **разделе "Аудиоконференции**" просмотрите идентификатор **конференции**.

    > [!TIP]
    > Все сведения о конференции можно отправить пользователю в сообщении электронной почты с идентификатором конференции и номерами телефонов, щелкнув ссылку "Отправить сведения о конференции **".**
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Просмотр идентификатора конференции с помощью Windows PowerShell

Дополнительные сведения см. в справочнике [по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

### <a name="to-reset-the-conference-id"></a>Сброс идентификатора конференции

Если, например, пользователь забыл идентификатор конференции, его можно сбросить.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Сброс идентификатора конференции с помощью Центра администрирования Microsoft Teams

1. В области навигации слева **щелкните "** Пользователи", а затем выберите пользователя из списка доступных пользователей.

2. В верхней части страницы нажмите кнопку "Изменить **"**.

3. В **разделе "Аудиоконференции" нажмите** кнопку **"Сбросить идентификатор конференции"**.

4. В **окне сброса идентификатора конференции** нажмите кнопку **"Сбросить"**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Сброс идентификатора конференции с помощью Windows PowerShell

Дополнительные сведения см. в справочнике [по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Дополнительные сведения

> [!IMPORTANT]
> После создания или сброса нового идентификатора конференции старый идентификатор конференции не может использоваться вызывающими абонентами. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.

- Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции. В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Связанные разделы

[Попробуйте или приобретите аудиоконференции в Microsoft 365 для Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)

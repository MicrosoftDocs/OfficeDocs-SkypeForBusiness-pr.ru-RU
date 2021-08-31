---
title: Просмотр, изменение и сброс назначенного пользователю ИД конференции в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как присвоить пользователю идентификатор конференции для Skype для бизнеса Online и какими должны быть параметры для установки идентификатора конференции. '
ms.openlocfilehash: a400536050ea22d4f841e3b401e30c3c14729093
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728008"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Сведения об ИД конференции пользователей в Microsoft Teams см. в этой [Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Когда пользователь Skype для бизнеса аудиоконференцию в Microsoft 365 или Office 365 и использует Майкрософт в качестве поставщика услуг аудиоконференций, пользователю автоматически Microsoft 365 или Office 365. Присвоенный ему ИД конференции отправляется в приглашении на собрание при его запланированном собрании. Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.

Хотя ИД конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать этот номер и хочет установить определенное число, или пользователи не могут вспомнить или потеряли свой ИД конференции.  **Войдите в административную панель Skype для бизнеса** и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.

Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код. Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Просмотр и сброс идентификатора конференции

### <a name="to-view-the-conference-id"></a>Просмотр ИД конференции

![Значок с логотипом Skype для бизнеса.](../images/sfb-logo-30x30.png) **Использование центра Skype для бизнеса администрирования**

Вы можете посмотреть их идентификатор конференции и отправить его пользователям.

1. Во войти с помощью своей учебной или учебной учетной записи.

2. Перейдите в центр администрирования > **Skype для бизнеса**.

3. В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.

4. На странице "Действия" найдите раздел **Идентификатор конференции**.

    > [!TIP]
    > Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД  и номера телефонов для аудиоконференции, щелкнув ссылку Отправить сведения о конференции по электронной почте после выбора пользователя на странице Пользователи. 

**Использование Windows PowerShell**

Windows PowerShell может быть использован для просмотра пользовательского идентификатора конференции. Для этого запустите:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Дополнительные информацию о нем см. в окне [Get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)


### <a name="to-reset-the-conference-id"></a>Сброс ИД конференции

Если, например, пользователь забыл идентификатор конференции, его можно сбросить.

![Значок с логотипом Skype для бизнеса.](../images/sfb-logo-30x30.png) **Использование центра Skype для бизнеса администрирования**

1. Во войти с помощью своей учебной или учебной учетной записи.

2. Перейдите в центр администрирования > **Skype для бизнеса**.

3. В центре **Skype для бизнеса** аудиоконференции Пользователи , в области действий в области "ИД конференции" >    >  нажмите кнопку **Сброс**. 

4. В **окне Сбросить ИД конференции?** нажмите кнопку **Да.** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Использование Windows PowerShell**

Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell. Для этого выполните команду:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Дополнительные сведения

   > [!IMPORTANT]
   >  После создания нового ИД конференции или сброса его старый ИД конференции нельзя использовать для вызывающих вызовов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Пользователи могут использовать средство переноса Skype для бизнеса для обновления существующих собраний. Чтобы узнать, как скачать, установить и запустить средство, см. средства обновления собраний для Skype для бизнеса и [Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype для бизнеса Online, Средство переноса собраний [(64-битная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и Skype для бизнеса Online, Средство переноса собраний [(32-битная версия).](https://www.microsoft.com/download/details.aspx?id=54079)

- See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.

- Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции. В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.

- По умолчанию код конференции для всех пользователей аудиоконференции состоит из 9 цифр, а количество цифр изменить нельзя.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

---
title: Просмотр, изменение и сброс назначенного пользователю конференц-зала в Skype для бизнеса Online
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как присвоить пользователю идентификатор конференции для Skype для бизнеса Online и какими должны быть параметры для установки идентификатора конференции. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643609"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online

> [!Note]
> Сведения об пользовательских ИД конференц-связи в Microsoft Teams см. в документе "Просмотр и сброс ИД конференции,назначенного [пользователю" в Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Когда пользователь настроил аудиоконференцию в Microsoft 365 или Office 365 и в качестве поставщика услуг аудиоконференции, пользователю Skype для бизнеса автоматически будет назначен соответствующий номер. При этом назначенная конференция отправляется в приглашении на собрание. Каждому собранию, которое должен назначить пользователь, будет назначен уникальный ИД конференции.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Просмотр и сброс идентификатора конференции

### <a name="to-view-the-conference-id"></a>Просмотр ИД конференции

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

Вы можете посмотреть их идентификатор конференции и отправить его пользователям.

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.

4. На странице "Действия" найдите раздел **Идентификатор конференции**.

    > [!TIP]
    > Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД  и номера телефонов для аудиосвязи,  щелкнув ссылку "Отправить сведения о конференции" по электронной почте после выбора пользователя на странице "Пользователи".

**Использование Windows PowerShell**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Дополнительные [информацию о cmdlet см. в get-CsOnlineDialInConferencingUser.](https://go.microsoft.com/fwlink/?LinkId=617693 )


### <a name="to-reset-the-conference-id"></a>Сброс ИД конференции

Если, например, пользователь забыл идентификатор конференции, его можно сбросить.

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

1. Войте свою учетную запись с помощью своей учебной или учебной учетной записи.

2. Перейдите в Центр администрирования > **Skype для бизнеса.**

3. В Центре **администрирования Skype** для бизнеса для пользователей аудиоконференции в области действий в области "ИД конференции" нажмите кнопку >    >    **"Сброс".**

4. В **окне "Сбросить ИД конференции?"** нажмите кнопку **"Да".** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Использование Windows PowerShell**

Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell. Для этого выполните команду:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Дополнительные сведения

   > [!IMPORTANT]
   >  После создания нового или сброса нового ИД конференции звоня не смогут использовать старый. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Пользователи могут использовать средство переноса собраний Skype для бизнеса для обновления существующих собраний. Чтобы узнать, как скачать, установить и запустить средство, см. :Средство обновления собраний для Skype для бизнеса и [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype для бизнеса Online, средство переноса собраний [(64-битная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и Skype для бизнеса Online, средство переноса собраний [(32-битная версия).](https://www.microsoft.com/download/details.aspx?id=54079)

- See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.

- Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции. В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.

- По умолчанию всем пользователям аудиоконференции будет присвоено 9 цифр, а количество цифр изменить нельзя.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


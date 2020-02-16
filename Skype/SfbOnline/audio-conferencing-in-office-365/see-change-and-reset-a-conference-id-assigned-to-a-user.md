---
title: Просмотр, изменение и сброс идентификатора конференц-связи, назначенного пользователю в Skype для бизнеса Online
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
ms.openlocfilehash: 8bec76e25df092beb18725467c3041de3c1d7745
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010992"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online

> [!Note]
> Сведения об идентификаторах конференций пользователей в Microsoft Teams можно найти в разделе [Просмотр и сброс идентификатора конференц-связи, назначенного пользователю в Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Просмотр и сброс идентификатора конференции

### <a name="to-view-the-conference-id"></a>Просмотр идентификатора конференции

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

Вы можете посмотреть их идентификатор конференции и отправить его пользователям.

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в центр администрирования > **Skype для бизнеса**.

3. В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.

4. На странице "Действия" найдите раздел **Идентификатор конференции**.

    > [!TIP]
    > Вы можете отправить всем сведения о конференциях в сообщение электронной почты, которое содержит идентификатор конференции и звуковые номера, нажав кнопку **отправить сведения о конференции по электронной почте** , после того как вы выберете пользователя на странице **Пользователи** .

**Использование Windows PowerShell**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Чтобы узнать больше о командлете, ознакомьтесь со [статьей Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) .


### <a name="to-reset-the-conference-id"></a>Сброс идентификатора конференции

Если, например, пользователь забыл идентификатор конференции, его можно сбросить.

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

1. Войдите в Office 365 под своей учебной или рабочей учетной записью.

2. Перейдите в центр администрирования > **Skype для бизнеса**.

3. В> **** центре >  **администрирования Skype для бизнеса**, в разделе " **идентификатор конференции****", в**области "действия" нажмите кнопку **Сброс**.

4. В окне **Сброс ИД конференции?** нажмите кнопку **Да**. A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Использование Windows PowerShell**

Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell. Для этого выполните команду:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Дополнительные сведения

   > [!IMPORTANT]
   >  После создания нового идентификатора конференции или сброса номера старый идентификатор конференции нельзя использовать для вызывающих сторон. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Пользователи могут использовать средство миграции собраний Skype для бизнеса для обновления существующих собраний. Сведения о том, как скачать, установить и запустить средство, можно найти в [статье: средство обновления собраний для Skype для бизнеса и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype для бизнеса Online, инструмент переноса собраний (64-разрядная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и [Skype для бизнеса Online, средство миграции собраний (32-разр.)](https://www.microsoft.com/download/details.aspx?id=54079).

- See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.

- Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции. В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.

- Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.

  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>См. также

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)


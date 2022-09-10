---
title: Электронные письма, отправляемые пользователям при изменении параметров
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
- seo-marvel-mar2020
description: 'Сведения о том, какие сведения автоматически отправляются пользователям по электронной почте при изменении параметров конференц-связи с телефонным подключением в Microsoft Teams. '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642140"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams

Сообщения электронной почты будут автоматически отправляться пользователям, [](set-up-audio-conferencing-in-teams.md) для которых включена аудиоконференции с помощью Майкрософт в качестве поставщика аудиоконференций.

По умолчанию существует четыре типа сообщений электронной почты, которые будут отправляться пользователям, для которых включена аудиоконференции. Однако если вы хотите ограничить количество отправленных пользователям сообщений электронной почты, его можно отключить. Аудиоконференции в Microsoft 365 или Office 365 будут отправлять сообщения электронной почты пользователей в следующих случаях:

- **Им назначается лицензия на аудиоконференции или при изменении поставщика аудиоконференций на Майкрософт.**

     Это сообщение электронной почты содержит идентификатор конференции, номер телефона конференции по умолчанию для собраний, ПИН-код аудиоконференций для пользователя, а также инструкции и ссылку для использования средства обновления собраний Teams, которое используется для обновления существующих собраний для пользователя. См [. раздел "Назначение лицензий на надстройки Microsoft Teams"](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Если в вашей организации включены динамические идентификаторы конференций, все собрания пользователя, которые они запланирует, будут иметь уникальные идентификаторы конференций. Дополнительные сведения см. в статье "Просмотр и сброс идентификатора конференции, назначенного пользователю в [Microsoft Teams](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) ".

    Ниже приведен пример этого сообщения электронной почты:

     ![Teams Verify License.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Дополнительные сведения о лицензировании см. в разделе " [Лицензирование надстроек Microsoft Teams"](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **Изменяется идентификатор конференции или номер телефона конференции по умолчанию для пользователя.**

    Это сообщение электронной почты содержит идентификатор конференции, номер телефона конференции по умолчанию, а также инструкции и ссылку для использования средства обновления собраний Teams, которое используется для обновления существующих собраний для пользователя. Но это сообщение электронной почты не содержит ПИН-код аудиоконференций пользователя. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    Ниже приведен пример этого сообщения электронной почты:

     ![Изменены сведения о конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Пин-код аудиоконференции пользователя сбрасывается.**

    Это сообщение электронной почты содержит ПИН-код аудиоконференций организатора, существующий идентификатор конференции и номер телефона конференции по умолчанию для пользователя. См [. раздел "Сброс ПИН-кода аудиоконференций"](reset-the-audio-conferencing-pin-in-teams.md).

     Ниже приведен пример этого сообщения электронной почты:

     ![Изменен ПИН-код конференц-связи с телефонным подключением.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Лицензия пользователя удаляется или когда поставщик аудиоконференций изменяется с Майкрософт на другого поставщика или нет.**

    Это происходит **при удалении** лицензии на аудиоконференции у пользователя или при установке для поставщика аудиоконференций значение **None**.

    См [. раздел "Назначение или удаление лицензий для Microsoft 365 для бизнеса"](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Ниже приведен пример этого сообщения электронной почты:

     ![Конференц-связь с телефонным подключением отключена.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Внесение изменений в отправленные им сообщения электронной почты

Вы можете внести изменения в сообщение электронной почты, которое автоматически отправляется пользователям. По умолчанию отправитель сообщений электронной почты будет из Microsoft 365 или Office 365, но вы можете изменить отображаемое имя с помощью Windows PowerShell. Дополнительные сведения см. в справочнике [по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Что делать, если вы не хотите, чтобы им отправляли электронную почту?

Если вы отключите отправку сообщений электронной почты пользователям, они не будут отправляться, даже если пользователю назначена лицензия. В этом случае идентификатор конференции, номер телефона конференц-связи по умолчанию и, что более важно, ПИН-код аудиоконференции не будут отправляться пользователю. В этом случае необходимо сообщить пользователю, отправив ему отдельное сообщение электронной почты или вызвав его.

По умолчанию пользователям будут отправляться сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференций, вы можете использовать Microsoft Teams или Windows PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.

2. В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста"**.

3. В области **параметров моста** включите или отключите автоматическую отправку сообщений электронной почты пользователям, если их параметры **телефонного подключения меняются**.

4. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Использование Windows PowerShell

Вы также можете использовать модуль Microsoft Teams PowerShell и выполнить:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Командлет [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) позволяет управлять другими параметрами организации, включая электронную почту.

Дополнительные сведения см. в справочнике [по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

По умолчанию отправитель сообщений электронной почты будет из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell.

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единой точки администрирования, которая может упростить вашу ежедневную работу при наличии нескольких задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Связанные разделы

[Включение и отключение отправки писем при смене настроек аудиоконференций](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

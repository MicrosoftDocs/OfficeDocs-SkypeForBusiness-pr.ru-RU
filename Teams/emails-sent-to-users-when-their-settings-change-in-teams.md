---
title: Электронные письма, отправляемые пользователям при изменении параметров
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Сведения о том, какие данные автоматически отправляются пользователям по электронной почте при изменении настроек для этой цели в Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120760"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams

Сообщения электронной почты будут автоматически [](set-up-audio-conferencing-in-teams.md) отправляться пользователям, у которых в качестве поставщика услуг аудиоконференции включена аудиоконференция с Майкрософт.

По умолчанию существует четыре типа сообщений электронной почты, которые отправляются пользователям, для которых включена аудиоконференция. Но если вы хотите ограничить количество сообщений, отключите их. Аудиоконференция в Microsoft 365 или Office 365 будет отправлять электронную почту пользователей по электронной почте в том случае, если:

- **Им назначена лицензия на аудиоконференцию или при смене поставщика услуг аудиоконференции на Майкрософт.**

     Это сообщение электронной почты содержит код конференции, номер телефона конференции по умолчанию для собраний, ПИН-код аудиоконференции для пользователя, а также инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое используется для обновления существующих собраний для пользователя. См. ["Назначение лицензий на надстройки Microsoft Teams"](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) или "Назначение Майкрософт в качестве поставщика аудиоконференций". [](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)

    > [!NOTE]
    > Если в вашей организации включены динамические ИД конференц-залов, всем собраниям пользователя, которые он запланил, будут уникальные. Вы можете настроить динамические ИД аудиоконференций [в своей организации.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) 

    Вот пример такого сообщения:

     ![Проверка лицензии Skype для бизнеса](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Дополнительные информацию о лицензировании см. в лицензировании надстройки [Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **Изменяется ИД конференции или телефонный номер конференции по умолчанию пользователя.**

    Это сообщение электронной почты содержит номер конференции, номер телефона конференции по умолчанию, инструкции и ссылку для использования средства обновления собраний Skype для бизнеса Online, которое используется для обновления существующих собраний для пользователя. Но это сообщение электронной почты не содержит ПИН-код аудиоконференции пользователя. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    Вот пример такого сообщения:

     ![Изменены сведения о телефонной телефонной телефонии.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **ПИН-код аудиоконференции пользователя сбрасывается.**

    Это сообщение электронной почты содержит ПИН-код аудиоконференции организатора, существующий код конференции и номер телефона конференции по умолчанию для пользователя. См. ["Сброс ПИН-кода аудиоконференции".](reset-the-audio-conferencing-pin-in-teams.md)
    
     Вот пример такого сообщения:
    
     ![Изменен ПИН-код для телефонной телефонной телефонии.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Лицензия пользователя удаляется или если поставщик услуг аудиоконференций изменяется с Microsoft на другого поставщика или "Нет".**

    Это происходит  при удалении лицензии на аудиоконференцию для пользователя или при установке для поставщика услуг аудиоконференции параметра **"Нет".**

    См. ["Назначение и удаление лицензий для Microsoft 365 для бизнеса".](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    Вот пример такого сообщения:

     ![Conferencing с dial-in отключается.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Внесение изменений в сообщения электронной почты, от которых они отправляются

Вы можете внести изменения в электронные письма, которые автоматически отправляются пользователям. По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить отображаемого имени, используя Windows PowerShell. Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Что делать, если вы не хотите, чтобы им отправляли электронную почту?

Если отключить отправку электронных писем пользователям, сообщения не будут отправляться, даже если пользователю назначена лицензия. В этом случае код конференции, номер телефона для конференц-связи по умолчанию и, что важнее, ПИН-код аудиоконференции не отправляются пользователю. В этом случае вы должны сообщить пользователю, отправив ему отдельный адрес электронной почты или позвонив ему.

По умолчанию пользователям отправляются сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференции, вы можете использовать Microsoft Teams или Windows PowerShell. 

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **"Мосты** конференций" щелкните **"Параметры моста".** 

3. В области **параметров моста** включите или отключите автоматическое отправку электронных писем пользователям в случае изменения **настроек телефонного дозвона.**

4. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**

Дополнительные [сведения см. в справочнике по Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)


## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени, используя Windows PowerShell. 

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Связанные разделы

[Включение и отключение отправки писем при смене настроек аудиоконференций](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
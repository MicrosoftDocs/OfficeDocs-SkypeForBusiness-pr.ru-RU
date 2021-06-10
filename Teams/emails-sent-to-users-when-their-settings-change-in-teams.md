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
description: 'Узнайте, какие сведения автоматически отправляются пользователям по электронной почте при изменении параметров их параметров для Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120760"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Сообщения электронной почты, отправляемые пользователям при изменении их настроек в Microsoft Teams

Сообщения электронной почты автоматически отправляются пользователям, у которых включена аудиоконференция с использованием Майкрософт в качестве поставщика услуг аудиоконференций. [](set-up-audio-conferencing-in-teams.md)

По умолчанию пользователям, для которых включена аудиоконференция, отправляются четыре типа электронной почты. Однако если вы хотите ограничить количество сообщений, отправленных пользователям, вы можете отключить их. Аудиоконференция в Microsoft 365 или Office 365 отправляет электронную почту пользователям в:

- **Им назначена лицензия на аудиоконференцию или при смене поставщика аудиоконференций на Майкрософт.**

     Это сообщение электронной почты содержит код конференции, номер телефона конференции по умолчанию для собраний, ПИН-код аудиоконференции для пользователя, инструкции и ссылку для использования средства обновления собраний по сети Skype для бизнеса, которое используется для обновления существующих собраний для пользователя. См. Microsoft Teams лицензии на [надстройки](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) или Назначение Майкрософт в качестве поставщика аудиоконференций. [](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)

    > [!NOTE]
    > Если в вашей организации включены динамические ИД конференции, у всех собраний пользователя, которые он запланет, будут уникальные. Вы можете настроить [динамические ID](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)аудиоконференции в своей организации. 

    Вот пример такого сообщения:

     ![Skype для бизнеса Проверка лицензии](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Дополнительные информацию о лицензировании см. в Microsoft Teams [лицензировании надстройки.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **Изменяется ИД конференции или телефонный номер конференции по умолчанию пользователя.**

    Это сообщение электронной почты содержит ИД конференции, номер телефона конференции по умолчанию, а также инструкции и ссылку для использования средства обновления собраний по сети Skype для бизнеса, которое используется для обновления существующих собраний для пользователя. Но это сообщение электронной почты не содержит ПИН-код аудиоконференции пользователя. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    Вот пример такого сообщения:

     ![Сведения о телефонном подмене изменены.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Пин-код аудиоконференции пользователя сбрасывается.**

    Это сообщение электронной почты содержит ПИН-код аудиоконференции организатора, существующий код конференции и телефонный номер конференции по умолчанию для пользователя. См. [сброс ПИН-кода аудиоконференции.](reset-the-audio-conferencing-pin-in-teams.md)
    
     Вот пример такого сообщения:
    
     ![Изменен ПИН-код для телефонной телефонии.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Лицензия пользователя удаляется либо поставщик аудиоконферент изменяется с Майкрософт на другого поставщика или нет.**

    Это происходит  при удалении лицензии пользователя на аудиоконференцию или при установке для поставщика услуг аудиоконференции параметра **Нет.**

    См. [назначение и удаление лицензий Microsoft 365 для бизнеса.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    Вот пример такого сообщения:

     ![Conferencing dial-in conferencing is turned off.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Внесение изменений в отправленные им сообщения электронной почты

Вы можете вносить изменения в сообщения электронной почты, которые автоматически отправляются пользователям. По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить отображаемого имени, используя Windows PowerShell. Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Что делать, если вы не хотите, чтобы им отправляли электронную почту?

Если отключить отправку сообщений пользователям, они не будут отправляться даже при назначении пользователю лицензии. В этом случае код конференции, номер телефона для конференц-связи по умолчанию и, что важнее, ПИН-код аудиоконференции не будут отправлены пользователю. В этом случае вы должны сообщить пользователю, отправив ему отдельное сообщение электронной почты или позвонив ему.

По умолчанию пользователям отправляются сообщения электронной почты, но если вы хотите запретить им получать электронную почту для аудиоконференций, вы можете использовать Microsoft Teams или Windows PowerShell. 

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **Мосты** конференций щелкните **Параметры моста**. 

3. В области **Параметры моста** включите или отключите параметр Автоматически отправлять сообщения электронной почты пользователям при изменении параметров телефонного **дозвона.**

4. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Использование Windows PowerShell**

Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)


## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

По умолчанию отправитель сообщений отправляется из Microsoft 365 или Office 365, но вы можете изменить адрес электронной почты и отображаемого имени с помощью Windows PowerShell. 

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

  - [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Связанные разделы

[Включение и отключение отправки писем при смене настроек аудиоконференций](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
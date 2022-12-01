---
title: Управление сообщениями электронной почты о действиях с действиями
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Сведения о включении и отключении сообщений электронной почты с действиями в беседах Майкрософт Teams
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198511"
---
# <a name="manage-actionable-activity-emails"></a>Управление сообщениями электронной почты о действиях с действиями

Сообщения электронной почты с действиями включены по умолчанию и уведомляют пользователей в вашей организации о пропущенных беседах в Майкрософт Teams.

В сообщении электронной почты о пропущенных действиях отображаются последние ответы на беседу, включая сообщения, отправленные после пропущенного сообщения. Эта функция позволяет пользователям отвечать непосредственно из Outlook, выбрав **Ответить**.

## <a name="disable-actionability-in-missed-activity-emails"></a>Отключение возможности действий в пропущенных сообщениях электронной почты о действиях

Хотя эта функция включена по умолчанию, вы можете отключить возможность действий в сообщениях электронной почты о действиях в организации, выполнив следующую команду:

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

После отключения функции параметр **Ответить** заменяется **ответом в Teams** , что делает сообщения электронной почты о пропущенных действиях не считаются действиями. Пользователи больше не смогут отвечать напрямую из Outlook и будут направлены на продолжение беседы в Teams.

> [!NOTE]
> Эта функция не поддерживается в Outlook для Mac или некоторых более старых версиях Outlook для Windows. Дополнительные сведения см. [в разделе Сообщения с действиями в Outlook и группах Office 365](/outlook/actionable-messages/).

## <a name="related-topics"></a>См. также

[Ответить на пропущенные сообщения электронной почты из Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

[Сообщения с действиями в Outlook и группах Office 365](/outlook/actionable-messages/).

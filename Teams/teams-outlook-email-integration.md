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
description: Сведения о включении и отключении сообщений электронной почты с действиями в беседах Microsoft Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43435c436685c53e0ad077887a9fe9d991cf2d61
ms.sourcegitcommit: f5480d0ca34b3160980a4b46b5afa34271293a26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2022
ms.locfileid: "68899693"
---
# <a name="manage-actionable-activity-emails"></a>Управление сообщениями электронной почты о действиях с действиями

Сообщения электронной почты с действиями включены по умолчанию и уведомляют пользователей в вашей организации о пропущенных беседах в Microsoft Teams.

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

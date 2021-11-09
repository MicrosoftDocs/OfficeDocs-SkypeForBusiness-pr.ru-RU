---
title: Teams и Outlook электронной почты
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте о Teams и Outlook интеграции с электронной почтой, в том числе о том, как пользователи могут обмениваться информацией между электронной почтой в Outlook чате или беседах каналов в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6f41d26a2d87d1c95b99534a866f64cd9f30eb8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837461"
---
# <a name="teams-and-outlook-email-integration"></a>Teams и Outlook электронной почты

Microsoft Teams функции, которые по возможности удобно делиться информацией между электронной почтой в Outlook и чатом или беседами каналов в Teams, а также не пропускать пропущенные беседы. В этой статье представлены общие сведения об этих функциях и применяемом средстве администрирования.

## <a name="share-to-outlook"></a>Поделиться с Outlook

**Отправка Outlook** позволяет пользователям отправлять копию беседы Teams сообщению электронной почты в Outlook, не покидая Teams. Эта функция удобна, если пользователям нужно делиться беседами или обновлениями состояния с пользователями за пределами их ближайшей группы или даже из вашей организации. Перейдите в верхнюю часть беседы в Teams выберите **̇ ̇ ̇** Дополнительные параметры , а затем выберите **Поделиться** Outlook .  Дополнительные информации см. в [Outlook в Teams.](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Снимок экрана: функция "Поделиться Outlook" в Teams.](media/share-to-outlook.png)

Чтобы использовать эту функцию, Outlook в Интернете должна быть включена для пользователя. Если Outlook в Интернете отключен, параметр Поделиться  Outlook не отображается в Teams для пользователя. По шагам о том, как включить и отключить Outlook в Интернете, см. в Outlook в Интернете для [почтового ящика.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>Сообщения электронной почты с действиями

Пользователи автоматически получают сообщения о пропущенных действиях, которые помогают им наверстать упущенную беседу в Teams. В сообщениях о пропущенных действиях показываются последние ответы из беседы, включая сообщения,  отправленные после пропущенного сообщения, и пользователи могут нажать кнопку Ответить, чтобы ответить непосредственно в Outlook. Дополнительные действия см. в ответе [на пропущенные сообщения](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)электронной почты с Outlook. 

> [!NOTE]
> Эта функция не поддерживается в Outlook для Mac или некоторых более старых версиях Outlook для Windows. Дополнительные сведения см. в этой Outlook [и Office 365 группах.](/outlook/actionable-messages/)

![Снимок экрана: пропущенный адрес электронной почты о действиях.](media/missed-activity-email.png)

![Снимок экрана: ответ на пропущенный адрес электронной почты о действиях.](media/missed-activity-email-reply.png)

Для отключения сообщений электронной почты с помощью параметра **SmtpActionableMessagesEnabled** можно использовать вместе с параметром [Set-OrganizationConfig.](/powershell/module/exchange/organization/set-organizationconfig) По умолчанию параметр **SmtpActionableMessagesEnabled** имеет **значение true**. Если задан параметр **False, сообщения электронной** почты с действиями будут отключены Office 365. Для Teams пользователей это означает,  что в пропущенных сообщениях о действиях недоступна возможность ответить непосредственно в Outlook сообщения. Вместо них в сообщениях о  пропущенных действиях есть параметр Ответить Teams, чтобы пользователи отвечали в Teams.

См. также [сообщения с действиями в Outlook и Office 365 группах.](/outlook/actionable-messages/)

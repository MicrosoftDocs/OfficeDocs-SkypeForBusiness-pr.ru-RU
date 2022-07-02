---
title: Интеграция электронной почты Teams и Outlook
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте о функциях интеграции с электронной почтой Teams и Outlook, включая функции, позволяющие пользователям делиться информацией между электронной почтой в Outlook и беседами в чатах или каналах в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606238"
---
# <a name="teams-and-outlook-email-integration"></a>Интеграция электронной почты Teams и Outlook

Microsoft Teams включает функции, которые позволяют пользователям в организации легко делиться информацией между электронной почтой в Outlook и беседами в чатах или каналах в Teams и оставаться на связи с пропущенными беседами. В этой статье приводятся общие сведения об этих функциях и применяемых элементах управления администратора.

## <a name="share-to-outlook"></a>Предоставление общего доступа к Outlook

**Предоставление общего доступа к Outlook** позволяет пользователям делиться копией беседы Teams с сообщением электронной почты в Outlook без необходимости выходить из Teams. Эта функция удобна, если пользователям необходимо делиться беседами или обновлениями состояния с пользователями за пределами их непосредственных групп или даже вашей организации. Перейдите в верхнюю часть беседы в Teams, выберите **... Дополнительные параметры**, а затем выберите **"Поделиться в Outlook"**.  Дополнительные сведения см. в [статье "Общий доступ к Outlook из Teams"](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Снимок экрана: функция "Поделиться в Outlook" в Teams.](media/share-to-outlook.png)

Чтобы использовать эту функцию, Outlook в Интернете необходимо включить для пользователя. Если Outlook в Интернете отключен, параметр "Поделиться в **Outlook**" не отображается в Teams для пользователя. Инструкции по включению и отключению Outlook в Интернете см. в Outlook в Интернете для [почтового ящика](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Сообщения электронной почты с действиями

Пользователи автоматически получают сообщения электронной почты о пропущенных действиях, которые помогают им наверсть пропущенные беседы в Teams. В сообщениях электронной почты о пропущенных действиях отображаются последние ответы из беседы, включая сообщения, отправленные после пропущенного сообщения, и  пользователи могут нажать кнопку "Ответить", чтобы ответить непосредственно из Outlook. Дополнительные сведения см [. в статье "Ответ на пропущенные сообщения электронной почты о действиях" в Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Эта функция не поддерживается в Outlook для Mac или некоторых более ранних версиях Outlook для Windows. Дополнительные сведения см. в статьях о интерактивных [сообщениях в Outlook и Office 365 группах](/outlook/actionable-messages/).

![Снимок экрана: сообщение электронной почты о пропущенных действиях.](media/missed-activity-email.png)

![Снимок экрана: ответ на сообщение электронной почты о пропущенных действиях.](media/missed-activity-email-reply.png)

Командлет [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) можно использовать вместе с параметром **SmtpActionableMessagesEnabled** , чтобы отключить интерактивные сообщения электронной почты. По умолчанию параметр **SmtpActionableMessagesEnabled** имеет значение **true**. Установка значения false для **параметра** отключает интерактивные сообщения электронной почты в Office 365. Для пользователей Teams это означает, что параметр **"** Ответить" для ответа непосредственно в Outlook недоступен в сообщениях электронной почты о пропущенных действиях. Вместо этого в сообщениях электронной почты о пропущенных действиях есть параметр **"Ответить в Teams** ", чтобы пользователи могли отвечать в Teams.

См. также [интерактивные сообщения в Outlook и Office 365 группах](/outlook/actionable-messages/).

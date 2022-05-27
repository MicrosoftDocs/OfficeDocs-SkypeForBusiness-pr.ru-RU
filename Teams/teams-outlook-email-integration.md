---
title: Teams и Outlook электронной почты
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте о функциях интеграции Teams и Outlook электронной почты, включая функции, позволяющие пользователям делиться информацией между электронной почтой в Outlook чате или беседах каналов в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd1226cddb41ee40139029b64c65d6c151c3993b
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681760"
---
# <a name="teams-and-outlook-email-integration"></a>Teams и Outlook электронной почты

Microsoft Teams включает функции, которые упрощают пользователям в организации общий доступ к информации между электронной почтой в Outlook и беседах чата или каналов в Teams, а также для отслеживания пропущенных бесед. В этой статье приводятся общие сведения об этих функциях и применяемых элементах управления администратора.

## <a name="share-to-outlook"></a>Предоставление общего доступа Outlook

**Предоставление общего доступа Outlook** позволяет пользователям делиться копией беседы Teams сообщению электронной почты в Outlook, не выходя из Teams. Эта функция удобна, если пользователям необходимо делиться беседами или обновлениями состояния с пользователями за пределами их непосредственных групп или даже вашей организации. Перейдите в верхнюю часть беседы в Teams выберите **... Дополнительные параметры**, а затем выберите "Поделиться"**, чтобы Outlook**.  Дополнительные сведения см. в [статье "Общий доступ Outlook из Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)".

![Снимок экрана: функция "Поделиться Outlook" в Teams.](media/share-to-outlook.png)

Чтобы использовать эту функцию, Outlook в Интернете необходимо включить для пользователя. Если Outlook в Интернете отключен, параметр "Общий доступ к Outlook" не отображается в Teams для пользователя. Инструкции по включению и отключению Outlook в Интернете см. в Outlook в Интернете для [почтового ящика](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Сообщения электронной почты с действиями

Пользователи автоматически получают сообщения электронной почты о пропущенных действиях, которые помогают им наверсть пропущенные беседы в Teams. В сообщениях электронной почты о пропущенных действиях отображаются последние ответы из беседы, включая сообщения, отправленные после пропущенного сообщения, и  пользователи могут нажать кнопку "Ответить", чтобы ответить непосредственно из Outlook. Дополнительные сведения см. в [статье "Ответ на пропущенные сообщения о действиях" Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Эта функция не поддерживается в Outlook для Mac или некоторых более старых версиях Outlook для Windows. Дополнительные сведения см. в статьях о интерактивных сообщениях в [Outlook и Office 365 группах](/outlook/actionable-messages/).

![Снимок экрана: сообщение электронной почты о пропущенных действиях.](media/missed-activity-email.png)

![Снимок экрана: ответ на сообщение электронной почты о пропущенных действиях.](media/missed-activity-email-reply.png)

Командлет [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) можно использовать вместе с параметром **SmtpActionableMessagesEnabled** , чтобы отключить интерактивные сообщения электронной почты. По умолчанию параметр **SmtpActionableMessagesEnabled** имеет значение **true**. Установка значения false для **параметра** отключает интерактивные сообщения электронной почты в Office 365. Для Teams пользователей это означает, что параметр "Ответить" для ответа непосредственно в Outlook недоступен в сообщениях электронной почты о пропущенных действиях. Вместо этого в сообщениях электронной почты о  пропущенных действиях Teams возможность ответа в Teams.

См. также [интерактивные сообщения в Outlook и Office 365 группах](/outlook/actionable-messages/).

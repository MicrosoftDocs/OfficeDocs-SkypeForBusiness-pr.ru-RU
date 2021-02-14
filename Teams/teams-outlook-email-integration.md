---
title: Интеграция Teams и Outlook с электронной почтой
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Узнайте о том, как интеграция с электронной почтой Teams и Outlook позволяет пользователям обмениваться информацией между электронной почтой в Outlook, а также общаться в чате или беседах каналов в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6e260148cfcdb45c516958bae03ecfadc1bbd64
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802399"
---
# <a name="teams-and-outlook-email-integration"></a>Интеграция Teams и Outlook с электронной почтой

Microsoft Teams включает функции, которые по возможности могут обмениваться информацией между электронной почтой в Outlook, а также общаться в чатах или каналах Teams и быть в верхней части пропущенных бесед. В этой статье представлены общие сведения об этих средствах и средствах администрирования, которые применяются.

## <a name="share-to-outlook"></a>Поделиться в Outlook

**Поделиться в Outlook позволяет** пользователям отправлять копию беседы Teams по электронной почте в Outlook, не покидая Teams. Эта функция удобна, если пользователям нужно делиться беседами или обновлениями состояния с пользователями за пределами их ближайшей группы или даже из вашей организации. Перейдите в верхнюю часть беседы в Teams, выберите **̇ ̇ ̇ "Дополнительные** параметры", а затем выберите "Поделиться **в Outlook".**  Дополнительные узнать см. в share [to Outlook (Поделиться в Outlook из Teams).](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Снимок экрана: функция "Поделиться в Outlook" в Teams](media/share-to-outlook.png)

Для использования этой функции необходимо, чтобы для пользователя был включен Outlook в Интернете. Если Outlook в Интернете отключен, параметр "Поделиться в **Outlook"** не отображается в Teams для пользователя. По шагам, позволяющим включить и отключить [Outlook](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)в Интернете, см. в этом видео.

## <a name="actionable-activity-emails"></a>Сообщения электронной почты с действиями

Пользователи автоматически получают сообщения о пропущенных действиях, которые помогают им наверстать упущенную беседу в Teams. В сообщениях о пропущенных действиях будут демонстрироваться последние ответы из беседы, включая  сообщения, отправленные после пропущенного сообщения, и пользователи могут нажать кнопку "Ответить", чтобы ответить непосредственно из Outlook. Дополнительные узнать см. в ответах на пропущенные сообщения электронной почты [о действиях из Outlook.](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> Эта функция не поддерживается в Outlook для Mac и некоторых более старых версиях Outlook для Windows. Дополнительные сведения см. в сообщениях с действиями [в Outlook и Группах Office 365.](https://docs.microsoft.com/outlook/actionable-messages/)

![Снимок экрана: сообщение о пропущенных действиях](media/missed-activity-email.png)

![Снимок экрана: ответ на пропущенные сообщения об активности](media/missed-activity-email-reply.png)

Для отключения сообщений электронной почты, которые можно использовать вместе с параметром **SmtpActionableMessagesEnabled,** можно использовать для этого набор параметров [Set-OrganizationConfig.](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) По умолчанию параметр **SmtpActionableMessagesEnabled** имеет **значение TRUE.** Если для параметра установить **false,** сообщения электронной почты с действиями будут отключены в Office 365. Для пользователей Teams это  означает, что команда "Ответить" для ответа прямо в Outlook недоступна в пропущенных сообщениях о действиях. Вместо них в пропущенных сообщениях о действиях есть команда **"Ответить** в Teams".

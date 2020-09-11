---
title: Интеграция Teams и электронной почты Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Узнайте о командах и функциях интеграции электронной почты Outlook, в том числе о функциях, которые позволяют пользователям обмениваться информацией между электронной почтой в Outlook, чатам или каналами связи в Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 675834cd36c4e86d34d179e91fe66905e3860b32
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429445"
---
# <a name="teams-and-outlook-email-integration"></a>Интеграция Teams и электронной почты Outlook

Microsoft Teams включает в себя возможности, облегчающие пользователям организации обмен данными между электронной почтой в Outlook, чата и маркетинговые беседы в Teams, а также для поддержания пропуска пропущенных разговоров. В этой статье представлены общие сведения об этих функциях и элементах управления администратора, которые применяются.

## <a name="share-to-outlook"></a>Предоставление общего доступа к Outlook

**Предоставление общего доступа к Outlook** позволяет пользователям делиться копиями беседы группы с электронной почтой в Outlook, не выходя из группы. Эта функция полезна, если пользователям необходимо предоставить общий доступ к беседам или обновлениям состояния пользователям за пределами ненужной команды или даже вашей организации. Перейдите в начало беседы в Teams, выберите **̇ ̇ ̇ Дополнительные параметры**, а затем выберите команду **поделиться в Outlook**.  Дополнительные сведения можно найти в статье [предоставление общего доступа к Outlook из Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Снимок экрана: функция "поделиться с Outlook" в Teams](media/share-to-outlook.png)

Чтобы использовать эту функцию, Outlook в Интернете должен быть включен для пользователя. Если приложение Outlook в Интернете выключено, параметр " **предоставить общий доступ к Outlook** " не отображается в Teams для пользователя. Сведения о том, как включить и отключить Outlook в Интернете, можно найти в статье [Включение и отключение Outlook в Интернете для почтового ящика](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Сообщения о действиях, которые можно отменять

Пользователи автоматически получают электронные сообщения о пропущенных действиях, которые помогают им отслеживать пропущенные беседы в Teams. В сообщениях о пропущенных действиях отображаются самые свежие ответы из беседы, в том числе сообщения, отправленные после пропущенного сообщения, и пользователи могут нажать кнопку **ответить** , чтобы ответить на него прямо в Outlook. Дополнительные сведения можно найти в статье [ответы на сообщения о пропущенных действиях из Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Эта функция не поддерживается в Outlook для Mac и некоторых более ранних версиях Outlook для Windows. Дополнительные сведения можно найти [в разделе сообщения о действиях в группах Outlook и Office 365](https://docs.microsoft.com/outlook/actionable-messages/).

![Снимок экрана, на котором показано сообщение о пропущенных действиях](media/missed-activity-email.png)

![Снимок экрана, на котором показано, как ответить на пропущенное сообщение о мероприятии](media/missed-activity-email-reply.png)

Вы можете использовать командлет [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) вместе с параметром **SmtpActionableMessagesEnabled** , чтобы отключить транзактные сообщения. По умолчанию для параметра **SmtpActionableMessagesEnabled** задано **значение true**. Если задать для параметра **значение false** , транзактные сообщения электронной почты отключаются в Office 365. Для пользователей Teams это означает, что параметр **ответа** , реагирующий прямо в Outlook, недоступен в сообщениях электронной почты о действиях. Вместо этого в сообщениях электронной почты о пропущенных действиях **в Teams** можно ответить, чтобы пользователи могли отвечать на них в Teams.

---
title: "Добавление домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: "Сведения о добавлении домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online для отправки уведомлений участникам."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f671d64b2928c3b5a81d38993143d9755ce42ba
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Добавление домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online 
=============================================================================

Создаете ли вы группу Office 365 с помощью консоли администратора или применяете Outlook для отправки уведомлений участнику команды, добавленному в эту группу, используется Exchange Online. Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams использует Microsoft Exchange Online и для отправки уведомлений членам команды при их добавлении. Отличие заключается в том, что полное доменное имя домена для сообщения SMTP имеет значение "@email.teams.microsoft.com" и может перехватываться фильтрами нежелательной почты. Как можно заметить на изображении ниже, Outlook относит это сообщение к внешнему отправителю, на которого распространяются стандартные функции безопасности, такие как блокировка изображений и некоторого контента.

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Для обеспечения оптимальных результатов и непрерывной работы рекомендуется добавить домен SMTP Microsoft Teams в список обслуживаемых доменов в конфигурации нежелательной почты Exchange Online:

![Снимок экрана с разделом списков разрешений в параметрах конфигурации нежелательной почты Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

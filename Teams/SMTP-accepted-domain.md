---
title: "Добавление домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о добавлении домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online для отправки уведомлений участникам."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 2006cde3cf2fc41a64b98fdc14004aa64876cb1a
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Добавление домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online 
=============================================================================

Создаете ли вы группу Office 365 с помощью консоли администратора или применяете Outlook для отправки уведомлений участнику команды, добавленному в эту группу, используется Exchange Online. Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams использует Microsoft Exchange Online и для отправки уведомлений членам команды при их добавлении. Отличие заключается в том, что полное доменное имя домена для сообщения SMTP имеет значение "@email.teams.microsoft.com" и может перехватываться фильтрами нежелательной почты. Как можно заметить на изображении ниже, Outlook относит это сообщение к внешнему отправителю, на которого распространяются стандартные функции безопасности, такие как блокировка изображений и некоторого контента.

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Для обеспечения оптимальных результатов и непрерывной работы рекомендуется добавить домен SMTP Microsoft Teams в список обслуживаемых доменов в конфигурации нежелательной почты Exchange Online:

![Снимок экрана с разделом списков разрешений в параметрах конфигурации нежелательной почты Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

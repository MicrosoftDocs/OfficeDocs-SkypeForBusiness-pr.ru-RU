---
title: Добавление домена SMTP в качестве разрешенного домена отправителя в Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: В этой статье описано, как добавить домен SMTP Microsoft Teams в качестве домена разрешенных отправителей в Exchange Online для отправки уведомлений участникам группы.
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc35a4797cf5b5fde001090e386f9c172c5b9458
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137269"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="d2ad2-103">Добавление SMTP-домена Microsoft Teams в качестве доверенного отправителя в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d2ad2-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="d2ad2-104">Создаете ли вы группу Office 365 с помощью консоли администратора или применяете Outlook для отправки уведомлений участнику команды, добавленному в эту группу, используется Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2ad2-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="d2ad2-105">Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2ad2-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="d2ad2-107">Teams использует Microsoft Exchange Online, а также отправлять уведомления участникам группы о добавлении.</span><span class="sxs-lookup"><span data-stu-id="d2ad2-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="d2ad2-108">Различием является полное доменное имя домена сообщения SMTP — "@email. teams.microsoft.com" для коммерческих и бизнес-клиентов и "@GCC-email.teams.com" для государственных клиентов и может быть перехвачено фильтром нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d2ad2-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="d2ad2-110">Для достижения наилучшего результата и эффективной работы рекомендуется добавить домен SMTP Microsoft Teams в список "разрешенные домены отправителей" в конфигурации спама в Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="d2ad2-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Снимок экрана: раздел "списки разрешенных" параметров конфигурации спама](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

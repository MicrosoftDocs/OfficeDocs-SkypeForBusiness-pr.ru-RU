---
title: Добавление домена SMTP в качестве разрешенного домена отправителя в Exchange Online
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582056"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="0fb5b-103">Добавление SMTP-домена Microsoft Teams в качестве доверенного отправителя в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0fb5b-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="0fb5b-104">Если вы создаете группу Microsoft 365 на консоли администрирования или Outlook, то Exchange Online используется для отправки уведомлений участника команды, добавленного в группу.</span><span class="sxs-lookup"><span data-stu-id="0fb5b-104">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group.</span></span> <span data-ttu-id="0fb5b-105">Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0fb5b-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="0fb5b-107">Teams использует Microsoft Exchange Online, а также отправлять уведомления участникам группы о добавлении.</span><span class="sxs-lookup"><span data-stu-id="0fb5b-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="0fb5b-108">Различием является полное доменное имя домена сообщения SMTP — "@email. teams.microsoft.com" для коммерческих и бизнес-клиентов и "@GCC-email.teams.microsoft.com" для государственных клиентов и может быть перехвачено фильтром нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="0fb5b-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.microsoft.com" for Government tenants and could be caught by spam filtering.</span></span>

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="0fb5b-110">Для достижения наилучшего результата и эффективной работы рекомендуется добавить домен SMTP Microsoft Teams в список "разрешенные домены отправителей" в конфигурации спама в Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0fb5b-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Снимок экрана: раздел "списки разрешенных" параметров конфигурации спама](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

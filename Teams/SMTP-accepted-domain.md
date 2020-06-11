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
ms.openlocfilehash: b66b58cb14c5205b0ba4a6ff7e95102dc1584579
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689865"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="b0e89-103">Добавление SMTP-домена Microsoft Teams в качестве доверенного отправителя в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b0e89-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="b0e89-104">Если вы создаете группу Microsoft 365 на консоли администрирования или Outlook, то Exchange Online используется для отправки уведомлений участника команды, добавленного в группу.</span><span class="sxs-lookup"><span data-stu-id="b0e89-104">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group.</span></span> <span data-ttu-id="b0e89-105">Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b0e89-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="b0e89-107">Teams использует Microsoft Exchange Online, а также отправлять уведомления участникам группы о добавлении.</span><span class="sxs-lookup"><span data-stu-id="b0e89-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="b0e89-108">Различием является полное доменное имя домена сообщения SMTP — "@email. teams.microsoft.com" для коммерческих и бизнес-клиентов и "@GCC-email.teams.com" для государственных клиентов и может быть перехвачено фильтром нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="b0e89-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="b0e89-110">Для достижения наилучшего результата и эффективной работы рекомендуется добавить домен SMTP Microsoft Teams в список "разрешенные домены отправителей" в конфигурации спама в Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="b0e89-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Снимок экрана: раздел "списки разрешенных" параметров конфигурации спама](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

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
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="200d2-103">Добавление домена SMTP Microsoft Teams в качестве обслуживаемого в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="200d2-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="200d2-104">Создаете ли вы группу Office 365 с помощью консоли администратора или применяете Outlook для отправки уведомлений участнику команды, добавленному в эту группу, используется Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="200d2-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="200d2-105">Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="200d2-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="200d2-107">Teams использует Microsoft Exchange Online и для отправки уведомлений членам команды при их добавлении.</span><span class="sxs-lookup"><span data-stu-id="200d2-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="200d2-108">Отличие заключается в том, что полное доменное имя домена для сообщения SMTP имеет значение "@email.teams.microsoft.com" и может перехватываться фильтрами нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="200d2-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering.</span></span> <span data-ttu-id="200d2-109">Как можно заметить на изображении ниже, Outlook относит это сообщение к внешнему отправителю, на которого распространяются стандартные функции безопасности, такие как блокировка изображений и некоторого контента.</span><span class="sxs-lookup"><span data-stu-id="200d2-109">As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="200d2-111">Для обеспечения оптимальных результатов и непрерывной работы рекомендуется добавить домен SMTP Microsoft Teams в список обслуживаемых доменов в конфигурации нежелательной почты Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="200d2-111">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![Снимок экрана с разделом списков разрешений в параметрах конфигурации нежелательной почты Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

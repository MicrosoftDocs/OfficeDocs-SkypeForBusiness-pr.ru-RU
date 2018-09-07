---
title: Добавление Microsoft группами домена SMTP как домена разрешенных отправителей в Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
search.appverid: MET150
description: Сведения для добавления домена SMTP группы Microsoft как домена разрешенных отправителей в Exchange Online для отправки уведомления участников группы.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f0b20f84484d4b0998a11653fe7f9d2bb1e9899
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861587"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="a8d9e-103">Добавление Microsoft группами домена SMTP как домена разрешенных отправителей в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a8d9e-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="a8d9e-104">Создаете ли вы группу Office 365 с помощью консоли администратора или применяете Outlook для отправки уведомлений участнику команды, добавленному в эту группу, используется Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="a8d9e-105">Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="a8d9e-107">Teams использует Microsoft Exchange Online и для отправки уведомлений членам команды при их добавлении.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="a8d9e-108">Отличие заключается в том, что полное доменное имя домена для сообщения SMTP имеет значение "@email.teams.microsoft.com" и может перехватываться фильтрами нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering.</span></span>

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="a8d9e-110">Для наиболее результатов и работать рассмотрите возможность добавления домена SMTP группами Майкрософт в список «разрешенные домены» в Exchange Online конфигурации нежелательной почты:</span><span class="sxs-lookup"><span data-stu-id="a8d9e-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Снимок экрана с разделом списков разрешений в параметрах конфигурации нежелательной почты Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

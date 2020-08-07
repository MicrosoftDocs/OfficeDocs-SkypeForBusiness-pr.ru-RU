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
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Добавление SMTP-домена Microsoft Teams в качестве доверенного отправителя в Exchange Online 
=============================================================================

Если вы создаете группу Microsoft 365 на консоли администрирования или Outlook, то Exchange Online используется для отправки уведомлений участника команды, добавленного в группу. Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams использует Microsoft Exchange Online, а также отправлять уведомления участникам группы о добавлении. Различием является полное доменное имя домена сообщения SMTP — "@email. teams.microsoft.com" для коммерческих и бизнес-клиентов и "@GCC-email.teams.microsoft.com" для государственных клиентов и может быть перехвачено фильтром нежелательной почты.

![Снимок экрана: заголовок сообщения, показывающий пользователя, добавленного в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Для достижения наилучшего результата и эффективной работы рекомендуется добавить домен SMTP Microsoft Teams в список "разрешенные домены отправителей" в конфигурации спама в Exchange Online:

![Снимок экрана: раздел "списки разрешенных" параметров конфигурации спама](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

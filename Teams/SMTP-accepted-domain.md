---
title: Добавление SMTP-домена Microsoft Teams в качестве доверенного отправителя в Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Сведения для добавления домена SMTP группы Microsoft как домена разрешенных отправителей в Exchange Online для отправки уведомления участников группы.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4a1a94bec69b1c7953dea6802d62058b04700bb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194173"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Добавление SMTP-домена Microsoft Teams в качестве доверенного отправителя в Exchange Online 
=============================================================================

Создаете ли вы группу Office 365 с помощью консоли администратора или применяете Outlook для отправки уведомлений участнику команды, добавленному в эту группу, используется Exchange Online. Эти сообщения формируются в клиенте, так как представляют полное доменное имя SMTP вашего домена по умолчанию.

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams использует Microsoft Exchange Online и для отправки уведомлений членам команды при их добавлении. Разница сейчас домена полное доменное имя SMTP-сообщения «@email.teams.microsoft.com» для коммерческих или бизнес-клиентов и «@GCC-email.teams.com» для правительственных клиентов и может обнаруживаться фильтрации нежелательной почты.

![Снимок экрана с примером заголовка сообщения Outlook, указывающего, что пользователь добавлен в группу.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Для наиболее результатов и работать рассмотрите возможность добавления домена SMTP группами Майкрософт в список «разрешенные домены» в Exchange Online конфигурации нежелательной почты:

![Снимок экрана с разделом списков разрешений в параметрах конфигурации нежелательной почты Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)

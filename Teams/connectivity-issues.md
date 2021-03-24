---
title: Устранение проблем с подключением в клиенте Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Сведения о поиске и устранении проблем связи с клиентом Microsoft Teams, которые чаще всего вызваны подключением к брандмауэру или прокси-серверу.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101165"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Устранение проблем связи с клиентом Microsoft Teams
==============================================================

Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу. Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок. Дополнительные сведения о URL-адресах и IP-адресах, необходимых для Microsoft Teams, см. в статье поддержки URL-адресов и IP-адресов [Microsoft 365 и Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.

- Проверка подлинности

- Взаимодействие с клиентом Microsoft Teams

- Совместная работа

- Мультимедиа

- Общие службы

- Интеграция со сторонними решениями

- Взаимодействие со Skype для бизнеса

- Взаимодействие с клиентом Skype для бизнеса

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Если Teams работает в автономном режиме или при низкой пропускной способности

Хорошая новость заключается в том, что Teams продолжает работать даже при работе в автономном режиме или при низкой пропускной способности. Teams сохраняет все неуправляемые сообщения в существующих чатах (в течение 24 часов) и отправляет их, как только вы снова будете в сети. Если вы работаете в автономном режиме более 24 часов, Teams позволяет повторно отправить или удалить неуданные сообщения. Мы работаем над добавлением этой функции в новые чаты и обновим эту документацию, когда она будет доступна.

## <a name="related-topics"></a>Статьи по теме

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)
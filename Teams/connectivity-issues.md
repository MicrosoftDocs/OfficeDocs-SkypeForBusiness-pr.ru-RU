---
title: Устранение неполадок с подключением к клиенту Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 8974aa7cf54ab61cb15650b839185daad1b82cc7
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562168"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Устранение проблем связи с клиентом Microsoft Teams

Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу. Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок. Дополнительные сведения о URL-адресах и IP-адресах, необходимых для Microsoft Teams, см. в статье о поддержке URL-Office 365 и URL-адресов [Microsoft 365 и Office 365 IP-адресов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.

- Проверка подлинности

- Взаимодействие с клиентом Microsoft Teams

- Совместная работа

- Мультимедиа

- Общие службы

- Интеграция со сторонними решениями

- Взаимодействие со Skype для бизнеса

- Взаимодействие с клиентом Skype для бизнеса

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Когда Teams находится в автономном режиме или в условиях низкой пропускной способности

Хорошая новость заключается в том, что Teams продолжает работать, даже если вы работаете в автономном режиме или работаете в условиях низкой пропускной способности. Teams сохраняет все ненаправленные сообщения для существующих чатов (до 24 часов) и отправляет их, как только вы снова будете подключены к сети. Если вы не в сети более 24 часов, Teams позволяет повторно отправлять или удалять неавторные сообщения. Мы работаем над добавлением этой функции в новые чаты и обновим эту документацию, когда она будет доступна.

## <a name="related-topics"></a>Статьи по теме

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)
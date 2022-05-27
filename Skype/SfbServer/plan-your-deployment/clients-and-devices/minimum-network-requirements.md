---
title: Минимальные требования к сети для приложения "Собрания Skype"
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: Сводка. Сведения для организаций, которые не используют Microsoft 365 или Office 365 и которым требуется доступ к собраниям, размещенным в организациях, которые это делать.
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674531"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"

**Сводка:** Сведения для организаций, которые не используют Microsoft 365 или Office 365 и должны получать доступ к собраниям, размещенным в организациях, которые это делать. Эта статья не предназначена для Office 365 или Microsoft 365 пользователей.

Пользователям приложения Skype "Собрания" в организациях, которые не используют Microsoft 365 или Office 365, может потребоваться посетить собрания, размещенные в Skype для бизнеса Online. Для участия в этих собраниях администраторам сети необходимо разрешить следующие полные доменные имена, IP-адреса и порты через брандмауэр.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключению Skype собраний

Приведенные здесь сведения — это подмножество сведений в Office 365 [URL-адресов и диапазонов IP-адресов](/microsoft-365/enterprise/urls-and-ip-address-ranges). Этот раздел является более подробным и всегда будет актуальным.

|Приложение|Полные доменные имена назначения|IP-адреса|Порты|
|---|---------|---------|---------|
|**Skype "Собрания"**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|Эти IP-адреса часто обновляются. См[. Skype для бизнеса и Microsoft Teams диапазонов IP-адресов](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), а [также Office IP-адресов](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|Эти IP-адреса часто обновляются. См[. Skype для бизнеса и Microsoft Teams диапазонов IP-адресов](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), а [также Office IP-адресов](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование клиентов собраний (веб-приложение и приложение для собраний)](meetings-clients.md)

[Развертывание веб-загружаемых клиентов в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы для Skype собраний](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

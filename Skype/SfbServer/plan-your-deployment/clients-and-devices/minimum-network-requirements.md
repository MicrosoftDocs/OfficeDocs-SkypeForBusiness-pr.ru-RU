---
title: Минимальные требования к сети для приложения "Собрания Skype"
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: Сводка. Сведения для организаций, которые не используют Microsoft 365 или Office 365 и должны получать доступ к собраниям, которые организованы организациями, которые это делают.
ms.openlocfilehash: b79c49b1b63041e84cc74887f6693e8601ae2465f90665ff757d9d890cb330cc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283201"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Сведения для организаций, которые не используют Microsoft 365 или Office 365 и должны получать доступ к собраниям, которые организованы организациями, которые это делают. Эта статья не предназначена для пользователей этих приложений.
  
Чтобы разрешить пользователям использовать Skype Meetings App для участия в собраниях, которые размещены в Skype для бизнеса Online, сетевые администраторы организаций, которые не используют Microsoft 365 или Office 365, должны разрешить или иным образом сделать доступными указанные ниже FQDNs, IPs и порты.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключению Skype к приложению meetings

Перечисленные здесь сведения — [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)это подмножество Office 365 URL-адресов и диапазонов IP-адресов, которые предоставляют больше глубины и всегда будут самыми в курсе.
                    
 
|Приложение |FQDNs назначения  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение "Собрания Skype"** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*трансляция <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Эти IP-адреса часто обновляются.  См. [Skype для бизнеса диапазоны](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) IP и [Office диапазоны IP-адресов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Эти IP-адреса часто обновляются.  См. [Skype для бизнеса диапазоны](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) IP и [Office диапазоны IP-адресов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование для клиентов собраний (Web App и Meetings App)](meetings-clients.md)

[Развертывание веб-загружаемых клиентов в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы для Skype собраний](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

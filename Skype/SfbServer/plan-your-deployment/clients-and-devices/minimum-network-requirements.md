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
description: Сводка. Сведения для организаций, которые не используют Microsoft 365 или Office 365 и должны получать доступ к собраниям, которые организованы организациями, которые это делают.
ms.openlocfilehash: 06432f8629ec8cdb451ebff9146e24b3929a2d3e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395121"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Сведения для организаций, которые не используют Microsoft 365 или Office 365 и должны получать доступ к собраниям, которые организованы организациями, которые это делают. Эта статья не предназначена для пользователей этих приложений.
  
Чтобы разрешить пользователям использовать Skype Meetings App для участия в собраниях, которые размещены в Skype для бизнеса Online, сетевые администраторы организаций, которые не используют Microsoft 365 или Office 365, должны разрешить или иным образом сделать доступными указанные ниже FQDNs, IPs и порты.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключению Skype к приложению meetings

Перечисленные здесь сведения — это подмножество Office 365 URL-адресов и [диапазонов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) IP-адресов, которые предоставляют более подробную информацию и всегда будут самыми в курсе.
                    
 
|Приложение |FQDNs назначения  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение "Собрания Skype"** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Эти IP-адреса часто обновляются.  См[. Skype для бизнеса диапазоны IP-адресов](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip), [а также Office диапазоны IP-адресов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Эти IP-адреса часто обновляются.  См[. Skype для бизнеса диапазоны IP-адресов](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip), [а также Office диапазоны IP-адресов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование для клиентов собраний (Web App и Meetings App)](meetings-clients.md)

[Развертывание веб-загружаемых клиентов в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы для Skype собраний](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

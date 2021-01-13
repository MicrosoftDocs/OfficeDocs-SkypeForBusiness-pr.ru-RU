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
description: Сводка. Сведения для организаций, которые не используют Microsoft 365 или Office 365 и которым необходим доступ к собраниям, которые будут проводиться в организациях.
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816309"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Сведения для организаций, которые не используют Microsoft 365 или Office 365 и которым необходим доступ к собраниям, которые будут проводиться организациями. Эта статья не предназначена для пользователей этих приложений.
  
Чтобы разрешить пользователям использовать приложение "Собрания Skype" для участия в собраниях, которые размещены в Skype для бизнеса Online, сетевые администраторы организаций, не пользующихся Microsoft 365 или Office 365, должны разрешить или иным образом сделать доступными FQDNs, IPS и порты, упомянутые ниже.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключению приложения "Собрания Skype"

Перечисленные здесь сведения — это подмножество URL-адресов [и диапазонов IP-адресов Office 365,](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)которые предоставляют более подробную информацию и всегда будут самыми последние.
                    
 
|Приложение |Destination FQDNs  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение "Собрания Skype"** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Эти IP-адреса часто обновляются.  См. [диапазоны IP-адресов Skype](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) для бизнеса, а также [диапазоны IP-адресов Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Эти IP-адреса часто обновляются.  См. [диапазоны IP-адресов Skype](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) для бизнеса, а также [диапазоны IP-адресов Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование клиентов собраний (Веб-приложение и приложение для собраний)](meetings-clients.md)

[Развертывание загружаемых веб-клиентов в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы для приложения "Собрания Skype"](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

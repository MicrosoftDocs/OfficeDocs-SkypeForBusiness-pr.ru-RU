---
title: Минимальные требования к сети для приложения "Собрания Skype"
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Сводка: сведения для организаций, которые не используют Office 365 и должны иметь доступ к собраниям, размещенным в организациях.'
ms.openlocfilehash: 631c4b9825181300552faa387c00a1ca73097885
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792858"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Сведения для организаций, которые не используют Office 365 и должны иметь доступ к собраниям, размещенным в организациях. Эта статья не предназначена для пользователей этих приложений.
  
Чтобы пользователи могли использовать приложение "собрания Skype" для участия в собраниях, размещенных в Skype для бизнеса Online, сетевые администраторы организаций, не использующих Office 365, должны Добавление или иным образом предоставлять полные доменные имена, IP-адреса и порты, упомянутые ниже.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключениям для приложения "Собрания Skype"

Указанные здесь сведения представляют собой подмножество [URL-адресов и диапазонов IP-адресов Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), что обеспечивает более глубокую и наиболее актуальную информацию.
                    
 
|· |Полные доменные имена назначения  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение для собраний Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.Live.com <br/>\*PowerPoint<span></span>. officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-microsoft.com<br/>        |   Эти IP-адреса часто обновляются.  Просмотр [диапазонов IP-адресов Skype для бизнеса](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) и [диапазонов IP-адресов Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478–3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Эти IP-адреса часто обновляются.  Просмотр [диапазонов IP-адресов Skype для бизнеса](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) и [диапазонов IP-адресов Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478–3481

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование клиентов собраний (приложение для веб-приложений и собраний)](meetings-clients.md)

[Развертывание загружаемых веб-клиентов в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Платформы, поддерживаемые приложением "собрания Skype"](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

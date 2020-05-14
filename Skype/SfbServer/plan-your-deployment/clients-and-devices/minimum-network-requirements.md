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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: Сводка. сведения для организаций, которые не используют Microsoft 365 или Office 365 и нуждаются в доступе к собраниям, размещенным в организациях.
ms.openlocfilehash: 656f8fa52f4a1080cca0b8464becf77c8c2a0ef0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219729"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Сведения для организаций, которые не используют Microsoft 365 или Office 365 и нуждаются в доступе к собраниям, размещенным в организациях. Эта статья не предназначена для пользователей этих приложений.
  
Чтобы разрешить пользователям использовать приложение для собраний Skype для участия в собраниях, размещенных в Skype для бизнеса Online, сетевые администраторы организаций, не использующих Microsoft 365 или Office 365, должны белом или иным образом предоставить доступ к полным доменным именам, IP-адресам и портам, указанным ниже.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключению приложений для собраний Skype

Приведенные здесь сведения являются подмножеством [URL-адресов и диапазонов IP-адресов Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), что более важно и всегда является самым актуальным.
                    
 
|Приложение |Полные доменные имена назначения  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение "Собрания Skype"** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast <span></span> . officeapps.Live.com <br/>\*PowerPoint <span></span> . officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   Эти IP-адреса часто обновляются.  Просмотрите [диапазоны IP-адресов Skype для бизнеса](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) и [диапазоны IP-адресов Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) .         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Эти IP-адреса часто обновляются.  Просмотрите [диапазоны IP-адресов Skype для бизнеса](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) и [диапазоны IP-адресов Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) .      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование для клиентов собраний (приложение для веб-приложений и собраний)](meetings-clients.md)

[Развертывание веб-клиентов, загружаемых через Интернет, в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы для приложения "собрания Skype"](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

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
description: 'Сводка: сведения для организаций, которые не используют Office 365 и должны иметь доступ к собраниям, размещенным в организациях.'
ms.openlocfilehash: e158d93b68df761b59535f4e9239d14194c10443
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816028"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Сведения для организаций, которые не используют Office 365 и должны иметь доступ к собраниям, размещенным в организациях. Эта статья не предназначена для пользователей этих приложений.
  
Чтобы пользователи могли использовать приложение "собрания Skype" для участия в собраниях, размещенных в Skype для бизнеса Online, сетевые администраторы организаций, не использующих Office 365, должны Добавление или иным образом предоставлять полные доменные имена, IP-адреса и порты, упомянутые ниже.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключениям для приложения "Собрания Skype"

Указанные здесь сведения представляют собой подмножество [URL-адресов и диапазонов IP-адресов Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), что обеспечивает более глубокую и наиболее актуальную информацию.
                    
 
|· |Полные доменные имена назначения  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение "Собрания Skype"** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.Live.com <br/>\*PowerPoint<span></span>. officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-microsoft.com<br/>        |   Эти IP-адреса часто обновляются.  Просмотр [диапазонов IP-адресов Skype для бизнеса](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) и [диапазонов IP-адресов Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478–3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Эти IP-адреса часто обновляются.  Просмотр [диапазонов IP-адресов Skype для бизнеса](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) и [диапазонов IP-адресов Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478–3481

## <a name="see-also"></a>См. также
<a name="BKMK_Conferencing"> </a>

[Планирование для клиентов собраний (Skype для бизнеса Web App и приложение "Собрания Skype")](meetings-clients.md)

[Развертывание веб-клиентов, доступных для загрузки, в Skype для бизнеса Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы приложения "Собрания Skype"](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

---
title: Минимальные требования к сети для приложения "Собрания Skype"
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Сводка: Сведения о для организаций, которые не использовать Office 365 и требуется доступ к собраниям, размещенного в организации, выполните.'
ms.openlocfilehash: e186b08a09f52e8de2d3f28867a4a0a30cdb1732
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19577037"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Минимальные требования к сети для приложения "Собрания Skype"
 
**Сводка:**  Информация для организаций, которые не использовать Office 365 и требуется доступ к собраниям, размещенного в организации, выполните. В этой статье не предназначен для пользователей из этих приложений.
  
Чтобы пользователи могли использовать приложение собраний Скайп собрания, размещенные в Скайп для бизнеса в Интернет, сетевых администраторов организаций, которые не используют <token>nm-office-365-short</token> следует белом или в противном случае — сделать доступным полные доменные имена, IP-адреса и порты упомянутые ниже.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Требования к подключениям для приложения "Собрания Skype"

Сведения, показанных здесь является частью [диапазонов адресов URL-адреса Office 365 и IP-адрес](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), который обеспечивает более подробно и всегда будет наиболее в актуальном состоянии.
                    
 
|Приложения |Полные доменные имена назначения  |IP-адреса  |Порты  |
|---|---------|---------|---------|
|**Приложение Скайп собраний** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*вещания<span></span>. officeapps.live.com <br/>\*PowerPoint<span></span>. officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-Microsoft.com (en)<br/>        |   Эти IP-адреса часто обновляются.  Просмотреть [Скайп для диапазонов IP-адресов бизнеса](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , а также [Office Online диапазонов IP-адресов](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478–3481<br/>
|**Teams**    | *. microsoft.com <br/> *. skype.com | Эти IP-адреса часто обновляются.  Просмотреть [Скайп для диапазонов IP-адресов бизнеса](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , а также [Office Online диапазонов IP-адресов](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478–3481

## <a name="see-also"></a>Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.
<a name="BKMK_Conferencing"> </a>

[Планирование для клиентов собрания (веб-приложения и приложения собрания)](meetings-clients.md)

[Развертывание веб-загрузки клиентов в Скайп для Business Server 2015](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Поддерживаемые платформы для приложения Скайп собраний](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
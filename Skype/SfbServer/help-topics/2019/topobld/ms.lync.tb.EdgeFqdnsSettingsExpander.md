---
title: Расширитель параметров полного доменного имени пограничного сервера
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Если для пограничных серверов требуется задать или изменить значения в разделе Внешние параметры, необходимо сначала определить, будут ли назначены отдельные IP-адреса для доступа по протоколу SIP, для пограничных веб-конференций и для пограничной службы передачи аудио- и видеоданных
ms.openlocfilehash: 4edc676da68538c9860083b1e27f7e16eb89f846
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069584"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="9a420-103">Расширитель параметров полного доменного имени пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="9a420-103">Edge Server FQDNs Settings Expander</span></span>
 
<span data-ttu-id="9a420-104">Если для пограничных серверов требуется задать или изменить значения в разделе **Внешние параметры**, необходимо сначала определить, будут ли назначены отдельные IP-адреса для доступа по протоколу SIP, для пограничных веб-конференций и для пограничной службы передачи аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="9a420-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>
  
<span data-ttu-id="9a420-p101">Если планируется назначить отдельный IP-адрес для каждой службы, установите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Для каждой службы должна быть создана соответствующая запись узла (A) в службе доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="9a420-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>
  
<span data-ttu-id="9a420-p102">Для каждой службы, обращенной к внешним сетям, укажите полное доменное имя и связанный с ней порт. Например, для службы **Доступ SIP** следовало бы указать полное доменное имя sip.contoso.com и связанный порт 5061.</span><span class="sxs-lookup"><span data-stu-id="9a420-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a420-p103">Если вы решили использовать отдельные полные доменные имена для каждой из служб, обращенных во внешние сети, с каждой службой должен быть сопоставлено уникальное значение порта. По умолчанию SIP использует порт 5061/TLS, пограничная служба веб-конференций использует порт 444/TLS, а пограничная служба передачи аудио- и видеоданных использует порт 443/TLS. Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="9a420-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span> 
  
<span data-ttu-id="9a420-p104">Если в организации планируется назначить единое полное доменное имя и единый IP-адрес для служб, обращенных к внешним сетям, снимите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. При необходимости значения полного доменного имени и порта для пула **Доступ SIP** можно изменить позднее.</span><span class="sxs-lookup"><span data-stu-id="9a420-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a420-114">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="9a420-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span> 
  
<span data-ttu-id="9a420-115">Для получения дополнительных сведений об определении и настройке параметров для службы пограничного сервера просмотрите [Определение пограничных серверов](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="9a420-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>
  


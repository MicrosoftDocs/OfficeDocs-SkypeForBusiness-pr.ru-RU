---
title: Расширитель параметров полного доменного имени пограничного сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Чтобы изменить или указать внешние параметры для edge Servers, сначала необходимо определить, будут ли вы использовать отдельные IP-адреса для доступа к протоколу инициации сеансов, службе веб-конференции Edge и службе аудио- и видеоконференции.
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095564"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="64d28-103">Расширитель параметров полного доменного имени пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="64d28-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="64d28-104">Чтобы изменить  или указать внешние параметры для edge Servers, сначала необходимо определить, будут ли вы использовать отдельные IP-адреса для доступа к протоколу инициации сеансов, службе веб-конференции Edge и службе аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="64d28-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="64d28-p101">Если вы намереваетесь для каждого из компонентов использовать разные IP-адреса, установите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Для каждой службы должна быть создана соответствующая запись хоста (A) службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="64d28-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="64d28-p102">Для каждой службы, обращенной во внешние сети, укажите полное доменное имя и соответствующий порт. Например, для **Доступ SIP** можно использовать sip.contoso.com с соответствующим портом 5061.</span><span class="sxs-lookup"><span data-stu-id="64d28-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64d28-p103">Если вы решили использовать отдельные полные доменные имена для каждой из служб, обращенных во внешние сети, с каждой службой должен быть сопоставлено уникальное значение порта. По умолчанию SIP использует порт 5061/TLS, пограничная служба веб-конференций использует порт 444/TLS, а пограничная служба передачи аудио- и видеоданных использует порт 443/TLS. Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="64d28-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="64d28-p104">Если в организации будет использоваться единое полное доменное имя и IP-адрес для служб, обращенных во внешние сети, снимите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Затем при необходимости можно изменить значения полного доменного имени и порта для пула **Доступ SIP**.</span><span class="sxs-lookup"><span data-stu-id="64d28-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64d28-114">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="64d28-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="64d28-115">Сведения об определении и настройке параметров для служб Edge см. в материале [Define Your Edge Topology.](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)</span><span class="sxs-lookup"><span data-stu-id="64d28-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>
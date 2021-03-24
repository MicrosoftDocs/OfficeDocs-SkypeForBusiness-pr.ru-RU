---
title: Расширитель пограничных параметров
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы изменить параметры для одного или нескольких существующих пулов пограничных серверов, можно воспользоваться следующими разделами параметров:'
ms.openlocfilehash: c887ffaa16818e377035109632871b7bc7ed25d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108805"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="61af7-103">Расширитель параметров пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="61af7-103">Edge Settings Expander</span></span>

<span data-ttu-id="61af7-104">Чтобы изменить параметры для одного или нескольких существующих пулов пограничных серверов, можно воспользоваться следующими разделами параметров:</span><span class="sxs-lookup"><span data-stu-id="61af7-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="61af7-105">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="61af7-105">General settings</span></span>

- <span data-ttu-id="61af7-106">Параметры выбора следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="61af7-106">Next hop selection settings</span></span>

- <span data-ttu-id="61af7-107">Конфигурация пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="61af7-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="61af7-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="61af7-108">General settings</span></span>

<span data-ttu-id="61af7-p101">Внутреннее полное доменное имя пола пограничных серверов. Измените полное доменное имя пула, чтобы изменить данный параметр.</span><span class="sxs-lookup"><span data-stu-id="61af7-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="61af7-111">Выберите поле "Включить федерацию" для этого пула **Edge (Порт 5061),** если вы настроили федерацию на сервере Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61af7-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="61af7-112">Укажите номер порта в поле **Внутренний порт репликации конфигурации (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="61af7-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="61af7-113">Параметры выбора следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="61af7-113">Next hop selection settings</span></span>

<span data-ttu-id="61af7-114">Чтобы настроить или изменить пул **next hop,** который будут использовать edge Servers для связи с внутренней инфраструктурой, выберите пул Director, Director, Front End Server или front End Server из окна списка.</span><span class="sxs-lookup"><span data-stu-id="61af7-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="61af7-115">Для выбора будут отображаться только директора или передние концы, настроенные в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="61af7-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="61af7-116">Конфигурация пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="61af7-116">Edge Server configuration</span></span>

<span data-ttu-id="61af7-117">Чтобы изменить или задать **Внешние параметры** для пограничных серверов, следует сначала определить, будете ли вы использовать IP-адреса для доступа по протоколу SIP, для веб-конференций и для службы передачи аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="61af7-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="61af7-p103">Если вы намереваетесь для каждого из компонентов использовать разные IP-адреса, установите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Для каждой службы должна быть создана соответствующая запись хоста (A) службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="61af7-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="61af7-p104">Для каждой службы, обращенной во внешние сети, укажите полное доменное имя и соответствующий порт. Например, для **Доступ SIP** можно использовать sip.contoso.com с соответствующим портом 5061.</span><span class="sxs-lookup"><span data-stu-id="61af7-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61af7-122">Если вы решили использовать отдельные полные доменные имена для каждой из служб, обращенных во внешние сети, с каждой службой должен быть сопоставлено уникальное значение порта.</span><span class="sxs-lookup"><span data-stu-id="61af7-122">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="61af7-123">По умолчанию SIP находится в порту 5061/TLS, край веб-конференциалов — на порте 444/TLS, а сервер A/V Conferencing — на порте 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="61af7-123">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="61af7-124">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="61af7-124">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="61af7-p106">Если в организации будет использоваться единое полное доменное имя и IP-адрес для служб, обращенных во внешние сети, снимите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Затем при необходимости можно изменить значения полного доменного имени и порта для пула **Доступ SIP**.</span><span class="sxs-lookup"><span data-stu-id="61af7-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61af7-127">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="61af7-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="61af7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="61af7-128">See also</span></span>

<span data-ttu-id="61af7-129">Дополнительные сведения об определении и настройке параметров для пограничных служб см. в разделе [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span><span class="sxs-lookup"><span data-stu-id="61af7-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>
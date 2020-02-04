---
title: Расширитель пограничных параметров
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Чтобы изменить параметры для одного или нескольких существующих пулов пограничных серверов, можно воспользоваться следующими разделами параметров:'
ms.openlocfilehash: cdc197bb5e6255a9ad0ff69110435908bf6156d5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684742"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="e420f-103">Расширитель пограничных параметров</span><span class="sxs-lookup"><span data-stu-id="e420f-103">Edge Settings Expander</span></span>

<span data-ttu-id="e420f-104">Чтобы изменить параметры для одного или нескольких существующих пулов пограничных серверов, можно воспользоваться следующими разделами параметров:</span><span class="sxs-lookup"><span data-stu-id="e420f-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="e420f-105">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="e420f-105">General settings</span></span>

- <span data-ttu-id="e420f-106">Параметры выбора следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="e420f-106">Next hop selection settings</span></span>

- <span data-ttu-id="e420f-107">Конфигурация пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e420f-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="e420f-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="e420f-108">General settings</span></span>

<span data-ttu-id="e420f-p101">Внутреннее полное доменное имя пола пограничных серверов. Измените полное доменное имя пула, чтобы изменить данный параметр.</span><span class="sxs-lookup"><span data-stu-id="e420f-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="e420f-111">Установите флажок **включить федерацию для этого пограничного пула (порт 5061)** , если вы настроили Федерацию с помощью доверенного партнера Lync Server 2013, Microsoft Lync Server 2010 или Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e420f-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="e420f-112">Если требуется разрешить федерацию XMPP, установите флажок **Включить поддержку федерации XMPP для этого пограничного пула**.</span><span class="sxs-lookup"><span data-stu-id="e420f-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="e420f-113">В поле **Внутренний порт репликации конфигурации (HTTPS)** укажите номер порта.</span><span class="sxs-lookup"><span data-stu-id="e420f-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="e420f-114">Параметры выбора следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="e420f-114">Next hop selection settings</span></span>

<span data-ttu-id="e420f-115">Для задания или изменения параметра **Пул узла следующего перехода**, определяющего маршрут обмена данными между пограничными серверами и внутренней инфраструктурой, выберите в раскрывающемся списке директор, пул директоров, сервер переднего плана или пул серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e420f-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="e420f-116">Для выделения будут отображаться только режиссеры и передние интерфейсы, настроенные в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="e420f-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="e420f-117">Конфигурация пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e420f-117">Edge Server configuration</span></span>

<span data-ttu-id="e420f-118">Если для пограничных серверов требуется задать или изменить значения в разделе **Внешние параметры**, необходимо сначала определить, будут ли назначены отдельные IP-адреса для доступа по протоколу SIP, для веб-конференций и для службы передачи аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="e420f-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="e420f-p103">Если планируется назначить отдельный IP-адрес для каждой службы, установите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Для каждой службы должна быть создана соответствующая запись узла (A) в службе доменных имен.</span><span class="sxs-lookup"><span data-stu-id="e420f-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="e420f-p104">Для каждой службы, обращенной к внешним сетям, следует указать полное доменное имя и связанный с ней порт. Например, для службы **Доступ SIP** были бы указаны полное доменное имя sip.contoso.com и связанный порт 5061.</span><span class="sxs-lookup"><span data-stu-id="e420f-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e420f-p105">Если вы решили использовать отдельные полные доменные имена для каждой из служб, обращенных во внешние сети, с каждой службой должен быть сопоставлено уникальное значение порта. По умолчанию SIP использует порт 5061/TLS, пограничная служба веб-конференций использует порт 444/TLS, а сервер аудио- и видеоконференций использует порт 443/TLS. Если внести какие-либо изменения любые из этих параметров, включая использование раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="e420f-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="e420f-p106">Если в организации планируется назначить единое полное доменное имя и единый IP-адрес для служб, обращенных к внешним сетям, снимите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. При необходимости значения полного доменного имени и порта для пула **Доступ SIP** можно изменить позднее.</span><span class="sxs-lookup"><span data-stu-id="e420f-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e420f-128">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="e420f-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="e420f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e420f-129">See also</span></span>

<span data-ttu-id="e420f-130">О задании и настройке параметров пограничных служб см. в разделе [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="e420f-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>



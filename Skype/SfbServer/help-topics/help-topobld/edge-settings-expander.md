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
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Чтобы изменить параметры для одного или нескольких существующих пулов пограничных серверов, можно воспользоваться следующими разделами параметров:'
ms.openlocfilehash: c2d4ec8e97557a584821bb82ef1d24b9bfa7a9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218900"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="219cd-103">Расширитель пограничных параметров</span><span class="sxs-lookup"><span data-stu-id="219cd-103">Edge Settings Expander</span></span>

<span data-ttu-id="219cd-104">Чтобы изменить параметры для одного или нескольких существующих пулов пограничных серверов, можно воспользоваться следующими разделами параметров:</span><span class="sxs-lookup"><span data-stu-id="219cd-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="219cd-105">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="219cd-105">General settings</span></span>

- <span data-ttu-id="219cd-106">Параметры выбора следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="219cd-106">Next hop selection settings</span></span>

- <span data-ttu-id="219cd-107">Конфигурация пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="219cd-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="219cd-108">Общие настройки</span><span class="sxs-lookup"><span data-stu-id="219cd-108">General settings</span></span>

<span data-ttu-id="219cd-p101">Внутреннее полное доменное имя пола пограничных серверов. Измените полное доменное имя пула, чтобы изменить данный параметр.</span><span class="sxs-lookup"><span data-stu-id="219cd-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="219cd-111">Установите флажок **включить федерацию для этого пограничного пула (порт 5061)** , если вы настроите Федерацию с помощью доверенного партнера Lync Server 2013, Microsoft Lync Server 2010 или Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="219cd-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="219cd-112">Выберите **Включить поддержку федерации XMPP для этого пограничного пула**, чтобы включить федерацию XMPP.</span><span class="sxs-lookup"><span data-stu-id="219cd-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="219cd-113">Укажите номер порта в поле **Внутренний порт репликации конфигурации (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="219cd-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="219cd-114">Параметры выбора следующего прыжка</span><span class="sxs-lookup"><span data-stu-id="219cd-114">Next hop selection settings</span></span>

<span data-ttu-id="219cd-115">Чтобы задать или изменить **пул следующего прыжка** , который будет использоваться пограничными серверами для взаимодействия с внутренней инфраструктурой, в раскрывающемся списке выберите директор, пул директоров, сервер переднего плана или пул серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="219cd-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="219cd-116">Для выбора будет отображаться только директор или интерфейсный сервер, настроенный в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="219cd-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="219cd-117">Конфигурация пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="219cd-117">Edge Server configuration</span></span>

<span data-ttu-id="219cd-118">Чтобы изменить или задать **Внешние параметры** для пограничных серверов, следует сначала определить, будете ли вы использовать IP-адреса для доступа по протоколу SIP, для веб-конференций и для службы передачи аудио- и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="219cd-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="219cd-p103">Если вы намереваетесь для каждого из компонентов использовать разные IP-адреса, установите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Для каждой службы должна быть создана соответствующая запись хоста (A) службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="219cd-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="219cd-p104">Для каждой службы, обращенной во внешние сети, укажите полное доменное имя и соответствующий порт. Например, для **Доступ SIP** можно использовать sip.contoso.com с соответствующим портом 5061.</span><span class="sxs-lookup"><span data-stu-id="219cd-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="219cd-123">Если вы решили использовать отдельные полные доменные имена для каждой из служб, обращенных во внешние сети, с каждой службой должен быть сопоставлено уникальное значение порта.</span><span class="sxs-lookup"><span data-stu-id="219cd-123">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="219cd-124">По умолчанию SIP находится в порте 5061/TLS, пограничная служба веб-конференций подключена к порту 444/TLS, а сервер аудио-и видеоконференций подключен к порту 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="219cd-124">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="219cd-125">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="219cd-125">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="219cd-p106">Если в организации будет использоваться единое полное доменное имя и IP-адрес для служб, обращенных во внешние сети, снимите флажок **Включить отдельное полное доменное имя и IP-адрес для служб веб-конференций и аудио- и видеоконференций**. Затем при необходимости можно изменить значения полного доменного имени и порта для пула **Доступ SIP**.</span><span class="sxs-lookup"><span data-stu-id="219cd-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="219cd-128">Если внести какие-либо изменения любые из этих параметров, включая использования раздельных полных доменных имен, а также IP-адресов и портов, необходимо обновить все остальные службы, которые зависят от изначально настраиваемых значений.</span><span class="sxs-lookup"><span data-stu-id="219cd-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="219cd-129">См. также</span><span class="sxs-lookup"><span data-stu-id="219cd-129">See also</span></span>

<span data-ttu-id="219cd-130">Дополнительные сведения об определении и настройке параметров для пограничных служб см. в разделе [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="219cd-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>



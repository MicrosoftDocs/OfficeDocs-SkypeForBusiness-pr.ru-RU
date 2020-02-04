---
title: Включить удаленное управление звонками
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190f4e56a291ce48b5cd18b2dcd3e1b3461e3d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="0a17e-102">Включить удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0a17e-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a17e-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0a17e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0a17e-104">Удаленное управление звонками позволяет пользователям управлять телефонными данными в частной ветви (АТС) с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a17e-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="0a17e-105">Если вы развернули удаленное управление звонками в устаревшей среде и хотите перенести его в Lync Server 2013, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0a17e-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="0a17e-106">Установите шлюз SIP/КСТА и настройте его для связи с вашей АТС.</span><span class="sxs-lookup"><span data-stu-id="0a17e-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="0a17e-107">Это действие необходимо выполнить при развертывании пула проектов Lync Server 2013 Pilot.</span><span class="sxs-lookup"><span data-stu-id="0a17e-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="0a17e-108">После того как вы объедините топологию и перенесите свои политики и параметры, настройте Lync Server 2013 для маршрутизации запросов КСТА на шлюз SIP/КСТА.</span><span class="sxs-lookup"><span data-stu-id="0a17e-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="0a17e-109">Это этап, выполняемый вручную после автоматического переноса.</span><span class="sxs-lookup"><span data-stu-id="0a17e-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="0a17e-110">Чтобы настроить маршрутизацию для запросов КСТА, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0a17e-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="0a17e-111">Удалите устаревшие авторизованные записи узла (такие как *надежные серверные* записи в Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="0a17e-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="0a17e-112">Если вы переносите пользователей из устаревшего развертывания, убедитесь, что удаляются все существующие авторизованные записи узла, созданные для шлюза SIP/КСТА, прежде чем настраивать новые записи надежных приложений в пуле Lync Server 2013 Pilot.</span><span class="sxs-lookup"><span data-stu-id="0a17e-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="0a17e-113">Подробнее об удалении устаревших авторизованных записей узла можно узнать в разделе [Удаление авторизованной записи узла](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="0a17e-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="0a17e-114">Настройте статический маршрут для удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="0a17e-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="0a17e-115">Вы можете настроить статический маршрут для отдельных пулов, которые должны поддерживать удаленное управление звонками, или настроить глобальный статический маршрут таким образом, чтобы каждый пул, не настроенный статическим маршрутом на уровне пула, применяет глобальный статический маршрут.</span><span class="sxs-lookup"><span data-stu-id="0a17e-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="0a17e-116">Подробнее о том, как настроить статический маршрут, можно найти в разделе [Настройка статического маршрута для удаленного управления звонком в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0a17e-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0a17e-117">Настройка записи надежного приложения для удаленного управления звонками в каждом пуле, для которого требуется поддерживать удаленное управление звонками.</span><span class="sxs-lookup"><span data-stu-id="0a17e-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="0a17e-118">Подробнее о том, как настроить запись надежного приложения, можно найти в разделе [Настройка надежной записи приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0a17e-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="0a17e-119">Если вы развернули шлюз SIP/КСТА, который использует протокол TCP для подключения к Lync Server 2013, укажите IP-адрес шлюза в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="0a17e-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="0a17e-120">Подробнее об определении IP-адреса можно узнать в разделе [Определение IP-адреса шлюза SIP/кста в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0a17e-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="0a17e-121">Настройка пользователей Lync 2013 для удаленного управления звонками путем включения удаленного управления звонком и назначения универсального кода ресурса (URI) и строки URI для построчного сервера.</span><span class="sxs-lookup"><span data-stu-id="0a17e-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="0a17e-122">При миграции пользователей из устаревшего развертывания на Lync Server 2013 параметры удаленного управления звонками переносятся вместе с другими параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="0a17e-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="0a17e-123">Если вы настроили правила нормализации номера телефона адресной книги в устаревшем развертывании, вам потребуется выполнить некоторые задачи вручную после того, как вы закончите автоматическое перемещение политик и параметров для миграции настроенных правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="0a17e-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="0a17e-124">Если вы не настраиваете правила нормализации, выполняется миграция адресной книги вместе с другими данными вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="0a17e-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="0a17e-125">Дополнительные сведения о переносе настроенных правил нормализации вручную см. в разделе [Миграция адресной книги](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="0a17e-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


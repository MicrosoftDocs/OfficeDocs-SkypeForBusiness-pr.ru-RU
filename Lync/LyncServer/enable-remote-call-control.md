---
title: Включение удаленного управления звонками
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa81c938d69aedbc599194c1d820fa4c40e3337
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502896"
---
# <a name="enable-remote-call-control"></a><span data-ttu-id="d0e59-102">Включение удаленного управления звонками</span><span class="sxs-lookup"><span data-stu-id="d0e59-102">Enable remote call control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0e59-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d0e59-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d0e59-104">Удаленное управление звонками позволяет пользователям управлять телефонами УАТС на рабочем столе с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0e59-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="d0e59-105">Если вы развернули удаленное управление звонками в устаревшей среде и хотите перенести его в Lync Server 2013, необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d0e59-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="d0e59-106">Установить шлюз SIP/CSTA и настроить его для связи с УАТС.</span><span class="sxs-lookup"><span data-stu-id="d0e59-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="d0e59-107">Это действие необходимо выполнить при развертывании пилотного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0e59-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="d0e59-108">После объединения топологии и переноса политик и параметров настройте Lync Server 2013 для маршрутизации запросов CSTA на шлюз SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="d0e59-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="d0e59-109">Этот шаг выполняется вручную после миграции в автоматическом режиме.</span><span class="sxs-lookup"><span data-stu-id="d0e59-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="d0e59-110">Чтобы настроить маршрутизацию CSTA-запросов, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d0e59-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="d0e59-111">Удаление устаревших авторизованных записей узла (известных как *записи доверенных серверов* в Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="d0e59-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="d0e59-112">При переносе пользователей из устаревшего развертывания убедитесь, что удалены все существующие авторизованные записи узла, созданные для шлюза SIP/CSTA, прежде чем настраивать новые записи доверенных приложений в пилотном пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0e59-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="d0e59-113">Сведения об удалении устаревших авторизованных записей узла можно найти [в разделе Удаление авторизованной записи узла](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="d0e59-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="d0e59-114">Настройте для дистанционного управления вызовами статический маршрут.</span><span class="sxs-lookup"><span data-stu-id="d0e59-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="d0e59-115">Можно настроить статический маршрут для отдельных пулов, которые согласно вашим планам должны поддерживать дистанционное управление вызовами, или можно настроить глобальный статический маршрут, чтобы каждый пул, который не сконфигурирован со статическим маршрутом на уровне пулов, использовал глобальный статический маршрут.</span><span class="sxs-lookup"><span data-stu-id="d0e59-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="d0e59-116">Сведения о настройке статического маршрута приведены в статье [Настройка статического маршрута для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d0e59-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d0e59-117">Настройте запись доверенного приложения для дистанционного управления вызовами в каждом пуле, который согласно вашим планам должен поддерживать дистанционное управление вызовами.</span><span class="sxs-lookup"><span data-stu-id="d0e59-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="d0e59-118">Подробнее о настройке записи доверенного приложения можно узнать в статье [Настройка надежной записи приложения для удаленного управления звонками в Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d0e59-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="d0e59-119">Если вы развернули шлюз SIP/CSTA, который использует протокол TCP для подключения к Lync Server 2013, определите IP-адрес шлюза в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="d0e59-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="d0e59-120">Подробнее об определении IP-адреса можно узнать в статье [Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d0e59-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="d0e59-121">Настройка пользователей Lync 2013 для удаленного управления звонками путем включения удаленного управления звонками и назначения универсального кода ресурса (URI) и линии URI для строкового сервера.</span><span class="sxs-lookup"><span data-stu-id="d0e59-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="d0e59-122">При переносе пользователей из устаревшего развертывания в Lync Server 2013 параметры удаленного управления звонками переносятся вместе с другими параметрами пользователя.</span><span class="sxs-lookup"><span data-stu-id="d0e59-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="d0e59-123">Если в унаследованном развертывании настроены правила нормализации телефонных номеров адресной книги, после завершения автоматической миграции политик и настроек требуется выполнить некоторые задачи вручную, чтобы выполнить миграцию настроенных правил нормализации.</span><span class="sxs-lookup"><span data-stu-id="d0e59-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="d0e59-124">Если правила нормализации не настраивались, миграция адресной книги выполняется вместе с остальной топологией.</span><span class="sxs-lookup"><span data-stu-id="d0e59-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="d0e59-125">Сведения о миграции вручную настроенных правил нормализации см. в разделе [Migrate Address Book](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="d0e59-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


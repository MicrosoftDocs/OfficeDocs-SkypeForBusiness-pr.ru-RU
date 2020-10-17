---
title: 'Lync Server 2013: Настройка параметров архивации'
description: 'Lync Server 2013: Настройка параметров архивации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99d57f016d76f9ae6a538ef28663a4b4c965b0a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562525"
---
# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="314b7-103">Настройка параметров архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314b7-103">Configuring Archiving options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="314b7-104">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="314b7-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="314b7-105">В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы указать способ реализации архивации.</span><span class="sxs-lookup"><span data-stu-id="314b7-105">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="314b7-106">Это включает следующие конфигурации архивирования:</span><span class="sxs-lookup"><span data-stu-id="314b7-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="314b7-107">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="314b7-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="314b7-108">Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="314b7-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="314b7-109">Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="314b7-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="314b7-110">В панели управления Lync Server 2013 вы можете использовать страницу **Конфигурация архивации** группы **Архивация и мониторинга** для управления конфигурациями на глобальном уровне, уровне сайта и на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="314b7-110">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="314b7-111">Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="314b7-111">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="314b7-112">Сведения об управлении конфигурациями после развертывания приведены в статье [Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="314b7-112">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="314b7-113">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="314b7-113">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="314b7-114">По умолчанию архивирование не включено ни для внутренней, ни для внешней связи.</span><span class="sxs-lookup"><span data-stu-id="314b7-114">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="314b7-115">Перед включением архивирования в любой политике необходимо задать подходящие конфигурации архивирования для развертывания и, если требуется, для определенных сайтов и пулов, как описано в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="314b7-115">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="314b7-116">Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="314b7-116">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="314b7-117">Если вы не используете интеграцию Microsoft Exchange для всех пользователей в развертывании, необходимо настроить политики архивации, чтобы указать, следует ли включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для обоих.</span><span class="sxs-lookup"><span data-stu-id="314b7-117">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="314b7-118">По умолчанию при использовании баз данных архивации Lync Server 2013 архивация не включена для внутренних или внешних коммуникаций для архивации данных.</span><span class="sxs-lookup"><span data-stu-id="314b7-118">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="314b7-119">Прежде чем включать архивацию в любых политиках, необходимо указать соответствующие конфигурации архивации для развертывания и, при необходимости, для конкретных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="314b7-119">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="314b7-120">Дополнительные сведения о том, как использовать архивацию для баз данных архивации Lync Server 2013, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="314b7-120">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="314b7-121">Содержание</span><span class="sxs-lookup"><span data-stu-id="314b7-121">In This Section</span></span>

  - [<span data-ttu-id="314b7-122">Настройка параметров архивации на глобальном уровне в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314b7-122">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="314b7-123">Настройка параметров архивации для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314b7-123">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="314b7-124">Настройка параметров архивации для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314b7-124">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


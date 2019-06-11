---
title: 'Lync Server 2013: Настройка параметров архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98356b53940c6189abac5a4b554769093f84dd2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="e42da-102">Настройка параметров архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42da-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e42da-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e42da-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e42da-104">В панели управления Lync Server 2013 вы можете настроить способ реализации архивации с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="e42da-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="e42da-105">К ним относятся следующие конфигурации архивации:</span><span class="sxs-lookup"><span data-stu-id="e42da-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="e42da-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e42da-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e42da-107">Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="e42da-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="e42da-108">Первоначально конфигурации архивации задаются при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания.</span><span class="sxs-lookup"><span data-stu-id="e42da-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="e42da-109">В панели управления Lync Server 2013 можно использовать страницу **Конфигурация архивации** в группе Архивация **и мониторинг** для управления конфигурациями на глобальном уровне, уровне сайта и уровне пула.</span><span class="sxs-lookup"><span data-stu-id="e42da-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="e42da-110">Сведения о способах реализации конфигураций архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, приведены в разделе [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, развертывание Документация или операционные документы.</span><span class="sxs-lookup"><span data-stu-id="e42da-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="e42da-111">Дополнительные сведения об управлении конфигурацией после развертывания можно найти в разделе [Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайты и пулы](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="e42da-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e42da-112">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для пользователей, расположенных на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e42da-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="e42da-113">По умолчанию архивация не включена для внутренней и внешней связи.</span><span class="sxs-lookup"><span data-stu-id="e42da-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="e42da-114">Перед включением архивации в любых политиках следует задать соответствующие конфигурации архивации для развертывания и (необязательно) для определенных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e42da-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="e42da-115">Подробнее о том, как включить архивацию, можно найти <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">в разделе Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e42da-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e42da-116">Если вы не используете интеграцию Microsoft Exchange для всех пользователей в развертывании, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для обоих.</span><span class="sxs-lookup"><span data-stu-id="e42da-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="e42da-117">По умолчанию при использовании баз данных Lync Server 2013 для архивации данных архивация не поддерживает внутренние и внешние сообщения.</span><span class="sxs-lookup"><span data-stu-id="e42da-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="e42da-118">Перед включением архивации в любых политиках следует задать соответствующие конфигурации архивации для развертывания и (необязательно) для определенных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e42da-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="e42da-119">Подробные сведения о том, как включить архивацию для баз данных Lync Server 2013, можно найти в разделе <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e42da-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e42da-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="e42da-120">In This Section</span></span>

  - [<span data-ttu-id="e42da-121">Настройка параметров архивации на глобальном уровне в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42da-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="e42da-122">Настройка параметров архивации для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42da-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="e42da-123">Настройка параметров архивации для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42da-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Настройка параметров архивации'
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
ms.openlocfilehash: 873b7775c889f5d866e21f04c1f154a3158ea99d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="0e9c7-102">Настройка параметров архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e9c7-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e9c7-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="0e9c7-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="0e9c7-104">В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы указать способ реализации архивации.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="0e9c7-105">Это включает следующие конфигурации архивирования:</span><span class="sxs-lookup"><span data-stu-id="0e9c7-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="0e9c7-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0e9c7-107">Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="0e9c7-108">Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="0e9c7-109">В панели управления Lync Server 2013 вы можете использовать страницу **Конфигурация архивации** группы **Архивация и мониторинга** для управления конфигурациями на глобальном уровне, уровне сайта и на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="0e9c7-110">Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="0e9c7-111">Сведения об управлении конфигурациями после развертывания приведены в статье [Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e9c7-112">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="0e9c7-113">По умолчанию архивирование не включено ни для внутренней, ни для внешней связи.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="0e9c7-114">Перед включением архивирования в любой политике необходимо задать подходящие конфигурации архивирования для развертывания и, если требуется, для определенных сайтов и пулов, как описано в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0e9c7-115">Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0e9c7-116">Если вы не используете интеграцию Microsoft Exchange для всех пользователей в развертывании, необходимо настроить политики архивации, чтобы указать, следует ли включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для обоих.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="0e9c7-117">По умолчанию при использовании баз данных архивации Lync Server 2013 архивация не включена для внутренних или внешних коммуникаций для архивации данных.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="0e9c7-118">Прежде чем включать архивацию в любых политиках, необходимо указать соответствующие конфигурации архивации для развертывания и, при необходимости, для конкретных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0e9c7-119">Дополнительные сведения о том, как использовать архивацию для баз данных архивации Lync Server 2013, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0e9c7-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e9c7-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="0e9c7-120">In This Section</span></span>

  - [<span data-ttu-id="0e9c7-121">Настройка параметров архивации на глобальном уровне в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e9c7-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="0e9c7-122">Настройка параметров архивации для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e9c7-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="0e9c7-123">Настройка параметров архивации для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e9c7-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


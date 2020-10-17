---
title: Включение или отключение архивации сеансов обмена мгновенными сообщениями или конференц-связи
description: Включение или отключение архивации сеансов обмена мгновенными сообщениями или конференц-связи.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9861024bbd4f4a1558287139a37559f782fcf008
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546535"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="f72a4-103">Включение или отключение архивации сеансов обмена мгновенными сообщениями или конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f72a4-103">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f72a4-104">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f72a4-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f72a4-105">В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы включать и отключать архивацию мгновенных сообщений, сеансов конференц-связи или и тех, и других.</span><span class="sxs-lookup"><span data-stu-id="f72a4-105">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="f72a4-106">Это включает следующие конфигурации архивирования:</span><span class="sxs-lookup"><span data-stu-id="f72a4-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f72a4-107">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f72a4-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f72a4-108">Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="f72a4-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f72a4-109">Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="f72a4-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="f72a4-110">Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="f72a4-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f72a4-111">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f72a4-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="f72a4-112">По умолчанию архивирование не включено ни для внутренней, ни для внешней связи.</span><span class="sxs-lookup"><span data-stu-id="f72a4-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="f72a4-113">Перед включением архивирования в любой политике необходимо задать подходящие конфигурации архивирования для развертывания и, если требуется, для определенных сайтов и пулов, как описано в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="f72a4-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f72a4-114">Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f72a4-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f72a4-115">Если вы решили после развертывания архивации, в которой вы хотите использовать интеграцию с Microsoft Exchange для хранения архивных данных и файлов на серверах Exchange 2013, а все пользователи размещены на серверах Exchange 2013, следует удалить конфигурацию базы данных SQL Server из топологии.</span><span class="sxs-lookup"><span data-stu-id="f72a4-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="f72a4-116">Для этого необходимо использовать построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="f72a4-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="f72a4-117">Дополнительные сведения приведены в статье <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных архивации в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="f72a4-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="f72a4-118">Включение и отключение архивации сеансов обмена мгновенными сообщениями и конференций</span><span class="sxs-lookup"><span data-stu-id="f72a4-118">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="f72a4-119">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f72a4-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f72a4-120">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f72a4-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f72a4-121">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f72a4-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f72a4-122">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="f72a4-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="f72a4-123">В списке конфигураций архивации выберите глобальную конфигурацию, конфигурацию на уровне сайта или пула, щелкните **Edit** (Изменить), щелкните **Show details** (Показать сведения) и затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f72a4-123">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="f72a4-124">Чтобы включить только архивацию сеансов обмена мгновенными сообщениями, щелкните **Archive IM sessions** (Архивировать сеансы обмена мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="f72a4-124">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="f72a4-125">Чтобы включить архивацию сеансов обмена мгновенными сообщениями и конференций, щелкните **Archive IM and conferencing sessions** (Архивировать сеансы обмена мгновенными сообщениями и конференций).</span><span class="sxs-lookup"><span data-stu-id="f72a4-125">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="f72a4-126">Чтобы отключить архивацию, щелкните **Disable archiving** (Отключить архивацию).</span><span class="sxs-lookup"><span data-stu-id="f72a4-126">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="f72a4-127">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="f72a4-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f72a4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f72a4-128">See Also</span></span>


[<span data-ttu-id="f72a4-129">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="f72a4-129">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="f72a4-130">Настройка и назначение политик архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f72a4-130">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


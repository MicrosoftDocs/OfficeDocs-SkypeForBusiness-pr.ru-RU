---
title: Включение и отключение архивирования сеансов обмена мгновенными сообщениями и конференц-связи
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
ms.openlocfilehash: be9782bfa73f30fbefaec0a51d91024b3c40ba55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="50a68-102">Включение и отключение архивирования сеансов обмена мгновенными сообщениями и конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50a68-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50a68-103">_**Тема последнего изменения:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="50a68-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="50a68-104">В панели управления Lync Server 2013 вы можете включать и отключать архивирование мгновенных сообщений, сеансов конференций и и тех, и других, с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="50a68-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="50a68-105">К ним относятся следующие конфигурации архивации:</span><span class="sxs-lookup"><span data-stu-id="50a68-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="50a68-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50a68-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="50a68-107">Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="50a68-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="50a68-108">Первоначально конфигурации архивации задаются при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания.</span><span class="sxs-lookup"><span data-stu-id="50a68-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="50a68-109">Сведения о том, как работают конфигурации архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="50a68-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="50a68-110">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для пользователей, расположенных на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50a68-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="50a68-111">По умолчанию архивация не включена для внутренней и внешней связи.</span><span class="sxs-lookup"><span data-stu-id="50a68-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="50a68-112">Перед включением архивации в любых политиках следует задать соответствующие конфигурации архивации для развертывания и (необязательно) для определенных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="50a68-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="50a68-113">Подробнее о том, как включить архивацию, можно найти <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">в разделе Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="50a68-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="50a68-114">Если вы решите, что после развертывания архивации вы хотите использовать интеграцию с Microsoft Exchange для хранения данных и файлов на серверах Exchange 2013, а все пользователи будут размещены на серверах Exchange 2013, необходимо удалить конфигурацию базы данных SQL Server. из топологии.</span><span class="sxs-lookup"><span data-stu-id="50a68-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="50a68-115">Для этого необходимо использовать Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="50a68-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="50a68-116">Подробнее смотрите в разделе <A href="lync-server-2013-changing-archiving-database-options.md">изменение параметров базы данных для архивации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="50a68-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="50a68-117">Включение и отключение архивирования сеансов обмена мгновенными сообщениями и конференц-связи</span><span class="sxs-lookup"><span data-stu-id="50a68-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="50a68-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="50a68-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50a68-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50a68-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50a68-120">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50a68-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50a68-121">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="50a68-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="50a68-122">Выберите в списке конфигураций архивации подходящую глоабальную конфигурацию либо конфигурацию сайта или пула, щелкните **Правка**, **Подробнее**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="50a68-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="50a68-123">Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, нажмите **Архивировать сеансы мгновенных сообщений**.</span><span class="sxs-lookup"><span data-stu-id="50a68-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="50a68-124">Если требуется архивировать как сеансы обмена мгновенными сообщениями, так и конференции, щелкните **Архивировать сеансы мгновенных сообщений и веб-конференций**.</span><span class="sxs-lookup"><span data-stu-id="50a68-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="50a68-125">Если требуется запретить архивацию для данной политики, щелкните **Отключить архивацию**.</span><span class="sxs-lookup"><span data-stu-id="50a68-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="50a68-126">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="50a68-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50a68-127">См. также</span><span class="sxs-lookup"><span data-stu-id="50a68-127">See Also</span></span>


[<span data-ttu-id="50a68-128">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="50a68-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="50a68-129">Настройка и назначение политик архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50a68-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Управление параметрами конфигурации архивации для Организации, сайтов и пулов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="2388b-102">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="2388b-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2388b-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2388b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2388b-104">В панели управления Lync Server 2013 вы можете настроить способ реализации архивации с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="2388b-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="2388b-105">К ним относятся следующие конфигурации архивации:</span><span class="sxs-lookup"><span data-stu-id="2388b-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="2388b-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2388b-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2388b-107">Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="2388b-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="2388b-108">Первоначально конфигурации архивации задаются при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания.</span><span class="sxs-lookup"><span data-stu-id="2388b-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="2388b-109">В панели управления Lync Server 2013 можно использовать страницу **Конфигурация архивации** в группе Архивация **и мониторинг** для управления конфигурациями на глобальном уровне, уровне сайта и уровне пула.</span><span class="sxs-lookup"><span data-stu-id="2388b-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="2388b-110">Сведения о том, как работают конфигурации архивации, в том числе доступные для выбора параметры и иерархию конфигураций архивации, описаны [в разделе как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, развертывание Документация или операционные документы.</span><span class="sxs-lookup"><span data-stu-id="2388b-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2388b-111">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы указать, следует ли включать архивирование для внутренней связи, для внешней связи или для всех пользователей, расположенных на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2388b-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="2388b-112">По умолчанию архивация не включена для внутренней и внешней связи.</span><span class="sxs-lookup"><span data-stu-id="2388b-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="2388b-113">Если вы используете Microsoft Exchange Integration, вы должны включить и настроить Exchange 2013 для поддержки архивирования для всех пользователей, использующих Exchange 2013 с почтовыми ящиками, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="2388b-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="2388b-114">Перед включением архивации следует задать соответствующие конфигурации архивации для развертывания и, при необходимости, для определенных сайтов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2388b-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="2388b-115">Подробнее о том, как включить архивацию, можно найти <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">в разделе Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2388b-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="2388b-116">**Просмотр сведений о конфигурации архивации с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2388b-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="2388b-117">Вы можете просматривать сведения о конфигурации архивации с помощью Windows PowerShell и командлета **Get-ксарчивингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="2388b-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="2388b-118">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2388b-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2388b-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2388b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="2388b-120">В командной консоли Lync Server выполните следующую команду, чтобы просмотреть сведения о всех параметрах конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="2388b-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="2388b-121">Содержание</span><span class="sxs-lookup"><span data-stu-id="2388b-121">In This Section</span></span>

  - [<span data-ttu-id="2388b-122">Создание конфигурации архивации в Lync Server 2013 для управления архивированием определенных сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="2388b-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="2388b-123">Включение и отключение архивирования сеансов обмена мгновенными сообщениями и конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2388b-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="2388b-124">Включение и отключение очистки архивированных данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2388b-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="2388b-125">Включение и отключение критического режима в Lync Server 2013 для блокирования и разрешения сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации</span><span class="sxs-lookup"><span data-stu-id="2388b-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [<span data-ttu-id="2388b-126">Включение и отключение отправки отказа от архивирования федеративным партнерам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2388b-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="2388b-127">Включение и отключение интеграции Lync Server 2013 с хранилищем Exchange</span><span class="sxs-lookup"><span data-stu-id="2388b-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="2388b-128">Удаление конфигурации архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2388b-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2388b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2388b-129">See Also</span></span>


[<span data-ttu-id="2388b-130">Управление архивированием Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2388b-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


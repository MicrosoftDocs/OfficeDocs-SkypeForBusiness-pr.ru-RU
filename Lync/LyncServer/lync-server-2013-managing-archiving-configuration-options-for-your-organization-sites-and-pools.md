---
title: 'Lync Server 2013: Управление параметрами конфигурации архивации для Организации, сайтов и пулов'
description: 'Lync Server 2013: Управление параметрами конфигурации архивации для Организации, сайтов и пулов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576625"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="0da64-103">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="0da64-103">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0da64-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0da64-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0da64-105">В панели управления Lync Server 2013 вы можете использовать конфигурации архивации, чтобы указать способ реализации архивации.</span><span class="sxs-lookup"><span data-stu-id="0da64-105">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="0da64-106">Это включает следующие конфигурации архивирования:</span><span class="sxs-lookup"><span data-stu-id="0da64-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="0da64-107">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0da64-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0da64-108">Необязательные конфигурации на уровне сайта или пула, которые можно создать и использовать для указания того, как архивирование реализуется для определенных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="0da64-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="0da64-109">Начальная настройка конфигураций архивирования производится во время развертывания архивирования, но вы можете изменить, добавить и удалить конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="0da64-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="0da64-110">В панели управления Lync Server 2013 вы можете использовать страницу **Конфигурация архивации** группы **Архивация и мониторинга** для управления конфигурациями на глобальном уровне, уровне сайта и на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="0da64-110">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="0da64-111">Сведения о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать, а также иерархия конфигураций архивации, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="0da64-111">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0da64-112">Чтобы использовать архивацию, необходимо настроить политики архивации, чтобы включить архивацию для внутренних коммуникаций, для внешних коммуникаций или для всех пользователей, размещенных в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0da64-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="0da64-113">По умолчанию архивирование не включено ни для внутренней, ни для внешней связи.</span><span class="sxs-lookup"><span data-stu-id="0da64-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="0da64-114">При использовании интеграции с Microsoft Exchange необходимо включить и настроить Exchange 2013 для поддержки архивации всех пользователей, размещенных на сервере Exchange 2013 с почтовыми ящиками, на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="0da64-114">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="0da64-115">Перед включением архивации необходимо указать соответствующие конфигурации архивации для вашего развертывания и, при необходимости, для определенных узлов и пулов, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0da64-115">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="0da64-116">Подробнее о том, как настроить архивацию, можно узнать в статье <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Настройка и назначение политик архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0da64-116">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0da64-117">**Просмотр сведений о конфигурации архивации с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0da64-117">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="0da64-118">Сведения о конфигурации архивации можно просмотреть с помощью Windows PowerShell и командлета **Get – CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0da64-118">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="0da64-119">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0da64-119">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0da64-120">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="0da64-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="0da64-121">Чтобы просмотреть сведения о всех параметрах конфигурации архивации, в командной консоли Lync Server используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0da64-121">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="0da64-122">Содержание</span><span class="sxs-lookup"><span data-stu-id="0da64-122">In This Section</span></span>

  - [<span data-ttu-id="0da64-123">Создание конфигурации архивации в Lync Server 2013 для управления архивацией определенных сайтов или пулов</span><span class="sxs-lookup"><span data-stu-id="0da64-123">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="0da64-124">Включение или отключение архивации сеансов обмена мгновенными сообщениями или конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da64-124">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="0da64-125">Включение или отключение очистки архивных данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da64-125">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="0da64-126">Включение или отключение критического режима в Lync Server 2013 для блокировки и разрешения сеансов обмена мгновенными сообщениями и веб-конференций в случае сбоя архивации</span><span class="sxs-lookup"><span data-stu-id="0da64-126">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="0da64-127">Включение или отключение отправки заявления об отказе от архивации федеративным партнерам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da64-127">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="0da64-128">Включение или отключение интеграции Lync Server 2013 с хранилищем Exchange</span><span class="sxs-lookup"><span data-stu-id="0da64-128">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="0da64-129">Удаление конфигурации архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da64-129">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0da64-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0da64-130">See Also</span></span>


[<span data-ttu-id="0da64-131">Управление архивированием Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da64-131">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


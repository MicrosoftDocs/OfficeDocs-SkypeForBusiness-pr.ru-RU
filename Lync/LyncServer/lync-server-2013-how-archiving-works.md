---
title: 'Lync Server 2013: принцип работы архивации'
description: 'Lync Server 2013: как работает архивация.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543385"
---
# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="760f6-103">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="760f6-103">How Archiving works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="760f6-104">_**Последнее изменение темы:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="760f6-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="760f6-105">Lync Server 2013 Архивация предоставляет варианты, которые помогут вам обеспечить соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="760f6-105">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="760f6-106">Чтобы реализовать и сохранить его в соответствии с требованиями вашей организации, необходимо ознакомиться с:</span><span class="sxs-lookup"><span data-stu-id="760f6-106">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="760f6-107">какая информация может архивироваться;</span><span class="sxs-lookup"><span data-stu-id="760f6-107">What information can be archived.</span></span>

  - <span data-ttu-id="760f6-108">как включить и отключить архивацию в развертывании;</span><span class="sxs-lookup"><span data-stu-id="760f6-108">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="760f6-109">параметры архивации, которые можно настраивать для управления реализацией архивации.</span><span class="sxs-lookup"><span data-stu-id="760f6-109">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="760f6-110">Какая информация может архивироваться?</span><span class="sxs-lookup"><span data-stu-id="760f6-110">What Information Can Be Archived?</span></span>

<span data-ttu-id="760f6-111">Следующие типы содержимого могут быть заархивированы:</span><span class="sxs-lookup"><span data-stu-id="760f6-111">The following types of content can be archived:</span></span>

  - <span data-ttu-id="760f6-112">одноранговые мгновенные сообщения;</span><span class="sxs-lookup"><span data-stu-id="760f6-112">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="760f6-113">конференции (собрания), которые являются сеансами обмена мгновенными сообщениями между несколькими сторонами;</span><span class="sxs-lookup"><span data-stu-id="760f6-113">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="760f6-114">содержимое конференций, включая загруженное содержимого (например, раздаточные материалы), и связанное с событиями содержание (например, сведения о присоединении, выходе, загрузке, общем доступе и изменениях видимости);</span><span class="sxs-lookup"><span data-stu-id="760f6-114">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="760f6-115">доски и общие опросы конференции.</span><span class="sxs-lookup"><span data-stu-id="760f6-115">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="760f6-116">Следующие типы содержимого не могут быть заархивированы:</span><span class="sxs-lookup"><span data-stu-id="760f6-116">The following types of content are not archived:</span></span>

  - <span data-ttu-id="760f6-117">одноранговые передачи файлов;</span><span class="sxs-lookup"><span data-stu-id="760f6-117">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="760f6-118">аудио/видео для одноранговых мгновенных сообщений и конференций;</span><span class="sxs-lookup"><span data-stu-id="760f6-118">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="760f6-119">совместное использование рабочего стола и приложений для одноранговых мгновенных сообщений и конференций.</span><span class="sxs-lookup"><span data-stu-id="760f6-119">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="760f6-120">Lync Server также не архивирует беседы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="760f6-120">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="760f6-121">Чтобы архивировать беседы сохраняемого чата, необходимо включить и настроить службу соответствия требованиям, которая является компонентом, который можно развернуть с помощью сервера Microsoft Lync Server 2013, сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="760f6-121">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="760f6-122">Дополнительные сведения приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="760f6-122">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="760f6-123">Как начать использовать архивацию?</span><span class="sxs-lookup"><span data-stu-id="760f6-123">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="760f6-p103">Архивация автоматически устанавливается на каждом интерфейсном сервере при развертывании сервера, но архивация не включается, пока ее не настроить. Способ настройки определяется тем, как как развертывается служба архивации:</span><span class="sxs-lookup"><span data-stu-id="760f6-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="760f6-126">**Архивация с использованием интеграции с Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="760f6-126">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="760f6-127">Если у вас есть пользователи, размещенные в Exchange 2013 и их почтовые ящики, размещенные на In-Place хранения, можно выбрать вариант интеграции хранилища Lync Server 2013 с хранилищем Exchange.</span><span class="sxs-lookup"><span data-stu-id="760f6-127">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="760f6-128">Если вы выбрали вариант интеграции с Microsoft Exchange, вы используете политики и конфигурации Exchange 2013 для управления архивацией данных Lync Server 2013 для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="760f6-128">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="760f6-129">**Архивация с помощью баз данных архивации Lync Server.**</span><span class="sxs-lookup"><span data-stu-id="760f6-129">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="760f6-130">Если у вас есть пользователи, не размещенные в Exchange 2013 или у которых нет почтовых ящиков на In-Place хранения, или если вы не хотите использовать интеграцию Microsoft Exchange для любых или всех пользователей в развертывании, вы можете развернуть базы данных архивации Lync Server с помощью SQL Server для хранения архивных данных для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="760f6-130">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="760f6-131">В этом случае в Lync Server 2013 политики архивации и конфигурации определяют, включено ли архивирование и как она реализована.</span><span class="sxs-lookup"><span data-stu-id="760f6-131">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="760f6-132">Чтобы использовать Lync Server 2013, необходимо добавить соответствующие базы данных SQL Server в топологию и опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="760f6-132">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="760f6-133">Настройка архивации при использовании интеграции с Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="760f6-133">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="760f6-134">Если пользователи размещены в Exchange 2013 и их почтовые ящики помещаются на In-Place удержание, можно выбрать вариант **интеграции с Microsoft Exchange** (как описано далее в этом разделе), чтобы архивировать Lync Server 2013 для этих пользователей, а затем управлять архивацией для этих пользователей, указав политики и параметры хранения Exchange In-Place, а также конфигурации Lync Server для управления следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="760f6-134">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="760f6-135">следует ли архивировать мгновенные сообщения, конференции или и то, и другие;</span><span class="sxs-lookup"><span data-stu-id="760f6-135">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="760f6-136">Следует ли реализовать критический режим для развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="760f6-136">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="760f6-137">Выбор варианта интеграции Microsoft Exchange для использования Exchange 2013 для хранения архивных данных.</span><span class="sxs-lookup"><span data-stu-id="760f6-137">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="760f6-138">Эти параметры конфигурации архивации Lync Server 2013 описаны далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="760f6-138">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="760f6-139">Сведения о настройке политик и параметров хранения Exchange In-Place для поддержки архивации можно найти в документации по продукту Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="760f6-139">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="760f6-140">Настройка архивации при использовании хранилища базы данных архивации Lync Server</span><span class="sxs-lookup"><span data-stu-id="760f6-140">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="760f6-141">Если вы хотите использовать базы данных архивации Lync Server (с помощью баз данных SQL Server) для архивации данных для всех пользователей в вашем развертывании, можно настроить политики архивации Lync Server, чтобы управлять включением архивации для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="760f6-141">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="760f6-142">В каждой политике архивации можно включить или отключить архивацию для одного или обоих следующих типов данных:</span><span class="sxs-lookup"><span data-stu-id="760f6-142">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="760f6-143">внутренние коммуникации;</span><span class="sxs-lookup"><span data-stu-id="760f6-143">Internal communications</span></span>

  - <span data-ttu-id="760f6-144">внешние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="760f6-144">External communications</span></span>

<span data-ttu-id="760f6-145">По умолчанию архивация не включена для внутренней связи или внешних коммуникаций во всех политиках архивации Lync Server.</span><span class="sxs-lookup"><span data-stu-id="760f6-145">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="760f6-146">Вы включаете и отключаете связь с помощью панели управления Lync Server 2013 или с помощью командлетов в командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="760f6-146">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="760f6-147">В качестве политики архивирования Lync Server 2013 входят следующие:</span><span class="sxs-lookup"><span data-stu-id="760f6-147">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="760f6-148">**Глобальная политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="760f6-148">**Global Archiving policy**.</span></span> <span data-ttu-id="760f6-149">Это политика архивации по умолчанию, которая применяется ко всему развертыванию.</span><span class="sxs-lookup"><span data-stu-id="760f6-149">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="760f6-150">Он создается при развертывании Lync Server 2013 и, по умолчанию, отключает архивацию для внутренних и внешних коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="760f6-150">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="760f6-151">Эту политику нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="760f6-151">You cannot delete this policy.</span></span> <span data-ttu-id="760f6-152">Если вы решили удалить этот параметр, восстанавливаются параметры глобальной политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="760f6-152">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="760f6-p110">**Политика архивации сайта**. При необходимости можно включить или отключить архивацию для одного или нескольких сайтов, создав и настроив политику архивации на уровне сайта. При создании политики архивации на уровне сайта архивация по умолчанию не включена. Вы можете удалить любую политику архивации на уровне сайта, которую вы создали. Политика архивации на уровне сайта переопределяет глобальную политику, но только для сайта, указанного в политике. Например, если включить архивацию для внутренних и внешних коммуникаций в глобальной политике и создать политику сайта, которая отключает архивацию для внешних коммуникаций, для этого сайта будут архивироваться только внутренние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="760f6-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="760f6-p111">**Политика архивации пользователя**. При необходимости можно включить или отключить архивацию для одного или нескольких пользователей и групп пользователей, создавая, настраивая и применяя политику архивации на уровне пользователя для указанных пользователей и групп пользователей. При создании политики архивации на уровне пользователя архивация по умолчанию не включена. Можно удалить любую созданную вами политику архивации на уровне пользователя и можно изменить пользователей и групп пользователей, к которым применяется политика архивации. Политика архивации на уровне пользователя переопределяет глобальную политику и любые политики сайта, но только для пользователей и групп пользователей, к которым применяется политика. Например, если отключить архивацию для внутренних и внешних коммуникаций в глобальной политике, создать политику на уровне сайта, в которой включается архивация для внутренних и внешних коммуникаций, а затем создать политику на уровне пользователя, в которой отключается архивация внешних коммуникаций, то будут архивироваться внешние и внутренние коммуникации для всех пользователей сайта, но для пользователей, к которым применяется политика на уровне пользователей, будут архивироваться только внутренние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="760f6-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="760f6-165">Сведения о настройке начальных политик архивации при развертывании архивации приведены в статье [Настройка и назначение политик архивации в Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="760f6-165">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="760f6-166">Сведения о том, как использовать политики архивации для включения и отключения связи после развертывания, можно узнать в статье [Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="760f6-166">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="760f6-167">Если вы реализуете базы данных архивации Lync Server 2013 и разрешите интеграцию Microsoft Exchange, политики Exchange 2013 переопределяют политики архивации Lync Server, но только для пользователей, размещенных в Exchange 2013 и почтовые ящики помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="760f6-167">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="760f6-168">Архивация в Lync зависит только от политики хранения In-Place Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="760f6-168">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="760f6-169">Какие существуют параметры для настройки архивации?</span><span class="sxs-lookup"><span data-stu-id="760f6-169">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="760f6-170">Помимо применения политик и возможности включать и отключать архивацию существующие другие параметры архивации, которые можно настроить для всего развертывания и, при необходимости, для определенных сайтов и пулов.</span><span class="sxs-lookup"><span data-stu-id="760f6-170">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="760f6-171">Для управления большинством параметров архивации можно использовать одну или несколько конфигураций архивации, которые доступны в панели управления Lync Server 2013, но Кроме того, можно использовать другой вариант, который доступен только для конфигурации с помощью командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="760f6-171">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="760f6-172">Параметры конфигурации архивации, доступные на панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="760f6-172">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="760f6-173">Каждая конфигурация архивации предоставляет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="760f6-173">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="760f6-p115">Конфигурация глобального уровня создается автоматически при развертывании архивации и ее можно настроить, но нельзя удалить. Если выбран параметр удаления глобальной конфигурации, восстанавливаются значения по умолчанию. Можно создать несколько конфигураций сайтов и пулов, которые вместе с глобальной конфигурацией управляют настройками архивации. Для глобальной конфигурации и конфигурации каждого сайта и пула доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="760f6-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="760f6-178">отключить архивацию, включить архивацию только для обмена мгновенными сообщениями или включить архивацию для мгновенных сообщений и конференций;</span><span class="sxs-lookup"><span data-stu-id="760f6-178">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="760f6-179">Настройка критического режима для блокировки сеансов обмена мгновенными сообщениями и конференц-связи в случае сбоя сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="760f6-179">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="760f6-180">К сбоям относятся следующие события:</span><span class="sxs-lookup"><span data-stu-id="760f6-180">Failures include the following:</span></span>
    
      - <span data-ttu-id="760f6-181">**Обмен мгновенными сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="760f6-181">**IM**.</span></span> <span data-ttu-id="760f6-182">Проблема со службой хранилища Lync Server.</span><span class="sxs-lookup"><span data-stu-id="760f6-182">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="760f6-183">В этом случае мгновенные сообщения заблокированы для пользователей, которым доступна архивация.</span><span class="sxs-lookup"><span data-stu-id="760f6-183">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="760f6-p118">**Конференции**. Сбоем может быть недоступный общий ресурс или проблема со службой хранения. В этом случае все активные конференции, размещенные в пуле на момент сбоя, переводятся в ограниченный режим, после чего можно активировать новые конференции.</span><span class="sxs-lookup"><span data-stu-id="760f6-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="760f6-187">Сеансы обмена мгновенными сообщениями и конференции автоматически восстанавливаются после устранения ошибок.</span><span class="sxs-lookup"><span data-stu-id="760f6-187">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="760f6-188">Указание использования интеграции Microsoft Exchange Server 2013 для хранения архивных данных с помощью Exchange 2013 вместо настройки отдельных баз данных SQL Server для хранения данных архивации Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="760f6-188">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="760f6-p119">Настройте параметры очистки для архивированных данных. Для этого также необходимо определить время очистки архивированных данных:</span><span class="sxs-lookup"><span data-stu-id="760f6-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="760f6-191">после определенного количества дней, которое следует указать;</span><span class="sxs-lookup"><span data-stu-id="760f6-191">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="760f6-192">После экспорта данных архивации (включая данные, которые были отправлены в Exchange, если включена интеграция с Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="760f6-192">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="760f6-193">Если вы включаете интеграцию с Microsoft Exchange, очистка для пользователей, размещенных в Exchange 2013 и почтовых ящиков, размещается на In-Place удержание управляется Exchange.</span><span class="sxs-lookup"><span data-stu-id="760f6-193">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="760f6-194">Единственное уточнение — для файлов конференций, которые хранятся на общем файловом ресурсе Lync Server.</span><span class="sxs-lookup"><span data-stu-id="760f6-194">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="760f6-195">Эти файлы удаляются из файлового хранилища только после того, как эти файлы экспортированы (отправлены в Exchange), если выбран параметр удаления данных после экспортирования архивных данных; или после заданного числа дней, если задан параметр числа дней хранения.</span><span class="sxs-lookup"><span data-stu-id="760f6-195">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="760f6-196">По умолчанию все параметры архивации отключены.</span><span class="sxs-lookup"><span data-stu-id="760f6-196">By default, no archiving options are enabled.</span></span> <span data-ttu-id="760f6-197">Вы можете управлять конфигурациями архивации с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="760f6-197">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="760f6-198">Вы можете задать следующие конфигурации архивации:</span><span class="sxs-lookup"><span data-stu-id="760f6-198">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="760f6-199">**Глобальная конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="760f6-199">**Global Archiving configuration**.</span></span> <span data-ttu-id="760f6-200">Это конфигурация архивации по умолчанию, которая применяется ко всему развертыванию.</span><span class="sxs-lookup"><span data-stu-id="760f6-200">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="760f6-201">Он создается при развертывании Lync Server 2013 и, по умолчанию, не включает функции архивации.</span><span class="sxs-lookup"><span data-stu-id="760f6-201">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="760f6-202">Вы можете изменить глобальную конфигурацию, но не можете удалить ее.</span><span class="sxs-lookup"><span data-stu-id="760f6-202">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="760f6-203">Если вы решите удалить конфигурацию, будут восстановлены параметры конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="760f6-203">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="760f6-p123">**Конфигурация архивации сайта**. При необходимости вы можете настроить архивацию для одного или нескольких сайтов, создав и настроив конфигурацию архивацию на уровне сайта для отдельного сайта. Конфигурация архивации на уровне сайта существует только, если ее создать. Вы можете изменить или удалить любую конфигурация архивации на уровне сайта. Конфигурация архивации на уровне сайта переопределяет глобальную конфигурацию, но только для сайта, указанного в конфигурации на уровне сайта. Например, если включить архивацию только для обмена мгновенными сообщениями в глобальной конфигурации и создать конфигурацию, в которой включена архивация для обмена мгновенными сообщениями и конференций, то конференции будут архивироваться только для сайта, а не не оставшейся части организации.</span><span class="sxs-lookup"><span data-stu-id="760f6-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="760f6-p124">**Конфигурация архивации пула**. При необходимости можно указать параметры архивации для одного или нескольких пулов, создав и настроив конфигурацию для отдельного пула. Конфигурация уровня пула существует только, если ее создать. Вы можете изменить или удалить любую конфигурация архивации на уровне пула. Конфигурация архивации на уровне пула переопределяет глобальную конфигурацию и все созданные конфигурации сайта. Например, если включить архивацию только для обмена мгновенными сообщениями в глобальной конфигурации и создать конфигурацию уровня сайта, в которой архивация включена для обмена мгновенными сообщениями и конференций, а затем создать конфигурацию уровня пула, в которой архивация включена только для мгновенных сообщений, коммуникации будут архивироваться для обмена мгновенными сообщениями и конференций для всех пользователей сайта, за исключением пользователей, размещенных в пуле, указанном в конфигурации уровня пула. Для всех других пользователей архивация включена только для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="760f6-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="760f6-217">Сведения о настройке начальных конфигураций архивации при развертывании архивации приведены в статье [Настройка параметров архивации в Lync Server 2013](lync-server-2013-configuring-archiving-options.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="760f6-217">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="760f6-218">Сведения об использовании политик архивации для включения и отключения связи после развертывания можно найти [в статье Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="760f6-218">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="760f6-219">Параметры архивации, доступные только в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="760f6-219">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="760f6-220">Используя командную консоль Lync Server 2013, вы можете использовать командлеты для реализации параметров, недоступных в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="760f6-220">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="760f6-221">К ним относятся следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="760f6-221">These options include the following:</span></span>

  - <span data-ttu-id="760f6-222">**Архивация повторяющихся сообщений**.</span><span class="sxs-lookup"><span data-stu-id="760f6-222">**Archive duplicate messages**.</span></span> <span data-ttu-id="760f6-223">Дополнительные сведения см. в статьях [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) и [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="760f6-223">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="760f6-224">**Экспорт архивированных данных**.</span><span class="sxs-lookup"><span data-stu-id="760f6-224">**Export archived data**.</span></span> <span data-ttu-id="760f6-225">Дополнительные сведения см. в разделе [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span><span class="sxs-lookup"><span data-stu-id="760f6-225">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="760f6-226">Как получить доступ к архивированным данным?</span><span class="sxs-lookup"><span data-stu-id="760f6-226">How Do I Access Archived Data?</span></span>

<span data-ttu-id="760f6-227">Доступ к архивированным данным зависит от места хранения данных:</span><span class="sxs-lookup"><span data-stu-id="760f6-227">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="760f6-228">**Хранилище Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="760f6-228">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="760f6-229">Если выбран параметр интеграция Exchange, Lync Server выполняет объединение содержимого архивации в хранилище Exchange 2013 для всех пользователей, размещенных в Exchange 2013, и почтовые ящики на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="760f6-229">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="760f6-230">Архивные данные хранятся в папке "элементы для восстановления почтовых ящиков", которая, как правило, не видна пользователям, и может выполнять поиск только по пользователям с ролью **управления обнаружением** Exchange.</span><span class="sxs-lookup"><span data-stu-id="760f6-230">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="760f6-231">Exchange включает федеративный поиск и обнаружение, а также SharePoint, если он развернут.</span><span class="sxs-lookup"><span data-stu-id="760f6-231">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="760f6-232">Дополнительные сведения о хранении, хранении и обнаружении данных, хранящихся в Exchange, можно найти в документации по Exchange 2013 и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="760f6-232">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="760f6-233">**Хранилище Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="760f6-233">**Lync Server storage**.</span></span> <span data-ttu-id="760f6-234">Если вы настроили базы данных архивации Lync Server 2013 для хранения данных Lync Server, то Lync Server депозитные данные для архивации в базах данных архивации Lync Server (базы данных SQL Server) для всех пользователей, которые не размещены в Exchange 2013, а их почтовые ящики не помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="760f6-234">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="760f6-235">Эти данные недоступны для поиска, но их можно экспортировать в форматы, доступные для поиска с использованием других средств.</span><span class="sxs-lookup"><span data-stu-id="760f6-235">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="760f6-236">Подробные сведения об экспорте данных, хранящихся в базах данных архивации, приведены в статье [Экспорт архивных данных из Lync Server 2013](lync-server-2013-exporting-archived-data.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="760f6-236">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="760f6-237">Для получения дополнительных сведений о том, как Lync Server 2013 и Exchange 2013 работают совместно, ознакомьтесь со статьей [Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="760f6-237">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


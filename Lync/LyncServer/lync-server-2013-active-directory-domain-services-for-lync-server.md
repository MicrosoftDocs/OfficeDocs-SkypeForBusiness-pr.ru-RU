---
title: 'Lync Server 2013: доменные службы Active Directory для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b53b878d7f41a5eb83eb67d98fc69d68709a603
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="afe6c-102">Доменные службы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afe6c-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afe6c-103">_**Последнее изменение темы:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="afe6c-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="afe6c-104">Доменные службы Active Directory функционируют как служба каталогов для сетей Windows Server 2003, Windows Server 2008, Windows Server 2012 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="afe6c-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="afe6c-105">Доменные службы Active Directory также служат основой, на которой строится инфраструктура безопасности Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afe6c-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="afe6c-106">В этом разделе описывается, как Lync Server 2013 использует доменные службы Active Directory для создания надежной среды для обмена мгновенными сообщениями, веб-конференций, мультимедиа и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="afe6c-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="afe6c-107">Дополнительные сведения о расширениях Lync Server для доменных служб Active Directory и подготовке среды для доменных служб Active Directory приведены в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="afe6c-108">Сведения о роли доменных служб Active Directory в сетях Windows Server представлены в документации по используемой версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="afe6c-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="afe6c-109">Lync Server 2013 использует доменные службы Active Directory для хранения следующих данных:</span><span class="sxs-lookup"><span data-stu-id="afe6c-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="afe6c-110">Глобальные параметры, необходимые для всех серверов, на которых работает Lync Server 2013 в лесу.</span><span class="sxs-lookup"><span data-stu-id="afe6c-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="afe6c-111">Сведения о службе, определяющие роли всех серверов, на которых работает Lync Server 2013, в лесу.</span><span class="sxs-lookup"><span data-stu-id="afe6c-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="afe6c-112">Некоторые параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="afe6c-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="afe6c-113">Инфраструктура Active Directory</span><span class="sxs-lookup"><span data-stu-id="afe6c-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="afe6c-114">Требования к инфраструктуре для Active Directory включают следующее:</span><span class="sxs-lookup"><span data-stu-id="afe6c-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="afe6c-115">Требования к операционной системе для контроллеров домена</span><span class="sxs-lookup"><span data-stu-id="afe6c-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="afe6c-116">Требования к функциональным уровням домена и леса</span><span class="sxs-lookup"><span data-stu-id="afe6c-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="afe6c-117">Требования к домену глобального каталога</span><span class="sxs-lookup"><span data-stu-id="afe6c-117">Global catalog domain requirements</span></span>

<span data-ttu-id="afe6c-118">Дополнительные сведения см в статье [требования к инфраструктуре Active Directory для Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="afe6c-119">Подготовка доменных служб Active Directory</span><span class="sxs-lookup"><span data-stu-id="afe6c-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afe6c-120">Рекомендуется развертывать глобальные параметры в контейнере конфигурации, а не в контейнере System.</span><span class="sxs-lookup"><span data-stu-id="afe6c-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="afe6c-121">Это не повышает безопасность, но может привести к улучшениям масштабируемости некоторых топологий доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="afe6c-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="afe6c-122">Если вы выполняете миграцию с Microsoft Office Communications Server 2007 и использовали системный контейнер, но планируете использовать контейнер конфигурации, необходимо переместить параметры из контейнера System перед выполнением любых подготовительных действий по обновлению.</span><span class="sxs-lookup"><span data-stu-id="afe6c-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="afe6c-123">Чтобы перенести параметры контейнера системы в контейнер конфигурации, ознакомьтесь со статьей средство миграции глобальных параметров Office Communications Server 2007 <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>на сайте.</span><span class="sxs-lookup"><span data-stu-id="afe6c-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="afe6c-124">При развертывании Lync Server 2013 первым этапом является подготовка доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="afe6c-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="afe6c-125">Подготовка доменных служб Active Directory для Lync Server 2013 состоит из следующих трех этапов:</span><span class="sxs-lookup"><span data-stu-id="afe6c-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="afe6c-126">**Подготовка схемы**.</span><span class="sxs-lookup"><span data-stu-id="afe6c-126">**Prepare Schema**.</span></span> <span data-ttu-id="afe6c-127">Эта задача расширяет схему в доменных службах Active Directory, чтобы включить классы и атрибуты, характерные для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afe6c-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="afe6c-128">Подробнее о подготовке схемы можно узнать в статье [Выполнение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="afe6c-129">Для получения дополнительных сведений обратитесь [к разделу миграция с Office Communications Server 2007 R2 на Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="afe6c-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="afe6c-130">**Подготовка леса**.</span><span class="sxs-lookup"><span data-stu-id="afe6c-130">**Prepare Forest**.</span></span> <span data-ttu-id="afe6c-131">Эта задача создает глобальные параметры и объекты в корневом домене леса, а также универсальную службу и административные группы, которые управляют доступом к этим параметрам и объектам.</span><span class="sxs-lookup"><span data-stu-id="afe6c-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="afe6c-132">Подробнее о подготовке леса можно узнать в документации по развертыванию, посвященной [подготовке лесов для Lync Server 2013](lync-server-2013-running-forest-preparation.md) .</span><span class="sxs-lookup"><span data-stu-id="afe6c-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="afe6c-133">**Подготовка домена**.</span><span class="sxs-lookup"><span data-stu-id="afe6c-133">**Prepare Domain**.</span></span> <span data-ttu-id="afe6c-134">Эта задача добавляет необходимые записи управления доступом (ACE) в универсальные группы, которые предоставляют разрешения для размещения пользователей в домене и управления ими.</span><span class="sxs-lookup"><span data-stu-id="afe6c-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="afe6c-135">Эту задачу необходимо выполнить во всех доменах, где необходимо развернуть серверы Lync Server 2013 и все домены, в которых находятся пользователи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="afe6c-136">Подробнее о подготовке домена можно узнать в документации по развертыванию: [Выполнение подготовки домена для Lync Server 2013](lync-server-2013-running-domain-preparation.md) .</span><span class="sxs-lookup"><span data-stu-id="afe6c-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="afe6c-137">Общие сведения о подготовке Active Directory и правах и разрешениях, необходимых для выполнения каждого этапа, приведены в статье [требования к инфраструктуре Active Directory для Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="afe6c-138">Универсальные группы</span><span class="sxs-lookup"><span data-stu-id="afe6c-138">Universal Groups</span></span>

<span data-ttu-id="afe6c-139">Во время подготовки леса Lync Server 2013 создает различные универсальные группы в доменных службах Active Directory, которые имеют разрешение на доступ к глобальным параметрам и службам и управление ими.</span><span class="sxs-lookup"><span data-stu-id="afe6c-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="afe6c-140">К этим универсальным группам относятся:</span><span class="sxs-lookup"><span data-stu-id="afe6c-140">These universal groups include:</span></span>

  - <span data-ttu-id="afe6c-141">**Административные группы**.</span><span class="sxs-lookup"><span data-stu-id="afe6c-141">**Administrative groups**.</span></span> <span data-ttu-id="afe6c-142">Эти группы определяют основные роли администратора для сети Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="afe6c-143">Во время подготовки леса эти группы администраторов добавляются в группы инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="afe6c-144">**Группы служб**.</span><span class="sxs-lookup"><span data-stu-id="afe6c-144">**Service groups**.</span></span> <span data-ttu-id="afe6c-145">Эти группы являются учетными записями служб, необходимыми для доступа к различным службам, предоставляемым Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="afe6c-146">**Группы инфраструктуры**.</span><span class="sxs-lookup"><span data-stu-id="afe6c-146">**Infrastructure groups**.</span></span> <span data-ttu-id="afe6c-147">Эти группы предоставляют разрешение на доступ к определенным областям инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="afe6c-148">Они работают как компоненты административных групп и не должны изменять их или добавлять пользователей в них напрямую.</span><span class="sxs-lookup"><span data-stu-id="afe6c-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="afe6c-149">Во время подготовки леса определенные группы служб и администрирования добавляются в соответствующие группы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="afe6c-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="afe6c-150">Для получения дополнительных сведений об определенных универсальных группах, созданных при подготовке AD для Lync Server, а также о группах служб и администраторов, которые добавляются в группы инфраструктуры, ознакомьтесь [с изменениями, внесенными при подготовке леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) , в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afe6c-151">Lync Server 2013 поддерживает универсальные группы в Windows Server 2012 для серверов, на которых работает Lync Server 2013, а также операционные системы Windows Server 2003 для контроллеров домена.</span><span class="sxs-lookup"><span data-stu-id="afe6c-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="afe6c-152">Участниками универсальных групп могут быть другие группы и учетные записи из любого домена в дереве доменов или лесу и могут получать разрешения в любом домене в дереве доменов или лесу.</span><span class="sxs-lookup"><span data-stu-id="afe6c-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="afe6c-153">Поддержка универсальных групп, в сочетании с делегированием прав администратора, упрощает управление развертыванием Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="afe6c-154">Например, не нужно добавлять один домен к другому, чтобы разрешить администратору управлять обоими.</span><span class="sxs-lookup"><span data-stu-id="afe6c-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="afe6c-155">Управление доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="afe6c-155">Role-Based Access Control</span></span>

<span data-ttu-id="afe6c-156">В дополнение к созданию универсальных групп служб и администрирования и добавлению групп служб и администрирования в соответствующие универсальные группы, при подготовке леса также создаются группы управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="afe6c-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="afe6c-157">Подробные сведения об определенных группах RBAC, созданных при подготовке леса, приведены в статье [изменения, внесенные в ходе подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="afe6c-158">Дополнительные сведения о группах RBAC см. в статье [Управление доступом на основе ролей (RBAC) для Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="afe6c-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="afe6c-159">Записи управления доступом (ACE) и наследование</span><span class="sxs-lookup"><span data-stu-id="afe6c-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="afe6c-160">При подготовке леса создаются частные и общедоступные записи ACE, а также добавляются записи ACE для универсальных групп, которые он создает.</span><span class="sxs-lookup"><span data-stu-id="afe6c-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="afe6c-161">Он создает определенные частные записи ACE в контейнере глобальных параметров, используемом Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afe6c-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="afe6c-162">Этот контейнер используется только Lync Server и находится в контейнере конфигурации или в контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="afe6c-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="afe6c-163">На этапе подготовки домена необходимые элементы управления доступом (ACE) добавляются в универсальные группы, которые предоставляют разрешения для размещения пользователей в домене и управления ими.</span><span class="sxs-lookup"><span data-stu-id="afe6c-163">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="afe6c-164">При подготовке домена создаются элементы управления доступом в корне домена и три встроенных контейнера: пользователей, компьютеров и контроллеров домена.</span><span class="sxs-lookup"><span data-stu-id="afe6c-164">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="afe6c-165">Для получения сведений о общедоступных элементах управления доступом, созданных и добавленных при подготовке леса и подготовке домена, ознакомьтесь с [изменениями, выполненными при подготовке леса в Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) , и [внесите изменения в подготовку доменов в Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="afe6c-166">Организации часто блокируют доменные службы Active Directory (AD DS), чтобы снизить риски безопасности.</span><span class="sxs-lookup"><span data-stu-id="afe6c-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="afe6c-167">Однако заблокированная среда Active Directory может ограничить разрешения, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afe6c-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="afe6c-168">Это может быть удаление записей ACE из контейнеров и подразделений, а также отключение наследования разрешений для объектов User, Contact, InetOrgPerson или Computer.</span><span class="sxs-lookup"><span data-stu-id="afe6c-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="afe6c-169">В заблокированной среде Active Directory разрешения необходимо задать вручную для контейнеров и подразделений, которым они требуются.</span><span class="sxs-lookup"><span data-stu-id="afe6c-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="afe6c-170">Дополнительные сведения приведены в статье [Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="afe6c-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="afe6c-171">Сведения о сервере</span><span class="sxs-lookup"><span data-stu-id="afe6c-171">Server Information</span></span>

<span data-ttu-id="afe6c-172">Во время активации Lync Server 2013 публикует сведения о сервере в трех следующих расположениях в доменных службах Active Directory:</span><span class="sxs-lookup"><span data-stu-id="afe6c-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="afe6c-173">Точка подключения службы (SCP) на каждом объекте компьютера Active Directory, соответствующем физическому компьютеру, на котором установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afe6c-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="afe6c-174">Объекты сервера, созданные в контейнере класса **msRTCSIP — Pools** .</span><span class="sxs-lookup"><span data-stu-id="afe6c-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="afe6c-175">Доверенные серверы, указанные в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="afe6c-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="afe6c-176">Точки подключения службы</span><span class="sxs-lookup"><span data-stu-id="afe6c-176">Service Connection Points</span></span>

<span data-ttu-id="afe6c-177">Каждый объект Lync Server 2013 в доменных службах Active Directory имеет точку подключения службы RTC, которая, в свою очередь, содержит несколько атрибутов, которые определяют каждый компьютер и указывают предоставляемые им службы.</span><span class="sxs-lookup"><span data-stu-id="afe6c-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="afe6c-178">Среди наиболее важных атрибутов SCP — *сервицеднснаме*, *сервицеднснаметипе*, *сервицекласснаме*и *сервицебиндингинформатион*.</span><span class="sxs-lookup"><span data-stu-id="afe6c-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="afe6c-179">Сторонние приложения управления активами могут получать сведения о сервере во всем развертывании, запрашивая эти и другие атрибуты SCP.</span><span class="sxs-lookup"><span data-stu-id="afe6c-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="afe6c-180">Объекты сервера Active Directory</span><span class="sxs-lookup"><span data-stu-id="afe6c-180">Active Directory Server Objects</span></span>

<span data-ttu-id="afe6c-181">Каждая роль сервера Lync Server 2013 имеет соответствующий объект Active Directory, атрибуты которого определяют службы, предоставляемые этой ролью.</span><span class="sxs-lookup"><span data-stu-id="afe6c-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="afe6c-182">Кроме того, при активации сервера Standard Edition или при создании пула Enterprise Edition в Lync Server 2013 создается новый объект **msRTCSIP-Pool** в контейнере **msRTCSIP-Pools** .</span><span class="sxs-lookup"><span data-stu-id="afe6c-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="afe6c-183">Класс **msRTCSIP-Pool** указывает полное доменное имя (FQDN) пула, а также связь между интерфейсными и внутренними компонентами пула.</span><span class="sxs-lookup"><span data-stu-id="afe6c-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="afe6c-184">(Сервер Standard Edition рассматривается как логический пул, передний и задний концом которого размещены на одном компьютере.)</span><span class="sxs-lookup"><span data-stu-id="afe6c-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="afe6c-185">Доверенные серверы</span><span class="sxs-lookup"><span data-stu-id="afe6c-185">Trusted Servers</span></span>

<span data-ttu-id="afe6c-186">В Lync Server 2013 доверенные серверы задаются при запуске построителя топологий и публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="afe6c-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="afe6c-187">Опубликованная топология, в том числе вся информация о сервере, хранится в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="afe6c-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="afe6c-188">Только серверы, определенные в центральном хранилище управления, являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="afe6c-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="afe6c-189">В Lync Server 2013 доверенный сервер — это один, который отвечает следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="afe6c-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="afe6c-190">Полное доменное имя сервера находится в топологии, хранящейся в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="afe6c-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="afe6c-191">Сервер предоставляет действительный сертификат от доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="afe6c-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="afe6c-192">Дополнительные сведения см в статье [требования к инфраструктуре сертификатов для Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afe6c-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="afe6c-193">Если один из этих критериев отсутствует, значит, сервер не является доверенным и подключение к нему отклонено.</span><span class="sxs-lookup"><span data-stu-id="afe6c-193">If either of these criteria is missing, the server is not trusted and connection with it is refused.</span></span> <span data-ttu-id="afe6c-194">Это двойное требование предотвращает возможную атаку, при которой незаконный сервер пытается пройти через допустимое полное доменное имя сервера.</span><span class="sxs-lookup"><span data-stu-id="afe6c-194">This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="afe6c-195">Кроме того, чтобы включить развертывание Microsoft Office Communications Server 2007 R2 и Microsoft Office Communications Server 2007 для связи с серверами Lync Server 2013, Lync Server 2013 создает контейнеры во время подготовки леса для хранения списков Доверенные серверы для предыдущих выпусков.</span><span class="sxs-lookup"><span data-stu-id="afe6c-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="afe6c-196">В следующей таблице описываются контейнеры, созданные для обеспечения совместимости с предыдущими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="afe6c-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="afe6c-197">Списки доверенных серверов и их контейнеры Active Directory для обеспечения совместимости с предыдущими выпусками</span><span class="sxs-lookup"><span data-stu-id="afe6c-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afe6c-198">Список доверенных серверов</span><span class="sxs-lookup"><span data-stu-id="afe6c-198">Trusted server list</span></span></th>
<th><span data-ttu-id="afe6c-199">Контейнер Active Directory</span><span class="sxs-lookup"><span data-stu-id="afe6c-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afe6c-200">Серверы Standard Edition и серверы переднего плана корпоративного пула</span><span class="sxs-lookup"><span data-stu-id="afe6c-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="afe6c-201">Служба RTC/глобальные параметры</span><span class="sxs-lookup"><span data-stu-id="afe6c-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afe6c-202">Серверы конференций</span><span class="sxs-lookup"><span data-stu-id="afe6c-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="afe6c-203">Служба RTC/Доверенная MCUs</span><span class="sxs-lookup"><span data-stu-id="afe6c-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afe6c-204">Серверы веб-компонентов</span><span class="sxs-lookup"><span data-stu-id="afe6c-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="afe6c-205">Служба RTC/Трустедвебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="afe6c-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afe6c-206">Серверы-посредники и серверы веб-клиента Communicator, сервер приложений, регистратор с QoE, служба аудио-и видеоконференций (также сторонние серверы SIP)</span><span class="sxs-lookup"><span data-stu-id="afe6c-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="afe6c-207">Служба RTC и Доверенные службы</span><span class="sxs-lookup"><span data-stu-id="afe6c-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afe6c-208">Прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="afe6c-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="afe6c-209">Lync Server 2013 не поддерживает обратную совместимость для прокси-серверов</span><span class="sxs-lookup"><span data-stu-id="afe6c-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="afe6c-210">Для поддержки доверенных серверов предыдущих выпусков необходимо запустить анализатор соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="afe6c-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="afe6c-211">Подробные сведения о запуске анализатора соответствия рекомендациям приведены [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)в разделе.</span><span class="sxs-lookup"><span data-stu-id="afe6c-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


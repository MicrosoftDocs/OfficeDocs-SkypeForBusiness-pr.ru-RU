---
title: 'Lync Server 2013: доменные службы Active Directory для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="8abd9-102">Доменные службы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8abd9-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8abd9-103">_**Тема последнего изменения:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="8abd9-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="8abd9-104">Доменные службы Active Directory функционируют как служба каталогов для сетей Windows Server 2003, Windows Server 2008, Windows Server 2012 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8abd9-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="8abd9-105">Доменные службы Active Directory также служат основой, на которой построена инфраструктура безопасности Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8abd9-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="8abd9-106">Цель этого раздела — описать, как в Lync Server 2013 используются доменные службы Active Directory для создания надежной среды для обмена сообщениями, веб-конференций, мультимедиа и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8abd9-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="8abd9-107">Дополнительные сведения о расширениях Lync Server для доменных служб Active Directory и о том, как подготовить среду для доменных служб Active Directory, можно найти в разделе [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) в развертывании содержатся.</span><span class="sxs-lookup"><span data-stu-id="8abd9-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="8abd9-108">Подробные сведения о роли доменных служб Active Directory в сетях Windows Server можно найти в документации по используемой версии операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8abd9-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="8abd9-109">Lync Server 2013 использует доменные службы Active Directory для хранения следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8abd9-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="8abd9-110">Глобальные параметры, необходимые для всех серверов с Lync Server 2013 в лесу.</span><span class="sxs-lookup"><span data-stu-id="8abd9-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="8abd9-111">Сведения о службе, определяющие роли всех серверов, на которых работает Lync Server 2013 в лесу.</span><span class="sxs-lookup"><span data-stu-id="8abd9-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="8abd9-112">некоторые пользовательские параметры.</span><span class="sxs-lookup"><span data-stu-id="8abd9-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="8abd9-113">Инфраструктура службы каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="8abd9-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="8abd9-114">Требования к инфраструктуре для Active Directory включают следующее:</span><span class="sxs-lookup"><span data-stu-id="8abd9-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="8abd9-115">требования к ОС для доменных контроллеров;</span><span class="sxs-lookup"><span data-stu-id="8abd9-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="8abd9-116">требования для функциональных уровней домена и леса;</span><span class="sxs-lookup"><span data-stu-id="8abd9-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="8abd9-117">требования для домена глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="8abd9-117">Global catalog domain requirements</span></span>

<span data-ttu-id="8abd9-118">Дополнительные сведения можно найти в разделе [требования к инфраструктуре службы каталогов Active Directory для Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="8abd9-119">Подготовка доменных служб Active Directory</span><span class="sxs-lookup"><span data-stu-id="8abd9-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8abd9-120">Рекомендуется развертывать глобальные параметры в контейнере конфигурации, а не в контейнере System.</span><span class="sxs-lookup"><span data-stu-id="8abd9-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="8abd9-121">Это не повышает безопасность, но может привести к увеличению масштабируемости для некоторых топологий доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8abd9-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="8abd9-122">Если вы переходите с Microsoft Office Communications Server 2007 и используете системный контейнер, но планируете использовать контейнер конфигурации, необходимо переместить параметры в контейнере системы перед выполнением каких бы то ни было подготовительных действий по обновлению.</span><span class="sxs-lookup"><span data-stu-id="8abd9-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="8abd9-123">Чтобы перенести параметры контейнера системы в контейнер конфигурации, ознакомьтесь с разстройкой средства миграции глобальных параметров Office Communications Server <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>2007 по адресу.</span><span class="sxs-lookup"><span data-stu-id="8abd9-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="8abd9-124">При развертывании Lync Server 2013 первым этапом является подготовка доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8abd9-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="8abd9-125">Подготовка доменных служб Active Directory для Lync Server 2013 включает в себя следующие три этапа:</span><span class="sxs-lookup"><span data-stu-id="8abd9-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="8abd9-126">**Подготовьте схему**.</span><span class="sxs-lookup"><span data-stu-id="8abd9-126">**Prepare Schema**.</span></span> <span data-ttu-id="8abd9-127">Эта задача расширяет схему доменных служб Active Directory, включая классы и атрибуты, специфичные для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8abd9-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="8abd9-128">Подробнее о подготовке схемы можно узнать в разделе [Выполнение подготовки схемы Active Directory в Lync Server 2013](lync-server-2013-running-schema-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="8abd9-129">Дополнительные сведения можно найти в разделе [Переход с Office Communications Server 2007 R2 на Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8abd9-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="8abd9-130">**Подготовка леса**.</span><span class="sxs-lookup"><span data-stu-id="8abd9-130">**Prepare Forest**.</span></span> <span data-ttu-id="8abd9-131">Эта задача создает глобальные параметры и объекты в корневом домене леса, а также универсальную службу и группы администраторов, которые определяют доступ к этим параметрам и объектам.</span><span class="sxs-lookup"><span data-stu-id="8abd9-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="8abd9-132">Подробнее о том, как подготовить лес, можно найти в разделе [Выполнение подготовки леса для Lync Server 2013](lync-server-2013-running-forest-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8abd9-133">**Подготовка домена**.</span><span class="sxs-lookup"><span data-stu-id="8abd9-133">**Prepare Domain**.</span></span> <span data-ttu-id="8abd9-134">Эта задача добавляет необходимые элементы управления доступом (ACE) в универсальные группы, предоставляющие разрешения на размещение пользователей и управление ими в пределах домена.</span><span class="sxs-lookup"><span data-stu-id="8abd9-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="8abd9-135">Эта задача должна быть выполнена во всех доменах, где вы хотите развернуть серверы Lync Server 2013 и домены, в которых находятся пользователи сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="8abd9-136">Дополнительные сведения о подготовке домена можно найти в разделе [Выполнение подготовки домена для Lync Server 2013](lync-server-2013-running-domain-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8abd9-137">Общие сведения о подготовке Active Directory, а также о правах и разрешениях, необходимых для выполнения каждого этапа, приведены в статье [требования к инфраструктуре службы каталогов Active Directory для Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="8abd9-138">Универсальные группы</span><span class="sxs-lookup"><span data-stu-id="8abd9-138">Universal Groups</span></span>

<span data-ttu-id="8abd9-139">Во время подготовки леса Lync Server 2013 создает различные универсальные группы в доменных службах Active Directory, которые имеют разрешение на доступ к глобальным параметрам и службам и управление ими.</span><span class="sxs-lookup"><span data-stu-id="8abd9-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="8abd9-140">Универсальные группы делятся на следующие группы:</span><span class="sxs-lookup"><span data-stu-id="8abd9-140">These universal groups include:</span></span>

  - <span data-ttu-id="8abd9-141">**административные группы**.</span><span class="sxs-lookup"><span data-stu-id="8abd9-141">**Administrative groups**.</span></span> <span data-ttu-id="8abd9-142">Эти группы определяют роли основных администраторов для сети Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="8abd9-143">Во время подготовки леса эти группы администраторов добавляются в группы инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="8abd9-144">**группы обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="8abd9-144">**Service groups**.</span></span> <span data-ttu-id="8abd9-145">Эти группы представляют собой учетные записи служб, необходимые для доступа к различным службам, предоставляемым Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="8abd9-146">**группы инфраструктур**.</span><span class="sxs-lookup"><span data-stu-id="8abd9-146">**Infrastructure groups**.</span></span> <span data-ttu-id="8abd9-147">Эти группы предоставляют разрешения на доступ к определенным областям инфраструктуры Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="8abd9-148">Они работают как компоненты административных групп; не следует изменять их или добавлять в них пользователей непосредственно.</span><span class="sxs-lookup"><span data-stu-id="8abd9-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="8abd9-149">При подготовке леса определенные группы обслуживания и администрирования добавляются в соответствующие группы инфраструктур.</span><span class="sxs-lookup"><span data-stu-id="8abd9-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="8abd9-150">Подробные сведения о конкретных универсальных группах, созданных при подготовке AD для Lync Server, а также о группах обслуживания и администрирования, добавленных в группы инфраструктуры, приведены в разделе [изменения, внесенные в процессе подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) в Документация по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8abd9-151">Lync Server 2013 поддерживает универсальные группы в Windows Server 2012 для серверов с Lync Server 2013, а также операционных систем Windows Server 2003 для контроллеров домена.</span><span class="sxs-lookup"><span data-stu-id="8abd9-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="8abd9-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span><span class="sxs-lookup"><span data-stu-id="8abd9-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="8abd9-153">Поддержка универсальной группы в сочетании с делегированием администратора упрощает управление развертыванием Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="8abd9-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span><span class="sxs-lookup"><span data-stu-id="8abd9-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="8abd9-155">Управление доступом на основе ролей</span><span class="sxs-lookup"><span data-stu-id="8abd9-155">Role-Based Access Control</span></span>

<span data-ttu-id="8abd9-156">Кроме создания универсальных групп обслуживания и администрирования и добавления этих групп в соответствующие универсальные группы, подготовка леса также создает группы управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8abd9-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="8abd9-157">Подробные сведения о конкретных группах RBAC, созданных с помощью подготовки леса, приведены в разделе [изменения подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="8abd9-158">Дополнительные сведения о группах RBAC можно найти в разделе [Управление доступом на основе ролей (RBAC) для Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="8abd9-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="8abd9-159">Записи управления доступом (ACE) и наследование</span><span class="sxs-lookup"><span data-stu-id="8abd9-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="8abd9-160">В процессе подготовки леса создаются частные и общедоступные записи ACE, а также создаются записи ACE универсальных групп при их добавлении.</span><span class="sxs-lookup"><span data-stu-id="8abd9-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="8abd9-161">Она создает определенные закрытые записи в контейнере глобальных параметров, используемом в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8abd9-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="8abd9-162">Этот контейнер используется только приложением Lync Server и находится в контейнере Configuration или контейнере System в корневом домене в зависимости от того, где хранятся глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="8abd9-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="8abd9-p114">На этапе подготовки домена в универсальные группы добавляются необходимые записи управления доступом (ACE), которые предоставляют разрешения для размещения и управления пользователями в домене. При подготовке домена создаются записи ACE в корне домена и три встроенных контейнера: пользователи, компьютеры и контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="8abd9-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="8abd9-165">Дополнительные сведения об открытых ACE, созданных и добавленных с помощью подготовки леса и подготовки домена, приведены в разделе [изменения подготовки домена в Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) и [изменения, внесенные с помощью подготовки доменов в Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) в развертывании содержатся.</span><span class="sxs-lookup"><span data-stu-id="8abd9-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8abd9-166">Организации часто блокируют доменные службы Active Directory (AD DS), чтобы снизить риски безопасности.</span><span class="sxs-lookup"><span data-stu-id="8abd9-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="8abd9-167">Однако заблокированная среда Active Directory может ограничивать разрешения, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8abd9-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="8abd9-168">Это может включать в себя записи ACE из контейнеров и подразделений, а также отключение разрешений наследования для объектов пользователя, контакта, InetOrgPerson или компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8abd9-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="8abd9-169">В заблокированной среде Active Directory разрешения должны быть установлены вручную в контейнерах и подразделениях, в которых они необходимы.</span><span class="sxs-lookup"><span data-stu-id="8abd9-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="8abd9-170">Дополнительные сведения можно найти [в разделе Подготовка заблокированных доменных служб Active Directory в Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8abd9-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="8abd9-171">Информация о сервере</span><span class="sxs-lookup"><span data-stu-id="8abd9-171">Server Information</span></span>

<span data-ttu-id="8abd9-172">Во время активации Lync Server 2013 публикует сведения о сервере в трех указанных ниже папках доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8abd9-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="8abd9-173">Точка подключения службы (SCP) для каждого объекта компьютера Active Directory, соответствующего физическому компьютеру, на котором установлено приложение Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8abd9-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="8abd9-174">объекты сервера, созданные в контейнере класса **msRTCSIP-Pools**;</span><span class="sxs-lookup"><span data-stu-id="8abd9-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="8abd9-175">Доверенные серверы, указанные в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="8abd9-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="8abd9-176">Точки подключения служб</span><span class="sxs-lookup"><span data-stu-id="8abd9-176">Service Connection Points</span></span>

<span data-ttu-id="8abd9-177">Каждый объект Lync Server 2013 в доменных службах Active Directory имеет точку обслуживания служб RTC, которая, в свою очередь, содержит несколько атрибутов, которые определяют каждый компьютер и указывают предоставляемые им службы.</span><span class="sxs-lookup"><span data-stu-id="8abd9-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="8abd9-178">Более важные атрибуты SCP включают в себя \*serviceDNSName \*, \*serviceDNSNameType \*, \*serviceClassname \* и *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="8abd9-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="8abd9-179">Сторонние приложения по управлению активами могут извлекать информацию о сервере в развертывании путем выдачи запросов по отношению этих и других атрибутов SCP.</span><span class="sxs-lookup"><span data-stu-id="8abd9-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="8abd9-180">Объекты сервера службы каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="8abd9-180">Active Directory Server Objects</span></span>

<span data-ttu-id="8abd9-181">Каждая серверная роль Lync Server 2013 имеет соответствующий объект Active Directory, атрибуты которого определяют службы, предоставленные этой ролью.</span><span class="sxs-lookup"><span data-stu-id="8abd9-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="8abd9-182">Кроме того, при активации стандартного сервера выпусков или создании пула Enterprise Edition Lync Server 2013 создает новый объект **пула msRTCSIP** в контейнере **msRTCSIP-Pools** .</span><span class="sxs-lookup"><span data-stu-id="8abd9-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="8abd9-183">Класс \*\*msRTCSIP-Pool \*\* указывает полное доменное имя пула и сопоставление между компонентами переднего плана и встроенными компонентами пула.</span><span class="sxs-lookup"><span data-stu-id="8abd9-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="8abd9-184">(Сервер Standard Edition рассматривается как логический пул, передний и задний концов которого выровнены на одном компьютере.)</span><span class="sxs-lookup"><span data-stu-id="8abd9-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="8abd9-185">Доверенные серверы</span><span class="sxs-lookup"><span data-stu-id="8abd9-185">Trusted Servers</span></span>

<span data-ttu-id="8abd9-186">В Lync Server 2013 при запуске Topology Builder и публикации топологии вы задаете доверенные серверы.</span><span class="sxs-lookup"><span data-stu-id="8abd9-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="8abd9-187">Опубликованная топология, включая все сведения сервера, сохраняется в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="8abd9-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="8abd9-188">Только серверы, определенные в центральном хранилище управления, являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="8abd9-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="8abd9-189">В Lync Server 2013 доверенный сервер — это один из указанных ниже критериев.</span><span class="sxs-lookup"><span data-stu-id="8abd9-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="8abd9-190">Полное доменное имя сервера встречается в топологии, сохраненной в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="8abd9-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="8abd9-191">Сервер предоставляет действительный сертификат от доверенного ЦС.</span><span class="sxs-lookup"><span data-stu-id="8abd9-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="8abd9-192">Дополнительные сведения можно найти в разделе [требования к инфраструктуре сертификатов для Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8abd9-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="8abd9-p120">При отсутствии любого из этих критериев сервер не является доверенным, а при подключении приходит отказ. Это двойное требование предотвращает возможную атаку, в которой незаконный сервер пытается присвоить себе полное доменное имя действительного сервера.</span><span class="sxs-lookup"><span data-stu-id="8abd9-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="8abd9-195">Кроме того, чтобы включить в развертывание Microsoft Office Communications Server 2007 R2 и Microsoft Office Communications Server 2007 связь с серверами Lync Server 2013, Lync Server 2013 создает контейнеры во время подготовки леса для хранения списков Доверенные серверы для предыдущих выпусков.</span><span class="sxs-lookup"><span data-stu-id="8abd9-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="8abd9-196">В таблице ниже описаны контейнеры, созданные для обеспечения совместимости с предыдущими развертываниями.</span><span class="sxs-lookup"><span data-stu-id="8abd9-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="8abd9-197">Списки надежных серверов и их контейнеры Active Directory для обеспечения совместимости с предыдущими выпусками</span><span class="sxs-lookup"><span data-stu-id="8abd9-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8abd9-198">Список доверенных серверов</span><span class="sxs-lookup"><span data-stu-id="8abd9-198">Trusted server list</span></span></th>
<th><span data-ttu-id="8abd9-199">Контейнер Active Directory</span><span class="sxs-lookup"><span data-stu-id="8abd9-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8abd9-200">Серверы стандартного выпуска и серверы переднего плана пула Enterprise</span><span class="sxs-lookup"><span data-stu-id="8abd9-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8abd9-201">Служба RTC Service/глобальные параметры</span><span class="sxs-lookup"><span data-stu-id="8abd9-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abd9-202">Серверы для конференций</span><span class="sxs-lookup"><span data-stu-id="8abd9-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="8abd9-203">Служба RTC Service/доверенные MCU</span><span class="sxs-lookup"><span data-stu-id="8abd9-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abd9-204">Серверы веб-компонентов</span><span class="sxs-lookup"><span data-stu-id="8abd9-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="8abd9-205">Служба RTC Service/доверенные серверы веб-компонентов</span><span class="sxs-lookup"><span data-stu-id="8abd9-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8abd9-206">Серверы-посредники и серверы веб-клиента Communicator, сервер приложений, регистратор с качеством взаимодействия, служба аудио- и видеоконференции (а также сторонние серверы SIP)</span><span class="sxs-lookup"><span data-stu-id="8abd9-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="8abd9-207">Служба RTC Service/доверенные службы</span><span class="sxs-lookup"><span data-stu-id="8abd9-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8abd9-208">Прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="8abd9-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="8abd9-209">Lync Server 2013 не поддерживает обратную совместимость с прокси-серверами</span><span class="sxs-lookup"><span data-stu-id="8abd9-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8abd9-210">Для поддержки доверенных серверов предыдущих выпусков необходимо запустить анализатор соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="8abd9-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="8abd9-211">Подробные сведения о том, как запустить анализатор соответствия рекомендациям, можно найти в разделе [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span><span class="sxs-lookup"><span data-stu-id="8abd9-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


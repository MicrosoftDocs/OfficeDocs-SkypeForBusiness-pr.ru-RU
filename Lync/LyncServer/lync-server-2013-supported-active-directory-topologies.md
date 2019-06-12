---
title: 'Lync Server 2013: поддерживаемые топологии Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="38af8-102">Поддерживаемые топологии Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38af8-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38af8-103">_**Тема последнего изменения:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="38af8-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="38af8-104">Lync Server 2013 поддерживает те же топологии доменных служб Active Directory, что и Microsoft Lync Server 2010 и Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="38af8-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="38af8-105">Поддерживаются следующие топологии:</span><span class="sxs-lookup"><span data-stu-id="38af8-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="38af8-106">Один лес с одним доменом</span><span class="sxs-lookup"><span data-stu-id="38af8-106">Single forest with single domain</span></span>

  - <span data-ttu-id="38af8-107">Один лес с одним деревом и несколькими доменами</span><span class="sxs-lookup"><span data-stu-id="38af8-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="38af8-108">Один лес с несколькими деревьями и несвязанными пространствами имен</span><span class="sxs-lookup"><span data-stu-id="38af8-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="38af8-109">Несколько лесов в топологии с центральным лесом</span><span class="sxs-lookup"><span data-stu-id="38af8-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="38af8-110">Несколько лесов в топологии с лесом ресурсов</span><span class="sxs-lookup"><span data-stu-id="38af8-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="38af8-111">Несколько лесов в топологии леса ресурсов Lync с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38af8-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="38af8-112">На приведенном ниже рисунке показаны значки, используемые на иллюстрациях в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="38af8-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="38af8-113">**Основные примеры топологии**</span><span class="sxs-lookup"><span data-stu-id="38af8-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="38af8-114">![Основные примеры топологии] (images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Основные примеры топологии")</span><span class="sxs-lookup"><span data-stu-id="38af8-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="38af8-115">Один лес, один домен</span><span class="sxs-lookup"><span data-stu-id="38af8-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="38af8-116">Самой простой топологией службы каталогов Active Directory, поддерживаемой Lync Server и одним лесом домена, является общая топология.</span><span class="sxs-lookup"><span data-stu-id="38af8-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="38af8-117">На приведенном ниже рисунке показано развертывание Lync Server в топологии с единым доменом Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38af8-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="38af8-118">**Топология с одним доменом**</span><span class="sxs-lookup"><span data-stu-id="38af8-118">**Single domain topology**</span></span>

<span data-ttu-id="38af8-119">![Топология с одним доменом] (images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Топология с одним доменом")</span><span class="sxs-lookup"><span data-stu-id="38af8-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="38af8-120">Один лес, несколько доменов</span><span class="sxs-lookup"><span data-stu-id="38af8-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="38af8-121">Другая топология службы каталогов Active Directory, поддерживаемая Lync Server, — это один лес, состоящий из корневого домена и одного или нескольких дочерних доменов.</span><span class="sxs-lookup"><span data-stu-id="38af8-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="38af8-122">В этом типе топологии службы каталогов Active Directory домен, в котором создаются пользователи, может отличаться от домена, на котором развертывается сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38af8-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="38af8-123">Однако при развертывании пула переднего плана необходимо развернуть все серверы переднего плана в пуле в пределах одного домена.</span><span class="sxs-lookup"><span data-stu-id="38af8-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="38af8-124">Поддержка групп Windows Universal Administrators в Lync Server обеспечивает междоменное администрирование.</span><span class="sxs-lookup"><span data-stu-id="38af8-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="38af8-125">На приведенном ниже рисунке показано развертывание в одном лесе с несколькими доменами.</span><span class="sxs-lookup"><span data-stu-id="38af8-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="38af8-126">На этом рисунке на значке пользователя показан домен, в котором расположена учетная запись пользователя, а стрелка указывает на домен, в котором находится пул Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38af8-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="38af8-127">Учетные записи пользователей включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="38af8-127">User accounts include the following:</span></span>

  - <span data-ttu-id="38af8-128">Учетные записи пользователей в рамках того же домена, что и пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="38af8-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="38af8-129">Учетные записи пользователей в другом домене из пула Lync Server</span><span class="sxs-lookup"><span data-stu-id="38af8-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="38af8-130">Учетные записи пользователей в дочернем домене домена с пулом серверов Lync Server</span><span class="sxs-lookup"><span data-stu-id="38af8-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="38af8-131">**Один лес с несколькими доменами**</span><span class="sxs-lookup"><span data-stu-id="38af8-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="38af8-132">![Один лес с несколькими доменами] (images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Один лес с несколькими доменами")</span><span class="sxs-lookup"><span data-stu-id="38af8-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="38af8-133">Один лес, несколько деревьев</span><span class="sxs-lookup"><span data-stu-id="38af8-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="38af8-134">Топология леса с несколькими деревом состоит из двух или более доменов, которые определяют независимые древовидные структуры и различные пространства имен Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38af8-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="38af8-135">На приведенном ниже рисунке показан один лес с несколькими деревьями.</span><span class="sxs-lookup"><span data-stu-id="38af8-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="38af8-136">На этом рисунке на значке пользователя показан домен, в котором расположена учетная запись пользователя, сплошная линия указывает на пул Lync Server, который находится в том же или другом домене, и пунктирная линия указывает на пул Lync Server, который находится в другом дереве.</span><span class="sxs-lookup"><span data-stu-id="38af8-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="38af8-137">Учетные записи пользователей включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="38af8-137">User accounts include the following:</span></span>

  - <span data-ttu-id="38af8-138">Учетные записи пользователей в рамках того же домена, что и пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="38af8-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="38af8-139">Учетные записи пользователей из другого домена (но с тем же деревом, что и в составе пула Lync Server)</span><span class="sxs-lookup"><span data-stu-id="38af8-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="38af8-140">Учетные записи пользователей в другом дереве из пула Lync Server</span><span class="sxs-lookup"><span data-stu-id="38af8-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="38af8-141">**Один лес с несколькими деревьями**</span><span class="sxs-lookup"><span data-stu-id="38af8-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="38af8-142">![Один лес с несколькими деревьями] (images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Один лес с несколькими деревьями")</span><span class="sxs-lookup"><span data-stu-id="38af8-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="38af8-143">Несколько лесов, Центральный лес</span><span class="sxs-lookup"><span data-stu-id="38af8-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="38af8-144">Lync Server поддерживает несколько лесов, настроенных в топологии центрального леса.</span><span class="sxs-lookup"><span data-stu-id="38af8-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="38af8-145">Топологии центрального леса используют объекты контактов в центральном лесе для представления пользователей в других лесах.</span><span class="sxs-lookup"><span data-stu-id="38af8-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="38af8-146">В центральном лесу также размещаются учетные записи пользователей для всех пользователей в этом лесу.</span><span class="sxs-lookup"><span data-stu-id="38af8-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="38af8-147">Продукт для синхронизации каталогов, например сервер интеграции удостоверений (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 или Диспетчер жизненного цикла удостоверений (FP1) 2007 (с пакетом управления жизненным циклом пользователей), управляет жизненным циклом пользовательских учетных записей в Организация: при создании новой учетной записи пользователя в одном из лесов или удалении учетной записи пользователя из леса программа синхронизации каталогов синхронизирует соответствующий контакт в центральном лесе.</span><span class="sxs-lookup"><span data-stu-id="38af8-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="38af8-148">У центрального леса есть следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="38af8-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="38af8-149">Серверы Lync Server централизованно находятся в одном лесе.</span><span class="sxs-lookup"><span data-stu-id="38af8-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="38af8-150">Пользователи могут выполнять поиск и связь с другими пользователями в любом лесе.</span><span class="sxs-lookup"><span data-stu-id="38af8-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="38af8-151">Пользователи могут просматривать сведения о присутствии других пользователей в любом лесе.</span><span class="sxs-lookup"><span data-stu-id="38af8-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="38af8-152">Продукт для синхронизации каталогов автоматизирует добавление и удаление объектов контактных данных в центральном лесе по мере создания или удаления учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="38af8-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="38af8-153">На приведенном ниже рисунке показана топология центрального леса.</span><span class="sxs-lookup"><span data-stu-id="38af8-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="38af8-154">На этом рисунке есть двусторонние доверительные отношения между доменом, который содержит Lync Server, который находится в центральном лесе, и каждым доменом, который находится в отдельном лесе.</span><span class="sxs-lookup"><span data-stu-id="38af8-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="38af8-155">Схема в отдельных лесах пользователя не нуждается в расширении.</span><span class="sxs-lookup"><span data-stu-id="38af8-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="38af8-156">**Топология центрального леса**</span><span class="sxs-lookup"><span data-stu-id="38af8-156">**Central forest topology**</span></span>

<span data-ttu-id="38af8-157">![Топология центрального леса] (images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Топология центрального леса")</span><span class="sxs-lookup"><span data-stu-id="38af8-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="38af8-158">Несколько лесов, леса ресурсов</span><span class="sxs-lookup"><span data-stu-id="38af8-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="38af8-159">В топологии леса ресурсов один лес предназначен для выполнения серверных приложений, таких как Microsoft Exchange Server и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38af8-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="38af8-160">В лесу ресурсов размещаются серверные приложения и синхронизированное представление активного объекта пользователя, но оно не содержит учетные записи пользователей с поддержкой входа.</span><span class="sxs-lookup"><span data-stu-id="38af8-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="38af8-161">Лес ресурсов действует как общедоступная среда служб для других лесов, где находятся объекты пользователя.</span><span class="sxs-lookup"><span data-stu-id="38af8-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="38af8-162">У пользователей лесов есть доверительные отношения на уровне леса с лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="38af8-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="38af8-163">При развертывании сервера Lync Server в этом типе топологии вы создаете в лесу ресурсов один отключенный объект пользователя для каждой учетной записи пользователя в лесах пользователя.</span><span class="sxs-lookup"><span data-stu-id="38af8-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="38af8-164">Если Microsoft Exchange уже развернут в лесу ресурсов, это может быть вызвано тем, что отключенные учетные записи пользователей уже существуют.</span><span class="sxs-lookup"><span data-stu-id="38af8-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="38af8-165">Продукт для синхронизации каталогов, например MIIS, Microsoft Forefront Identity Manager (FIM) 2010 или Диспетчер жизненного цикла Microsoft Identity Manager (ILM) 2007 с пакетом дополнительных компонентов 1 (FP1), управляет жизненным циклом учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="38af8-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="38af8-166">При создании новой учетной записи пользователя в одном из лесов пользователя или удалении учетной записи пользователя из леса программа синхронизации каталогов синхронизирует соответствующее представление пользователя в лесу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="38af8-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="38af8-167">Эта топология может использоваться для предоставления общей инфраструктуры служб в организациях, которые управляют несколькими лесами или для разделения администрирования объектов Active Directory из другого администратора.</span><span class="sxs-lookup"><span data-stu-id="38af8-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="38af8-168">Компании, которым необходимо изолировать администрирование Active Directory по соображениям безопасности, часто выбирают эту топологию.</span><span class="sxs-lookup"><span data-stu-id="38af8-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="38af8-169">Эта топология обеспечивает преимущество для ограничения возможности продления схемы Active Directory до одного леса (то есть леса ресурсов).</span><span class="sxs-lookup"><span data-stu-id="38af8-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="38af8-170">На приведенной ниже схеме показана топология леса ресурсов.</span><span class="sxs-lookup"><span data-stu-id="38af8-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="38af8-171">**Топология леса ресурсов**</span><span class="sxs-lookup"><span data-stu-id="38af8-171">**Resource forest topology**</span></span>

<span data-ttu-id="38af8-172">![Топология леса ресурсов Active Directory] (images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Топология леса ресурсов Active Directory")</span><span class="sxs-lookup"><span data-stu-id="38af8-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="38af8-173">Несколько лесов в топологии леса ресурсов Lync с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="38af8-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="38af8-174">В этой топологии один или несколько лесов находятся в локальной среде и предназначены для размещения учетных записей пользователей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38af8-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="38af8-175">Лес ресурсов размещается не в локальной среде и поддерживается сторонним поставщиком услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="38af8-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="38af8-176">Лес ресурсов включает только развертывание Lync Server и синхронизированную репликацию учетных записей пользователей из локальных лесов учетных записей пользователей (-ов).</span><span class="sxs-lookup"><span data-stu-id="38af8-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="38af8-177">Она не содержит учетные записи пользователей с включенным входом.</span><span class="sxs-lookup"><span data-stu-id="38af8-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="38af8-178">Сервер Exchange развернут в локальных лесах (и), интегрированных с Exchange Online (гибридная среда), или службы электронной почты для локальных учетных записей пользователей предоставляются исключительно в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="38af8-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="38af8-179">Лес ресурсов действует как общедоступная среда служб для локальных лесов Active Directory, где находятся объекты пользователя.</span><span class="sxs-lookup"><span data-stu-id="38af8-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="38af8-180">Лес учетных записей пользователей имеет одностороннее отношение доверия между лесом и лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="38af8-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="38af8-181">При развертывании сервера Lync Server в этом типе топологии вы создаете в лесу ресурсов один отключенный объект пользователя для каждой учетной записи пользователя в лесах пользователя.</span><span class="sxs-lookup"><span data-stu-id="38af8-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="38af8-182">Продукт для синхронизации каталогов, например MIIS, Microsoft Forefront Identity Manager (FIM) 2010 или Диспетчер жизненного цикла Microsoft Identity Manager (ILM) 2007 с пакетом дополнительных компонентов 1 (FP1), управляет жизненным циклом учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="38af8-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="38af8-183">При создании новой учетной записи пользователя в одном из лесов пользователя или удалении учетной записи пользователя из леса программа синхронизации каталогов синхронизирует соответствующее представление пользователя в лесу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="38af8-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="38af8-184">Дополнительные сведения о настройке развертывания с несколькими лесами можно найти в разделе [развертывание Lync в архитектуре с несколькими лесами (партнер, на котором размещена Lync с гибридным Exchange)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="38af8-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


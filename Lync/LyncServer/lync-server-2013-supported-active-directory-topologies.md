---
title: 'Lync Server 2013: Поддерживаемые топологии Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46f9236bfbd110ee17811edec2e3e81fc4a0e0f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524166"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="05231-102">Поддерживаемые топологии Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05231-102">Supported Active Directory topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05231-103">_**Последнее изменение темы:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="05231-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="05231-104">Lync Server 2013 поддерживает те же топологии доменных служб Active Directory, что и Microsoft Lync Server 2010 и Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="05231-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="05231-105">Поддерживаются следующие топологии:</span><span class="sxs-lookup"><span data-stu-id="05231-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="05231-106">Одиночный лес с одним доменом</span><span class="sxs-lookup"><span data-stu-id="05231-106">Single forest with single domain</span></span>

  - <span data-ttu-id="05231-107">один лес с одним деревом и несколькими доменами;</span><span class="sxs-lookup"><span data-stu-id="05231-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="05231-108">один лес с несколькими деревьями и несвязанными пространствами имен;</span><span class="sxs-lookup"><span data-stu-id="05231-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="05231-109">несколько лесов в топологии с центральным лесом;</span><span class="sxs-lookup"><span data-stu-id="05231-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="05231-110">несколько лесов в топологии с лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="05231-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="05231-111">Несколько лесов в топологии с лесом ресурсов Lync в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="05231-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="05231-112">На следующем рисунке поясняются значки, используемые на иллюстрациях в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="05231-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="05231-113">**Пояснения к иллюстрациям по топологиям**</span><span class="sxs-lookup"><span data-stu-id="05231-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="05231-114">![Пояснения к иллюстрациям по топологиям](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Пояснения к иллюстрациям по топологиям")</span><span class="sxs-lookup"><span data-stu-id="05231-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="05231-115">Одиночный лес, один домен</span><span class="sxs-lookup"><span data-stu-id="05231-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="05231-116">Самая простая топология Active Directory, поддерживаемая Lync Server, одним лесом одного домена, представляет собой общую топологию.</span><span class="sxs-lookup"><span data-stu-id="05231-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="05231-117">На следующем рисунке показано развертывание Lync Server в топологии с одним доменом Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05231-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="05231-118">**Топология с одним доменом**</span><span class="sxs-lookup"><span data-stu-id="05231-118">**Single domain topology**</span></span>

<span data-ttu-id="05231-119">![Топология с одним доменом](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Топология одного домена")</span><span class="sxs-lookup"><span data-stu-id="05231-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="05231-120">Одиночный лес, несколько доменов</span><span class="sxs-lookup"><span data-stu-id="05231-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="05231-121">Еще одна топология Active Directory, поддерживаемая Lync Server — это один лес, состоящий из корневого домена и одного или нескольких дочерних доменов.</span><span class="sxs-lookup"><span data-stu-id="05231-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="05231-122">В этом типе топологии Active Directory домен, в котором создаются пользователи, может отличаться от домена, в котором развертывается Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05231-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="05231-123">Однако в случае развертывания интерфейсного пула все серверы переднего плана следует развернуть в пуле в рамках одного домена.</span><span class="sxs-lookup"><span data-stu-id="05231-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="05231-124">Поддержка групп универсальных администраторов Windows в Lync Server позволяет выполнять администрирование между доменами.</span><span class="sxs-lookup"><span data-stu-id="05231-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="05231-125">На следующем рисунке приведена иллюстрация к развертыванию в одиночном лесу с несколькими доменами.</span><span class="sxs-lookup"><span data-stu-id="05231-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="05231-126">На этом рисунке значок пользователя показывает домен, в котором расположена учетная запись пользователя, а стрелка указывает на домен, в котором размещается пул Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05231-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="05231-127">Учетные записи пользователей включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="05231-127">User accounts include the following:</span></span>

  - <span data-ttu-id="05231-128">Учетные записи пользователей в том же домене, что и пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="05231-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="05231-129">Учетные записи пользователей в другом домене из пула Lync Server</span><span class="sxs-lookup"><span data-stu-id="05231-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="05231-130">Учетные записи пользователей в дочернем домене домена с пулом Lync Server</span><span class="sxs-lookup"><span data-stu-id="05231-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="05231-131">**Одиночный лес с несколькими доменами**</span><span class="sxs-lookup"><span data-stu-id="05231-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="05231-132">![Одиночный лес с несколькими доменами](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Одиночный лес с несколькими доменами")</span><span class="sxs-lookup"><span data-stu-id="05231-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="05231-133">Одиночный лес, несколько деревьев</span><span class="sxs-lookup"><span data-stu-id="05231-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="05231-134">Топология из леса с несколькими деревьями состоит из двух или более доменов, которые определяют независимые древовидные структуры и раздельные пространства имен Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05231-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="05231-135">На следующем рисунке приведена иллюстрация к одиночному лесу с несколькими деревьями.</span><span class="sxs-lookup"><span data-stu-id="05231-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="05231-136">На этом рисунке значок пользователя показывает домен, в котором размещена учетная запись пользователя, сплошная линия указывает на пул Lync Server, находящийся в том же или другом домене, а пунктирная линия указывает на пул Lync Server, расположенный в другом дереве.</span><span class="sxs-lookup"><span data-stu-id="05231-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="05231-137">Учетные записи пользователей включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="05231-137">User accounts include the following:</span></span>

  - <span data-ttu-id="05231-138">Учетные записи пользователей в том же домене, что и пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="05231-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="05231-139">Учетные записи пользователей в разных доменах (но в том же дереве, что и) пул Lync Server</span><span class="sxs-lookup"><span data-stu-id="05231-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="05231-140">Учетные записи пользователей в другом дереве из пула Lync Server</span><span class="sxs-lookup"><span data-stu-id="05231-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="05231-141">**Одиночный лес с несколькими деревьями**</span><span class="sxs-lookup"><span data-stu-id="05231-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="05231-142">![Одиночный лес с несколькими деревьями](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Одиночный лес с несколькими деревьями")</span><span class="sxs-lookup"><span data-stu-id="05231-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="05231-143">Несколько лесов, центральный лес</span><span class="sxs-lookup"><span data-stu-id="05231-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="05231-144">Lync Server поддерживает несколько лесов, настроенных в топологии с центральным лесом.</span><span class="sxs-lookup"><span data-stu-id="05231-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="05231-145">Топологии с центральным лесом используют контактные объекты в центральном лесу, чтобы представлять пользователей в других лесах.</span><span class="sxs-lookup"><span data-stu-id="05231-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="05231-146">Центральный лет также содержит учетные записи для всех пользователей в этом лесу.</span><span class="sxs-lookup"><span data-stu-id="05231-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="05231-147">Продукт для синхронизации службы каталогов, например Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 или Microsoft Identity Lifecycle Manager (ILM) 2007 с пакетом дополнительных компонентов 1 (FP1), управляет жизненным циклом учетных записей пользователей внутри организации: когда в одном из лесов создается или удаляется учетная запись пользователя, продукт для синхронизации службы каталогов синхронизирует соответствующий контакт в центральном лесу.</span><span class="sxs-lookup"><span data-stu-id="05231-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="05231-148">Центральный лес предоставляет следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="05231-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="05231-149">Серверы, на которых работает Lync Server, централизованы в пределах одного леса.</span><span class="sxs-lookup"><span data-stu-id="05231-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="05231-150">Пользователи могут выполнять поиск пользователей в любом лесу и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="05231-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="05231-151">Пользователи могут просматривать состояние присутствия других пользователей в любом лесу.</span><span class="sxs-lookup"><span data-stu-id="05231-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="05231-152">Продукт для синхронизации службы каталогов автоматизирует добавление и удаление контактных объектов в центральном лесу при создании или удалении учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="05231-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="05231-153">На следующем рисунке приведена иллюстрация к топологии с центральным лесом.</span><span class="sxs-lookup"><span data-stu-id="05231-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="05231-154">На этом рисунке существуют двусторонние отношения доверия между доменом, на котором размещается Lync Server, который находится в центральном лесу, и каждым доменом пользователя, который находится в отдельном лесе.</span><span class="sxs-lookup"><span data-stu-id="05231-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="05231-155">Расширение схемы в отдельных лесах пользователей не требуется.</span><span class="sxs-lookup"><span data-stu-id="05231-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="05231-156">**Топология с центральным лесом**</span><span class="sxs-lookup"><span data-stu-id="05231-156">**Central forest topology**</span></span>

<span data-ttu-id="05231-157">![Топология с центральным лесом](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Топология с центральным лесом")</span><span class="sxs-lookup"><span data-stu-id="05231-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="05231-158">Несколько лесов, лес ресурсов</span><span class="sxs-lookup"><span data-stu-id="05231-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="05231-159">В топологии с лесом ресурсов один лес предназначен для выполнения серверных приложений, таких как Microsoft Exchange Server и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05231-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="05231-160">В лесу ресурсов размещаются серверные приложения и синхронизованное представление активного объекта пользователя, но он не содержит учетные записи пользователей с поддержкой входа.</span><span class="sxs-lookup"><span data-stu-id="05231-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="05231-161">Лес ресурсов выступает в роли среды общих служб для других лесов, где находятся объекты пользователей.</span><span class="sxs-lookup"><span data-stu-id="05231-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="05231-162">Леса пользователей имеют отношение доверия на уровне лесов с лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="05231-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="05231-163">При развертывании Lync Server в этом типе топологии вы создаете один отключенный объект пользователя в лесу ресурсов для каждой учетной записи пользователя в лесах пользователя.</span><span class="sxs-lookup"><span data-stu-id="05231-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="05231-164">Если Microsoft Exchange уже развернут в лесу ресурсов, отключенные учетные записи пользователей могут уже существовать.</span><span class="sxs-lookup"><span data-stu-id="05231-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="05231-165">Продукт для синхронизации службы каталогов, например MIIS, Microsoft Forefront Identity Manager (FIM) 2010 или Microsoft Identity Lifecycle Manager (ILM) 2007 с пакетом дополнительных компонентов 1 (FP1), управляет жизненным циклом учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="05231-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="05231-166">Когда в одном из лесов пользователей создается или удаляется учетная запись пользователя, продукт для синхронизации службы каталогов синхронизирует соответствующее представление пользователя в лесу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="05231-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="05231-p108">Эта топология может использоваться, чтобы предоставить общую инфраструктуру для служб в организациях, которые управляют несколькими лесами, или чтобы отделить администрирование объектов Active Directory от остальных задач администрирования. Эту топологию часто выбирают компании, которым требуется изолировать администрирование Active Directory по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="05231-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="05231-169">Данная топология имеет преимущество, заключающееся в ограничении потребности в расширении схемы Active Directory до отдельного леса (то есть леса ресурсов).</span><span class="sxs-lookup"><span data-stu-id="05231-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="05231-170">На следующей схеме приведена иллюстрация для топологии с лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="05231-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="05231-171">**Топология леса ресурсов**</span><span class="sxs-lookup"><span data-stu-id="05231-171">**Resource forest topology**</span></span>

<span data-ttu-id="05231-172">![Топология леса ресурсов Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Топология леса ресурсов Active Directory")</span><span class="sxs-lookup"><span data-stu-id="05231-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="05231-173">Несколько лесов в топологии с лесом ресурсов Lync в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="05231-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="05231-174">В этой топологии один или несколько лесов размещены локально и предназначены для хостинга учетных записей пользователей Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05231-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="05231-175">Лес ресурсов размещается локально и обслуживается сторонним поставщиком услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="05231-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="05231-176">Лес ресурсов содержит только развертывание Lync Server и синхронизированную репликацию учетных записей пользователей из локальных лесов учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="05231-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="05231-177">Он не содержит учетных записей пользователей с включенным входом.</span><span class="sxs-lookup"><span data-stu-id="05231-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="05231-178">Exchange развернута в локальных лесах учетных записей пользователей, интегрированных вместе с Exchange Online (гибридная среда), или службы электронной почты для локальных учетных записей пользователей предоставляются исключительно Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05231-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="05231-179">Лес ресурсов выступает в качестве общедоступной среды служб для локальных лесов Active Directory, в которых находятся объекты пользователя.</span><span class="sxs-lookup"><span data-stu-id="05231-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="05231-180">Лес учетных записей пользователей имеет одностороннее отношение доверия на уровне леса с лесом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="05231-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="05231-181">При развертывании Lync Server в этом типе топологии вы создаете один отключенный объект пользователя в лесу ресурсов для каждой учетной записи пользователя в лесах пользователя.</span><span class="sxs-lookup"><span data-stu-id="05231-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="05231-182">Продукт для синхронизации службы каталогов, например MIIS, Microsoft Forefront Identity Manager (FIM) 2010 или Microsoft Identity Lifecycle Manager (ILM) 2007 с пакетом дополнительных компонентов 1 (FP1), управляет жизненным циклом учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="05231-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="05231-183">Когда в одном из лесов пользователей создается или удаляется учетная запись пользователя, продукт для синхронизации службы каталогов синхронизирует соответствующее представление пользователя в лесу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="05231-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="05231-184">Дополнительные сведения о настройке развертывания с несколькими лесами приведены [в статье Deploy Lync in a Multi-Forest Architecture (партнер, размещенный в Lync с гибридной средой Exchange)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="05231-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


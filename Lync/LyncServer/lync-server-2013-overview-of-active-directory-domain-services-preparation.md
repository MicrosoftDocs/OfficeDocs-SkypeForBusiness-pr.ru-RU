---
title: 'Lync Server 2013: обзор подготовки доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51d0fec8f36749f52acf3272bf83dee3170da8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="65960-102">Обзор подготовки доменных служб Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65960-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65960-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="65960-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="65960-104">Для подготовки доменных служб Active Directory для развертывания Lync Server 2013 необходимо выполнить три действия в определенной последовательности.</span><span class="sxs-lookup"><span data-stu-id="65960-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="65960-105">В приведенной ниже таблице описаны шаги, необходимые для подготовки AD DS для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="65960-106">Этапы подготовки службы каталогов Active Directory</span><span class="sxs-lookup"><span data-stu-id="65960-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="65960-107">Шаг</span><span class="sxs-lookup"><span data-stu-id="65960-107">Step</span></span></th>
<th><span data-ttu-id="65960-108">Описание</span><span class="sxs-lookup"><span data-stu-id="65960-108">Description</span></span></th>
<th><span data-ttu-id="65960-109">Где бы вы ни напускались</span><span class="sxs-lookup"><span data-stu-id="65960-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="65960-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Подготовка схемы Active Directory в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65960-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="65960-111">Расширяет схему Active Directory, добавляя новые классы и атрибуты, которые используются в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="65960-112">Выполняются один раз для каждого леса в развертывании, на котором будет развернут сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="65960-113">Для хозяина схемы в корневом домене каждого леса, на котором будет развернут сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="65960-114">Вам не нужно выполнять этот шаг в корневом домене, если у вас есть разрешения на доступ к хозяину схемы, но вы должны быть членом группы "Администраторы схемы" в корневом домене и входить в группу "Администраторы предприятия" на хозяине схемы.</span><span class="sxs-lookup"><span data-stu-id="65960-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="65960-115">В топологии леса ресурсов выполните это действие только в лесу ресурсов, а не в лесах пользователей.</span><span class="sxs-lookup"><span data-stu-id="65960-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="65960-116">В топологии с центральным лесом выполните это действие только в центральном лесе, а не в лесах пользователей.</span><span class="sxs-lookup"><span data-stu-id="65960-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="65960-117"><a href="lync-server-2013-preparing-the-forest.md">Подготовка леса для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65960-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="65960-118">Создание глобальных параметров и универсальных групп, используемых в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="65960-119">Выполняются один раз для каждого леса в развертывании, на котором будет развернут сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="65960-120">В корневом домене каждого леса, на котором будет развернут сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="65960-121">Чтобы выполнить это действие, необходимо быть членом группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="65960-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="65960-122">В топологии леса ресурсов выполните это действие только в лесу ресурсов, а не в лесах пользователей.</span><span class="sxs-lookup"><span data-stu-id="65960-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="65960-123">В топологии с центральным лесом выполните это действие только в центральном лесе, а не в лесах пользователей.</span><span class="sxs-lookup"><span data-stu-id="65960-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="65960-124"><a href="lync-server-2013-preparing-domains.md">Подготовка доменов для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="65960-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="65960-125">Добавляет разрешения для объектов, которые будут использоваться членами универсальных групп.</span><span class="sxs-lookup"><span data-stu-id="65960-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="65960-126">Однократное выполнение для домена пользователя или домена сервера.</span><span class="sxs-lookup"><span data-stu-id="65960-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="65960-127">При переходе с Lync Server 2010 на Lync Server 2013 мастер развертывания может указать, что подготовка домена уже завершена.</span><span class="sxs-lookup"><span data-stu-id="65960-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="65960-128">Не нужно повторно выполнять подготовку домена.</span><span class="sxs-lookup"><span data-stu-id="65960-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="65960-129">Разрешения не изменились с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65960-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="65960-130">На рядовом сервере в каждом домене, где будет развернут сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65960-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="65960-131">Чтобы выполнить это действие, необходимо быть членом группы "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="65960-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="65960-132">Lync Server 2013, например Lync Server 2010, сохраняет большое количество сведений о конфигурации в хранилище Центрального управления, а не в службах AD, как и в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="65960-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="65960-133">Однако указанные ниже сведения хранятся в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="65960-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="65960-134">**Расширения схемы**.</span><span class="sxs-lookup"><span data-stu-id="65960-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="65960-135">Расширения объекта пользователя</span><span class="sxs-lookup"><span data-stu-id="65960-135">User object extensions</span></span>
    
      - <span data-ttu-id="65960-136">Расширения для классов Office Communications Server 2007 R2 для обеспечения обратной совместимости</span><span class="sxs-lookup"><span data-stu-id="65960-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="65960-137">**Данные** (хранящиеся в расширенной схеме Lync Server и существующих классах схем):</span><span class="sxs-lookup"><span data-stu-id="65960-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="65960-138">Универсальный код ресурса (URI) пользователя SIP и другие пользовательские параметры</span><span class="sxs-lookup"><span data-stu-id="65960-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="65960-139">Объекты контактов для таких приложений, как группа ответа и конференц-связь</span><span class="sxs-lookup"><span data-stu-id="65960-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="65960-140">Указатель на хранилище Центрального управления</span><span class="sxs-lookup"><span data-stu-id="65960-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="65960-141">Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="65960-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="65960-142">В Lync Server 2013 вы делегируйте настройку и администрирование, предоставляя разрешения на установку для универсальной группы Рткуниверсалсерверадминс, чтобы участники этой группы могли устанавливать и активировать Lync Server 2013 на локальном сервере (после добавления сервера в "топология", "Опубликовано" и "включено".</span><span class="sxs-lookup"><span data-stu-id="65960-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="65960-143">Делегированные пользователи должны быть локальными администраторами на компьютере, на котором они устанавливают и активируются с помощью Lync Server 2013, но не должны быть членами группы администраторов домена.</span><span class="sxs-lookup"><span data-stu-id="65960-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="65960-144">Вы также можете предоставить разрешения на доступ к объектам в указанных организационных подразделениях (OU), чтобы пользователи универсальных групп, созданные во время подготовки леса, могли обращаться к ним без участия в группе Администраторы домена.</span><span class="sxs-lookup"><span data-stu-id="65960-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="65960-145">Для новых развертываний Lync Server 2013 глобальные параметры должны храниться в контейнере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="65960-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="65960-146">Если ваша организация выполняет обновление из более ранней версии, но у вас есть глобальные параметры в системном контейнере, системный контейнер по-прежнему поддерживается.</span><span class="sxs-lookup"><span data-stu-id="65960-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65960-147">См. также</span><span class="sxs-lookup"><span data-stu-id="65960-147">See Also</span></span>


[<span data-ttu-id="65960-148">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65960-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="65960-149">Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65960-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="65960-150">Подготовка леса для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65960-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="65960-151">Подготовка доменов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65960-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: изменения схемы в Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70b090f59c0a0f8510d778ef659def77cfd0747
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="8890f-102">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8890f-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8890f-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8890f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8890f-104">Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить доменные службы Active Directory, расширив схему.</span><span class="sxs-lookup"><span data-stu-id="8890f-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="8890f-105">Расширения схемы добавляют классы и атрибуты, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8890f-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="8890f-106">Lync Server 2013 требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="8890f-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="8890f-107">Кроме того, многие сведения о конфигурации для Lync Server 2013 хранятся в центральном хранилище управления, а не в службах AD DS, как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="8890f-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="8890f-108">Следующие сведения по-прежнему хранятся в AD DS в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="8890f-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="8890f-109">**Расширения схемы**:</span><span class="sxs-lookup"><span data-stu-id="8890f-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="8890f-110">расширения объектов-пользователей;</span><span class="sxs-lookup"><span data-stu-id="8890f-110">User object extensions</span></span>
    
      - <span data-ttu-id="8890f-111">Расширения для классов Office Communications Server 2007 и Office Communications Server 2007 R2 для обеспечения обратной совместимости с поддерживаемыми предыдущими версиями</span><span class="sxs-lookup"><span data-stu-id="8890f-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="8890f-112">**Данные** (хранятся в расширенной схеме Lync Server и существующих классах схемы):</span><span class="sxs-lookup"><span data-stu-id="8890f-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="8890f-113">универсальный код ресурса (URI) SIP и другие параметры пользователя;</span><span class="sxs-lookup"><span data-stu-id="8890f-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="8890f-114">контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;</span><span class="sxs-lookup"><span data-stu-id="8890f-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="8890f-115">Указатель на центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="8890f-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="8890f-116">Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="8890f-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="8890f-117">В этом разделе описываются изменения схемы Active Directory, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8890f-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="8890f-118">В нем не описываются изменения схемы, представленные в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="8890f-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="8890f-119">Список классов и их описаний приведен [в статье классы и описания схемы в Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="8890f-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="8890f-120">Список атрибутов и их описание приведены [в статье атрибуты и описания схемы в Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="8890f-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="8890f-121">Список классов с атрибутами, которые они могут содержать, приведен [в статье атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="8890f-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="8890f-122">Префикс msRTCSIP определяет классы и атрибуты, характерные для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8890f-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="8890f-123">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="8890f-123">New Active Directory Attributes</span></span>

<span data-ttu-id="8890f-124">В следующей таблице описываются атрибуты Active Directory, добавленные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8890f-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="8890f-125">Атрибуты, добавленные Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8890f-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8890f-126">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8890f-126">Attribute</span></span></th>
<th><span data-ttu-id="8890f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8890f-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8890f-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8890f-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="8890f-129">Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="8890f-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="8890f-130">Политики хранения определяют срок хранения элементов почтового ящика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8890f-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="8890f-131">Этот атрибут используется совместно с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8890f-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8890f-132">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="8890f-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="8890f-p105">Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8890f-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8890f-135">msRTCSIP — Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="8890f-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="8890f-136">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="8890f-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="8890f-137">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="8890f-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="8890f-138">В следующей таблице описываются классы Active Directory, измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8890f-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="8890f-139">Классы, измененные в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8890f-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8890f-140">Класс</span><span class="sxs-lookup"><span data-stu-id="8890f-140">Class</span></span></th>
<th><span data-ttu-id="8890f-141">Изменение</span><span class="sxs-lookup"><span data-stu-id="8890f-141">Change</span></span></th>
<th><span data-ttu-id="8890f-142">Класс или атрибут</span><span class="sxs-lookup"><span data-stu-id="8890f-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8890f-143">Пользователь</span><span class="sxs-lookup"><span data-stu-id="8890f-143">User</span></span></p></td>
<td><p><span data-ttu-id="8890f-144">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8890f-144">add: mayContain</span></span></p>
<p><span data-ttu-id="8890f-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8890f-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8890f-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8890f-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="8890f-147">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="8890f-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8890f-148">Контакт</span><span class="sxs-lookup"><span data-stu-id="8890f-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="8890f-149">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8890f-149">add: mayContain</span></span></p>
<p><span data-ttu-id="8890f-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8890f-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8890f-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8890f-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="8890f-152">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="8890f-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8890f-153">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="8890f-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="8890f-154">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8890f-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8890f-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8890f-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8890f-156">msRTCSIP — Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="8890f-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="8890f-157">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="8890f-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="8890f-158">msRTCSIP — Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="8890f-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


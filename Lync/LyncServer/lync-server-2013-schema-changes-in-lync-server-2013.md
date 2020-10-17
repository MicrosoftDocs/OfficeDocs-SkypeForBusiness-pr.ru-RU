---
title: 'Lync Server 2013: изменения схемы в Lync Server 2013'
description: 'Lync Server 2013: изменения схемы в Lync Server 2013.'
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
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557155"
---
# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="0ba46-103">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba46-103">Schema changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ba46-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0ba46-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0ba46-105">Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить доменные службы Active Directory, расширив схему.</span><span class="sxs-lookup"><span data-stu-id="0ba46-105">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="0ba46-106">Расширения схемы добавляют классы и атрибуты, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ba46-106">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="0ba46-107">Lync Server 2013 требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="0ba46-107">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="0ba46-108">Кроме того, многие сведения о конфигурации для Lync Server 2013 хранятся в центральном хранилище управления, а не в службах AD DS, как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="0ba46-108">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="0ba46-109">Следующие сведения по-прежнему хранятся в AD DS в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0ba46-109">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="0ba46-110">**Расширения схемы**:</span><span class="sxs-lookup"><span data-stu-id="0ba46-110">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="0ba46-111">расширения объектов-пользователей;</span><span class="sxs-lookup"><span data-stu-id="0ba46-111">User object extensions</span></span>
    
      - <span data-ttu-id="0ba46-112">Расширения для классов Office Communications Server 2007 и Office Communications Server 2007 R2 для обеспечения обратной совместимости с поддерживаемыми предыдущими версиями</span><span class="sxs-lookup"><span data-stu-id="0ba46-112">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="0ba46-113">**Данные** (хранятся в расширенной схеме Lync Server и существующих классах схемы):</span><span class="sxs-lookup"><span data-stu-id="0ba46-113">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="0ba46-114">универсальный код ресурса (URI) SIP и другие параметры пользователя;</span><span class="sxs-lookup"><span data-stu-id="0ba46-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="0ba46-115">контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;</span><span class="sxs-lookup"><span data-stu-id="0ba46-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="0ba46-116">Указатель на центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="0ba46-116">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="0ba46-117">Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="0ba46-117">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="0ba46-118">В этом разделе описываются изменения схемы Active Directory, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ba46-118">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="0ba46-119">В нем не описываются изменения схемы, представленные в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="0ba46-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="0ba46-120">Список классов и их описаний приведен [в статье классы и описания схемы в Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="0ba46-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="0ba46-121">Список атрибутов и их описание приведены [в статье атрибуты и описания схемы в Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="0ba46-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="0ba46-122">Список классов с атрибутами, которые они могут содержать, приведен [в статье атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="0ba46-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="0ba46-123">Префикс msRTCSIP определяет классы и атрибуты, характерные для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ba46-123">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="0ba46-124">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="0ba46-124">New Active Directory Attributes</span></span>

<span data-ttu-id="0ba46-125">В следующей таблице описываются атрибуты Active Directory, добавленные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ba46-125">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="0ba46-126">Атрибуты, добавленные Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba46-126">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ba46-127">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0ba46-127">Attribute</span></span></th>
<th><span data-ttu-id="0ba46-128">Описание</span><span class="sxs-lookup"><span data-stu-id="0ba46-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ba46-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0ba46-129">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="0ba46-130">Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="0ba46-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="0ba46-131">Политики хранения определяют срок хранения элементов почтового ящика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0ba46-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="0ba46-132">Этот атрибут используется совместно с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0ba46-132">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba46-133">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="0ba46-133">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="0ba46-p105">Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0ba46-p105">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba46-136">msRTCSIP — Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="0ba46-136">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="0ba46-137">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="0ba46-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="0ba46-138">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="0ba46-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="0ba46-139">В следующей таблице описываются классы Active Directory, измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ba46-139">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="0ba46-140">Классы, измененные в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba46-140">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ba46-141">Класс</span><span class="sxs-lookup"><span data-stu-id="0ba46-141">Class</span></span></th>
<th><span data-ttu-id="0ba46-142">Изменение</span><span class="sxs-lookup"><span data-stu-id="0ba46-142">Change</span></span></th>
<th><span data-ttu-id="0ba46-143">Класс или атрибут</span><span class="sxs-lookup"><span data-stu-id="0ba46-143">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ba46-144">Пользователь</span><span class="sxs-lookup"><span data-stu-id="0ba46-144">User</span></span></p></td>
<td><p><span data-ttu-id="0ba46-145">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="0ba46-145">add: mayContain</span></span></p>
<p><span data-ttu-id="0ba46-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="0ba46-146">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="0ba46-147">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0ba46-147">ProxyAddresses</span></span></p>
<p><span data-ttu-id="0ba46-148">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="0ba46-148">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba46-149">Контакт</span><span class="sxs-lookup"><span data-stu-id="0ba46-149">Contact</span></span></p></td>
<td><p><span data-ttu-id="0ba46-150">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="0ba46-150">add: mayContain</span></span></p>
<p><span data-ttu-id="0ba46-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="0ba46-151">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="0ba46-152">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0ba46-152">ProxyAddresses</span></span></p>
<p><span data-ttu-id="0ba46-153">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="0ba46-153">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba46-154">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="0ba46-154">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="0ba46-155">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="0ba46-155">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="0ba46-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0ba46-156">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba46-157">msRTCSIP — Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="0ba46-157">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="0ba46-158">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="0ba46-158">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="0ba46-159">msRTCSIP — Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="0ba46-159">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


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
ms.openlocfilehash: 54a3fd5f18785a649803cc6f9a0a56d7b98a2ee6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a><span data-ttu-id="5de5a-102">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de5a-102">Schema changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de5a-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5de5a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5de5a-104">Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить доменные службы Active Directory, расширив схему.</span><span class="sxs-lookup"><span data-stu-id="5de5a-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="5de5a-105">Расширения схемы добавляют классы и атрибуты, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5de5a-105">The schema extensions add the classes and attributes that are required by Lync Server 2013.</span></span>

<span data-ttu-id="5de5a-106">Lync Server 2013 требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты.</span><span class="sxs-lookup"><span data-stu-id="5de5a-106">Lync Server 2013 requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="5de5a-107">Кроме того, многие сведения о конфигурации Lync Server 2013 хранятся в главном хранилище, а не в службах AD DS, как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="5de5a-107">In addition, much configuration information for Lync Server 2013 is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="5de5a-108">Следующая информация сохраняется в службах AD DS в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="5de5a-108">The following information is still stored in AD DS in Lync Server 2013:</span></span>

  - <span data-ttu-id="5de5a-109">**Расширения схемы**.</span><span class="sxs-lookup"><span data-stu-id="5de5a-109">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="5de5a-110">Расширения объекта пользователя</span><span class="sxs-lookup"><span data-stu-id="5de5a-110">User object extensions</span></span>
    
      - <span data-ttu-id="5de5a-111">Расширения для классов Office Communications Server 2007 и Office Communications Server 2007 R2 обеспечивают обратную совместимость с предыдущими версиями</span><span class="sxs-lookup"><span data-stu-id="5de5a-111">Extensions for Office Communications Server 2007 and Office Communications Server 2007 R2 classes to maintain backward compatibility with supported previous versions</span></span>

<!-- end list -->

  - <span data-ttu-id="5de5a-112">**Данные** (хранящиеся в расширенной схеме Lync Server и существующих классах схем):</span><span class="sxs-lookup"><span data-stu-id="5de5a-112">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="5de5a-113">Универсальный код ресурса (URI) пользователя SIP и другие пользовательские параметры</span><span class="sxs-lookup"><span data-stu-id="5de5a-113">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="5de5a-114">Объекты контактов для таких приложений, как группа ответа и конференц-связь</span><span class="sxs-lookup"><span data-stu-id="5de5a-114">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="5de5a-115">Указатель на хранилище Центрального управления</span><span class="sxs-lookup"><span data-stu-id="5de5a-115">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="5de5a-116">Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)</span><span class="sxs-lookup"><span data-stu-id="5de5a-116">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="5de5a-117">В этой статье описаны изменения схемы Active Directory, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5de5a-117">This topic describes the Active Directory schema changes required by Lync Server 2013.</span></span> <span data-ttu-id="5de5a-118">В нем не описаны изменения схемы, которые появились в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="5de5a-118">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="5de5a-119">Список классов и их описаний можно найти в разделе [классы и описания схемы в Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="5de5a-119">For a list of classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="5de5a-120">Список атрибутов и их описание можно найти [в разделе атрибуты и описания схемы в Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="5de5a-120">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="5de5a-121">Список классов с атрибутами, которые они могут содержать, можно найти [в разделе атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="5de5a-121">For a list of classes with the attributes they may contain, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span>

<span data-ttu-id="5de5a-122">Префикс msRTCSIP определяет классы и атрибуты, специфичные для сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5de5a-122">The msRTCSIP prefix identifies classes and attributes that are specific to Lync Server.</span></span>

<div>

## <a name="new-active-directory-attributes"></a><span data-ttu-id="5de5a-123">Новые атрибуты Active Directory</span><span class="sxs-lookup"><span data-stu-id="5de5a-123">New Active Directory Attributes</span></span>

<span data-ttu-id="5de5a-124">В таблице ниже описаны атрибуты Active Directory, добавленные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5de5a-124">The following table describes the Active Directory attributes that are added by Lync Server 2013.</span></span>

### <a name="attributes-added-by-lync-server-2013"></a><span data-ttu-id="5de5a-125">Атрибуты, добавленные в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de5a-125">Attributes Added by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5de5a-126">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5de5a-126">Attribute</span></span></th>
<th><span data-ttu-id="5de5a-127">Описание</span><span class="sxs-lookup"><span data-stu-id="5de5a-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5de5a-128">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5de5a-128">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="5de5a-129">Этот атрибут с несколькими значениями содержит идентификаторы для политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="5de5a-129">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="5de5a-130">Политики удержания сохраняют для пользователя элементы почтового ящика на время удержания.</span><span class="sxs-lookup"><span data-stu-id="5de5a-130">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="5de5a-131">Этот атрибут является общим для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="5de5a-131">This attribute is shared with Exchange 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de5a-132">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="5de5a-132">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="5de5a-133">Это идентификатор группы маршрутизации SIP.</span><span class="sxs-lookup"><span data-stu-id="5de5a-133">This is the SIP routing group ID.</span></span> <span data-ttu-id="5de5a-134">Пользователи в одной группе будут регистрироваться на одном и том же внешнем сервере.</span><span class="sxs-lookup"><span data-stu-id="5de5a-134">Users in the same group will register to the same Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5de5a-135">msRTCSIP-Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="5de5a-135">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="5de5a-136">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5de5a-136">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a><span data-ttu-id="5de5a-137">Измененные классы Active Directory</span><span class="sxs-lookup"><span data-stu-id="5de5a-137">Modified Active Directory Classes</span></span>

<span data-ttu-id="5de5a-138">В таблице ниже описаны классы Active Directory, измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5de5a-138">The following table describes the Active Directory classes that are modified by Lync Server 2013.</span></span>

### <a name="classes-modified-by-lync-server-2013"></a><span data-ttu-id="5de5a-139">Классы, измененные в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5de5a-139">Classes Modified by Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5de5a-140">Классов</span><span class="sxs-lookup"><span data-stu-id="5de5a-140">Class</span></span></th>
<th><span data-ttu-id="5de5a-141">Изменение</span><span class="sxs-lookup"><span data-stu-id="5de5a-141">Change</span></span></th>
<th><span data-ttu-id="5de5a-142">Класс или атрибут</span><span class="sxs-lookup"><span data-stu-id="5de5a-142">Class or Attribute</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5de5a-143">Пользователь</span><span class="sxs-lookup"><span data-stu-id="5de5a-143">User</span></span></p></td>
<td><p><span data-ttu-id="5de5a-144">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="5de5a-144">add: mayContain</span></span></p>
<p><span data-ttu-id="5de5a-145">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="5de5a-145">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5de5a-146">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5de5a-146">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5de5a-147">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="5de5a-147">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de5a-148">Службу</span><span class="sxs-lookup"><span data-stu-id="5de5a-148">Contact</span></span></p></td>
<td><p><span data-ttu-id="5de5a-149">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="5de5a-149">add: mayContain</span></span></p>
<p><span data-ttu-id="5de5a-150">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="5de5a-150">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5de5a-151">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5de5a-151">ProxyAddresses</span></span></p>
<p><span data-ttu-id="5de5a-152">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="5de5a-152">msRTCSIP-UserRoutingGroupId</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5de5a-153">Почта-получатель</span><span class="sxs-lookup"><span data-stu-id="5de5a-153">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="5de5a-154">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="5de5a-154">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5de5a-155">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5de5a-155">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de5a-156">msRTCSIP-Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="5de5a-156">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="5de5a-157">Add (Добавить): Майконтаин</span><span class="sxs-lookup"><span data-stu-id="5de5a-157">add: mayContain</span></span></p></td>
<td><p><span data-ttu-id="5de5a-158">msRTCSIP-Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="5de5a-158">msRTCSIP-MirrorBackEndServer</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


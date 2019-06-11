---
title: 'Lync Server 2013: атрибуты и описания схемы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="59c7a-102">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c7a-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59c7a-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="59c7a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="59c7a-104">В этом разделе описаны все атрибуты схемы, которые используются в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59c7a-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="59c7a-105">Классы, связанные с атрибутами, приведены [в разделе атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="59c7a-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="59c7a-106">Список классов и атрибутов, новых в Lync Server 2013, можно найти [в разделе изменения схемы в Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="59c7a-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="59c7a-107">Атрибуты, которые являются связанными парами, задаются как пересылаемые ссылки или обратные ссылки.</span><span class="sxs-lookup"><span data-stu-id="59c7a-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="59c7a-108">Атрибут, который ссылается на другой объект, является прямой ссылкой; атрибут другого объекта, который ссылается на первый объект, является обратной ссылкой.</span><span class="sxs-lookup"><span data-stu-id="59c7a-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="59c7a-109">Пересылка ссылок является обновляемой, а обратные ссылки — в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="59c7a-110">Некоторые атрибуты имеют значение битовой маски.</span><span class="sxs-lookup"><span data-stu-id="59c7a-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="59c7a-111">Для этих атрибутов каждый параметр представляется битом, а отображаемое десятичное число — разрядное положение.</span><span class="sxs-lookup"><span data-stu-id="59c7a-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="59c7a-112">Битовые позиции начинаются с бита 0.</span><span class="sxs-lookup"><span data-stu-id="59c7a-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="59c7a-113">Например, 1 (двоичный) является битом 0, а 10000 (двоичный) — бит 4 множества.</span><span class="sxs-lookup"><span data-stu-id="59c7a-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="59c7a-114">Каждый бит представляет свойство.</span><span class="sxs-lookup"><span data-stu-id="59c7a-114">Each bit represents a property.</span></span> <span data-ttu-id="59c7a-115">Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="59c7a-115">The following are some examples:</span></span>

  - <span data-ttu-id="59c7a-116">10000 (двоичный) имеет десятичное значение 16 (то есть установлено значение bit 4).</span><span class="sxs-lookup"><span data-stu-id="59c7a-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="59c7a-117">100000000 (двоичный) имеет десятичное значение 256 (то есть установлено значение bit 8).</span><span class="sxs-lookup"><span data-stu-id="59c7a-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="59c7a-118">1100 (двоичный) имеет десятичное значение 12 (это означает, что установлены биты 2 и 3; включены свойства, представленные обоими битами).</span><span class="sxs-lookup"><span data-stu-id="59c7a-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="59c7a-119">1111000001 (двоичный) имеет десятичное значение 961 (это значит, что заданы биты 0, 6, 7, 8 и 9), для каждого из этих битов включена поддержка свойств.</span><span class="sxs-lookup"><span data-stu-id="59c7a-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="59c7a-120">Атрибуты схемы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c7a-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59c7a-121">Атрибут</span><span class="sxs-lookup"><span data-stu-id="59c7a-121">Attribute</span></span></th>
<th><span data-ttu-id="59c7a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="59c7a-122">Description</span></span></th>
<th><span data-ttu-id="59c7a-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="59c7a-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-124">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59c7a-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="59c7a-125">Существующий атрибут в доменных службах Active Directory, который теперь связан с классами <strong>msRTCSIP-Pool</strong> и <strong>msRTCSIP-мониторингсервер</strong> .</span><span class="sxs-lookup"><span data-stu-id="59c7a-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="59c7a-126">Этот атрибут указывает полное доменное имя (FQDN) для пула или сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="59c7a-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="59c7a-127">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-128">Новые возможности Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-129">msDS-Саурцеобжектдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-130">Этот атрибут представляет строковое представление различающегося имени (DN) объекта в другом лесе, которое соответствует этому объекту.</span><span class="sxs-lookup"><span data-stu-id="59c7a-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="59c7a-131">Этот атрибут используется для расширения группы рассылки и автоматического посещения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="59c7a-132">Этот атрибут определен в схеме Active Directory, используемой по умолчанию, для Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="59c7a-133">Чтобы не допустить необходимости обновления AD DS до Windows Server 2003 R2, подготовка схемы Active Directory расширяет схему Windows Server 2003 с помощью этого определения атрибута.</span><span class="sxs-lookup"><span data-stu-id="59c7a-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-134">Новые возможности Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-135">Мсексчуквоицемаилсеттингс</span><span class="sxs-lookup"><span data-stu-id="59c7a-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="59c7a-136">Этот атрибут с несколькими значениями хранит параметры голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="59c7a-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="59c7a-137">Этот атрибут является общим для единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="59c7a-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="59c7a-138">Новые возможности Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="59c7a-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="59c7a-140">Этот атрибут с несколькими значениями содержит идентификаторы для политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="59c7a-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="59c7a-141">Политики удержания сохраняют для пользователя элементы почтового ящика на время удержания.</span><span class="sxs-lookup"><span data-stu-id="59c7a-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="59c7a-142">Этот атрибут является общим для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="59c7a-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-143">Новые возможности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59c7a-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-144">msRTCSIP-Акпинфо</span><span class="sxs-lookup"><span data-stu-id="59c7a-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="59c7a-145">Этот атрибут хранит сведения о поставщике голосовой конференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-146">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-147">msRTCSIP-Аппликатиондестинатион</span><span class="sxs-lookup"><span data-stu-id="59c7a-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="59c7a-148">Этот атрибут указывает на запись доверенной службы для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-149">Новые возможности Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-150">msRTCSIP-Аппликатионлист</span><span class="sxs-lookup"><span data-stu-id="59c7a-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="59c7a-151">Этот атрибут включает список размещенных приложений на сервере приложений.</span><span class="sxs-lookup"><span data-stu-id="59c7a-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-152">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-153">msRTCSIP-Аппликатионоптионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="59c7a-154">Этот атрибут определяет параметры для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-155">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-156">msRTCSIP-Аппликатионпримарилангуаже</span><span class="sxs-lookup"><span data-stu-id="59c7a-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="59c7a-157">Этот атрибут включает основной язык для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-158">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-159">msRTCSIP-Аппликатионсекондарилангуажес</span><span class="sxs-lookup"><span data-stu-id="59c7a-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="59c7a-160">Этот многозначный атрибут имеет дополнительные языки для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-161">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-162">msRTCSIP-Аппликатионсервербл</span><span class="sxs-lookup"><span data-stu-id="59c7a-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="59c7a-163">Этот атрибут включает список серверов приложений, входящих в этот пул.</span><span class="sxs-lookup"><span data-stu-id="59c7a-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="59c7a-164">Соответствующая ссылка для перехода на этот атрибут обратной ссылки — <strong>msRTCSIP-аппликатионсерверпуллинк</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-165">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-166">msRTCSIP-Аппликатионсерверпуллинк</span><span class="sxs-lookup"><span data-stu-id="59c7a-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="59c7a-167">Этот атрибут указывает на пул, к которому относится этот сервер приложений.</span><span class="sxs-lookup"><span data-stu-id="59c7a-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="59c7a-168">Это пересылка ссылки.</span><span class="sxs-lookup"><span data-stu-id="59c7a-168">This is the forward link.</span></span> <span data-ttu-id="59c7a-169">Соответствующая обратная ссылка — <strong>msRTCSIP-аппликатионсервербл</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-170">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-171">msRTCSIP-Арчиведефаулт (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-172">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-173">Устаревшие в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-174">msRTCSIP-Арчиведефаултфлагс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-175">Этот атрибут определяет глобальное значение по умолчанию в пределах границы леса для архивации всех пользовательских сообщений.</span><span class="sxs-lookup"><span data-stu-id="59c7a-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="59c7a-176">Это действие обеспечивается уровнем агента архивации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="59c7a-177">Диапазон значений для этого атрибута выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59c7a-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-178"><strong>Истина</strong>: архивация всех пользователей</span><span class="sxs-lookup"><span data-stu-id="59c7a-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="59c7a-179"><strong>False</strong>: не архивировать всех пользователей</span><span class="sxs-lookup"><span data-stu-id="59c7a-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="59c7a-180">Этот атрибут глобально Controls в пределах границы леса, в котором архивируются сведения о взаимодействии пользователей во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="59c7a-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="59c7a-181"><strong>Поведение сервера Live Communications Server 2005 (теперь оно устарело)</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="59c7a-182">Диапазон значений для этого атрибута выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59c7a-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-183">0: Архивация текста сообщения [бит 0]</span><span class="sxs-lookup"><span data-stu-id="59c7a-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="59c7a-184">1: не архивируйте текст сообщения [бит 0]</span><span class="sxs-lookup"><span data-stu-id="59c7a-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="59c7a-185"><strong>Поведение сервера Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="59c7a-186">Диапазон значений для этого атрибута выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59c7a-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-187">0: Арчивефедератиондефаултвисаутбоди (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-188">1-2: Арчивеинтерналкоммуникатионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="59c7a-189">3-4: Арчивефедератедкоммуникатионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="59c7a-190">5: Рекордпресенцерегистратионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="59c7a-191">6: Рекордимкаллдетаилс</span><span class="sxs-lookup"><span data-stu-id="59c7a-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="59c7a-192">7: Рекордграупимкаллдетаилс</span><span class="sxs-lookup"><span data-stu-id="59c7a-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="59c7a-193">8: Рекордфилетрансферинстанцес</span><span class="sxs-lookup"><span data-stu-id="59c7a-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="59c7a-194">9: Рекордаудиокаллдетаилс</span><span class="sxs-lookup"><span data-stu-id="59c7a-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="59c7a-195">10: Рекордвидеокаллдетаилс</span><span class="sxs-lookup"><span data-stu-id="59c7a-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="59c7a-196">11: Рекордремотеассистанцекаллдетаилс</span><span class="sxs-lookup"><span data-stu-id="59c7a-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="59c7a-197">12: Рекордаппликатионшарингдетаилс</span><span class="sxs-lookup"><span data-stu-id="59c7a-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="59c7a-198">13: Рекордмитингинстантиатионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="59c7a-199">14: Рекордмитингжоинс</span><span class="sxs-lookup"><span data-stu-id="59c7a-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="59c7a-200">15: Рекорддатажоинс</span><span class="sxs-lookup"><span data-stu-id="59c7a-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="59c7a-201">16: Рекордавжоинс</span><span class="sxs-lookup"><span data-stu-id="59c7a-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-202">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-203">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-204">msRTCSIP-Арчивефедератиондефаулт (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-205">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-206">Устаревшие в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-207">msRTCSIP-Арчивефедератиондефаултфлагс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-208">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-209">Устаревшие в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-210">msRTCSIP-Арчивинженаблед</span><span class="sxs-lookup"><span data-stu-id="59c7a-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="59c7a-211">Этот атрибут является целым числом, используемым в качестве битового поля, чтобы указать, нужно ли архивировать связь отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="59c7a-212">Этот элемент управления принудительно применяется уровнем агента архивации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="59c7a-213">Оно помечено для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="59c7a-214">Область действия этого атрибута зависит от одного пользователя или контакта.</span><span class="sxs-lookup"><span data-stu-id="59c7a-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="59c7a-215">Допустимые значения (и связанные с ними битовые позиции) в Lync Server описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-216">0: не архивировать (не установлен бит)</span><span class="sxs-lookup"><span data-stu-id="59c7a-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-217">1: устарело (разрядное расположение 0)</span><span class="sxs-lookup"><span data-stu-id="59c7a-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-218">2: устарело (разрядное расположение 1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-219">4: Архивация внутренних сообщений (разрядность 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-220">8: Архивация федеративных коммуникаций (разрядное расположение 3)</span><span class="sxs-lookup"><span data-stu-id="59c7a-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="59c7a-221">Ранее действительные значения в режиме Live Communications Server 2005 описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-222">0: используйте значение по умолчанию, определяемое <strong>msRTCSIP-арчиведефаулт</strong> и <strong>msRTCSIP-арчивефедератион</strong> в следующем порядке приоритета:</span><span class="sxs-lookup"><span data-stu-id="59c7a-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-223">1: Архив</span><span class="sxs-lookup"><span data-stu-id="59c7a-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="59c7a-224">2: не архивировать</span><span class="sxs-lookup"><span data-stu-id="59c7a-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="59c7a-225">3: Архивация без текста сообщения</span><span class="sxs-lookup"><span data-stu-id="59c7a-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-226">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-227">msRTCSIP-Арчивингсервердата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-228">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-229">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-230">msRTCSIP-Арчивингсерверверсион (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-231">Этот атрибут определяет версию службы архивации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="59c7a-232">Этот атрибут является монотонаусли увеличивающимся целочисленным типом, увеличивающимся до каждого официального выпуска продукта.</span><span class="sxs-lookup"><span data-stu-id="59c7a-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="59c7a-233">Возможные допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="59c7a-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-234">Не определено: сервер Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="59c7a-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="59c7a-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="59c7a-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="59c7a-236">                 Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="59c7a-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="59c7a-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="59c7a-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="59c7a-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-239">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-240">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-241">msRTCSIP-Баккендсервер</span><span class="sxs-lookup"><span data-stu-id="59c7a-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="59c7a-242">Этот атрибут указывает полное доменное имя сервера, на котором находится пул.</span><span class="sxs-lookup"><span data-stu-id="59c7a-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="59c7a-243">Так как в каждом пуле может быть только один сервер, это является атрибутом с одним значением.</span><span class="sxs-lookup"><span data-stu-id="59c7a-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="59c7a-244">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-245">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-246">msRTCSIP-Конференцедиректорихомепул</span><span class="sxs-lookup"><span data-stu-id="59c7a-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="59c7a-247">Этот атрибут содержит идентификатор пула, на котором размещен каталог конференций.</span><span class="sxs-lookup"><span data-stu-id="59c7a-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-248">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-249">msRTCSIP-Конференцедиректорид</span><span class="sxs-lookup"><span data-stu-id="59c7a-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="59c7a-250">Этот атрибут включает идентификатор каталога конференций.</span><span class="sxs-lookup"><span data-stu-id="59c7a-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-251">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-252">msRTCSIP-Конференцедиректоритаржетпул</span><span class="sxs-lookup"><span data-stu-id="59c7a-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="59c7a-253">Этот атрибут содержит идентификатор пула, в который перемещается Каталог конференций.</span><span class="sxs-lookup"><span data-stu-id="59c7a-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-254">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-255">msRTCSIP — по умолчанию</span><span class="sxs-lookup"><span data-stu-id="59c7a-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="59c7a-256">Этот логический атрибут определяет, используется ли по умолчанию использование телефона.</span><span class="sxs-lookup"><span data-stu-id="59c7a-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="59c7a-257">Если для этого атрибута установлено <strong>значение true</strong>, использование телефона является использованием по умолчанию и не может быть удалено администратором.</span><span class="sxs-lookup"><span data-stu-id="59c7a-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="59c7a-258">Если для атрибута задано значение <strong>false</strong>, использование может быть удалено.</span><span class="sxs-lookup"><span data-stu-id="59c7a-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-259">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-260">msRTCSIP-Дефаулткваекстерналурл</span><span class="sxs-lookup"><span data-stu-id="59c7a-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="59c7a-261">Этот атрибут определяет URL-адрес Communicator Web Access для пользователей, которые находятся за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-262">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-263">msRTCSIP-Дефаулткваинтерналурл</span><span class="sxs-lookup"><span data-stu-id="59c7a-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="59c7a-264">Этот атрибут определяет URL-адрес Communicator Web Access для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-265">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-266">msRTCSIP-Дефаултлокатионпрофилелинк (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-267">Этот атрибут с одним значением включает различающееся имя (DN) объекта класса профиля расположения, присвоенного ему.</span><span class="sxs-lookup"><span data-stu-id="59c7a-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="59c7a-268">Ссылка "вперед": <strong>ИД ссылки 11036</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="59c7a-269">Соответствующая обратная ссылка — <strong>msRTCSIP-серверреференцебл</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-270">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-271">msRTCSIP-Дефаултполици (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-272">Этот логический атрибут указывает, является ли политика политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59c7a-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="59c7a-273">Политика — это политика по умолчанию, для которой установлено <strong>значение true</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-274">Новые возможности Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="59c7a-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="59c7a-275">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-276">msRTCSIP-Дефаултраутетоеджепрокси (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-277">Этот атрибут указывает полное доменное имя либо для пограничного сервера, на котором запущена служба Edge Access, если к нему есть прямой доступ, либо из подсистемы балансировки нагрузки для пула серверов, на котором запущена служба пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="59c7a-278">Если доступ к службам пограничного сервера Access возможен только через одного или нескольких режиссеров, этот атрибут указывает полное доменное имя и, при необходимости, номер порта режиссера или аппаратного балансировщика подсистемы балансировки нагрузки, обслуживающего каталог пула.</span><span class="sxs-lookup"><span data-stu-id="59c7a-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="59c7a-279">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-280">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-281">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-282">msRTCSIP-Дефаултраутетоеджепроксипорт (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-283">Этот атрибут представляет номер порта, который должен использоваться для подключения к серверу, на котором запущена служба пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="59c7a-284">Допустимое значение — это целое число, задающее используемый порт.</span><span class="sxs-lookup"><span data-stu-id="59c7a-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="59c7a-285">Значение по умолчанию — 5061.</span><span class="sxs-lookup"><span data-stu-id="59c7a-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-286">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-287">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-288">msRTCSIP-Дефпресенцесубскриптионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-289">Этот атрибут представляет период ожидания подписки на присутствие по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59c7a-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-290">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-291">msRTCSIP-Дефрегистратионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-292">Этот атрибут представляет окно времени ожидания регистрации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59c7a-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-293">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-294">msRTCSIP-Дефроамингдатасубскриптионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-295">Этот атрибут представляет окно времени ожидания для подписки на перемещаемые данные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59c7a-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-296">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="59c7a-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="59c7a-298">Этот атрибут используется в топологии разделения доменов и содержит полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="59c7a-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="59c7a-299">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-300">msRTCSIP — описание (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-301">Этот однозначный строковый атрибут Юникода включает понятное описание этого маршрута или правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-302">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-303">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-304">msRTCSIP-Домаиндата</span><span class="sxs-lookup"><span data-stu-id="59c7a-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-305">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-306">msRTCSIP-имя_домена</span><span class="sxs-lookup"><span data-stu-id="59c7a-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="59c7a-307">Этот атрибут представляет домен, настроенный для регистратора.</span><span class="sxs-lookup"><span data-stu-id="59c7a-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-308">msRTCSIP-Еджепроксидата</span><span class="sxs-lookup"><span data-stu-id="59c7a-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-309">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-310">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-311">msRTCSIP-Еджепроксифкдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-312">Этот атрибут указывает полное доменное имя сервера, на котором запущена служба пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="59c7a-313">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-314">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-315">msRTCSIP-Енаблебестеффортнотифи (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-316">Этот атрибут определяет, будет ли сервер создавать запрос уведомления о неэффективном выполнении (уведомления), а не запрос уведомления в ответ на запрос подписки от клиента.</span><span class="sxs-lookup"><span data-stu-id="59c7a-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="59c7a-317">УВЕДОМЛЕНИЕ — это расширение с повышенной производительностью для подтверждения подписки на подписку, в котором сервер генерирует запросы уведомлений, а не обычные уведомления.</span><span class="sxs-lookup"><span data-stu-id="59c7a-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="59c7a-318">Преимущество в производительности заключается в том, что запрос на уведомление не требует ответа на 200 ОК от клиента в ответ на запрос уведомления.</span><span class="sxs-lookup"><span data-stu-id="59c7a-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="59c7a-319">Допустимые значения: <strong>true</strong> или <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="59c7a-320">Сервер Live Communications Server 2003 не поддерживает уведомления запросов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="59c7a-321">Для взаимодействия с серверными приложениями, написанными с помощью API сервера Live Communications Server 2003, работающего на сервере Live Communications Server 2005 и сторонних серверах, запросы уведомления можно отключить, задавая для них значение <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="59c7a-322">В настоящее время уведомления не входят в стандарт IETF (задачи по проектированию Интернета), процесс стандартизации SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="59c7a-323">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-324">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-325">msRTCSIP-Енаблефедератион (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-326">Этот атрибут является глобальным переключателем, с помощью которого администраторы могут настроить, разрешено ли пользователям взаимодействовать с пользователями из других организаций.</span><span class="sxs-lookup"><span data-stu-id="59c7a-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="59c7a-327">Он позволяет администратору перезаписать атрибут <strong>федератионенаблед</strong> отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="59c7a-328">Этот атрибут полезен для защиты внутренней сети от атак из Интернета, которые могут быть вызваны червем, вирусами или целевыми атаками в компании.</span><span class="sxs-lookup"><span data-stu-id="59c7a-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="59c7a-329">Допустимые значения (и связанные с ними битовые положения) приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-330">1: включено для общедоступной службы обмена мгновенными сообщениями (разрядное расположение 0)</span><span class="sxs-lookup"><span data-stu-id="59c7a-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-331">2: зарезервировано (разрядное расположение 1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-332">4: зарезервировано (разрядное расположение 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-333">8: зарезервировано (разрядное расположение 3)</span><span class="sxs-lookup"><span data-stu-id="59c7a-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-334">16: удаленное управление звонками включено [телефония] (разрядность 4)</span><span class="sxs-lookup"><span data-stu-id="59c7a-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-335">64: АлловорганиземитингвисанонимауспартиЦипантс (разрешите пользователям приглашать анонимных пользователей к собраниям (разрядное расположение 6)</span><span class="sxs-lookup"><span data-stu-id="59c7a-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-336">128: Уценаблед (включение пользователей для единой системы обмена сообщениями) (разрядность 7)</span><span class="sxs-lookup"><span data-stu-id="59c7a-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-337">256: Енабледфоренханцедпресенце (включение пользователей для общедоступной службы обмена мгновенными сообщениями) (разрядное расположение 8)</span><span class="sxs-lookup"><span data-stu-id="59c7a-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-338">512: Ремотекаллконтролдуалмоде (разрядность 9)</span><span class="sxs-lookup"><span data-stu-id="59c7a-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-339">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-340">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="59c7a-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="59c7a-342">Этот атрибут указывает, загружены ли корпоративные службы на данном сервере.</span><span class="sxs-lookup"><span data-stu-id="59c7a-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-343">msRTCSIP-Екстенсиондата</span><span class="sxs-lookup"><span data-stu-id="59c7a-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-344">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-345">msRTCSIP-Екстерналакцесскоде</span><span class="sxs-lookup"><span data-stu-id="59c7a-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="59c7a-346">Этот атрибут включает код набора номера для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-347">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-348">msRTCSIP-Федератионенаблед</span><span class="sxs-lookup"><span data-stu-id="59c7a-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="59c7a-349">Этот атрибут определяет, включена ли Федерация для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="59c7a-350">Она принудительно применена уровнем корпоративных служб.</span><span class="sxs-lookup"><span data-stu-id="59c7a-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="59c7a-351">Оно помечено для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="59c7a-352">Допустимые значения: <strong>true</strong> или <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-353">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-354">msRTCSIP-Фронтендсерверс</span><span class="sxs-lookup"><span data-stu-id="59c7a-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="59c7a-355">Этот атрибут — Многозначный список доменных имен всех серверов Enterprise Edition, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="59c7a-356">Обратная ссылка: <strong>идентификатор ссылки 11023</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="59c7a-357">Соответствующая ссылка "вперед" на эту ссылку <strong>msRTCSIP-пуладдресс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-358">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-359">msRTCSIP — Gateways (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-360">Этот многозначный атрибут строки включает список шлюзов и портов (для шлюза).</span><span class="sxs-lookup"><span data-stu-id="59c7a-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="59c7a-361">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-362">msRTCSIP-Глобалсеттингсдата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-363">Этот атрибут хранит пары имя: значение.</span><span class="sxs-lookup"><span data-stu-id="59c7a-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="59c7a-364">В параметре " <strong>Разрешить опрос для проверки присутствия</strong> " указана уже определенная пара имя: значение.</span><span class="sxs-lookup"><span data-stu-id="59c7a-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-365">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-366">msRTCSIP-Граупингид</span><span class="sxs-lookup"><span data-stu-id="59c7a-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="59c7a-367">Этот атрибут является уникальным идентификатором группы, которая используется для группировки записей в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="59c7a-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-368">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-369">msRTCSIP-Хомесервер (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-370">Новые возможности Live Communications Server 2003 (не используется).</span><span class="sxs-lookup"><span data-stu-id="59c7a-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="59c7a-371">Устаревшие возможности для сервера Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-372">msRTCSIP-Хомесерверстринг (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-373">Новые возможности Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="59c7a-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="59c7a-374">Устаревшие возможности для сервера Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-375">msRTCSIP-Хомеусерс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-376">Новые возможности Live Communications Server 2003 (не используется).</span><span class="sxs-lookup"><span data-stu-id="59c7a-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="59c7a-377">Устаревшие возможности для сервера Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-378">msRTCSIP-Интернетакцессенаблед</span><span class="sxs-lookup"><span data-stu-id="59c7a-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="59c7a-379">Этот атрибут определяет, разрешено ли для одного пользователя доступ за пределы внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="59c7a-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="59c7a-380">Она принудительно применена уровнем корпоративных служб.</span><span class="sxs-lookup"><span data-stu-id="59c7a-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="59c7a-381">Оно помечено для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="59c7a-382">Допустимые значения: <strong>true</strong> или <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-383">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-384">msRTCSIP-Master (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-385">Новые возможности Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="59c7a-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="59c7a-386">Устаревшие возможности для сервера Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-387">msRTCSIP (линия)</span><span class="sxs-lookup"><span data-stu-id="59c7a-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="59c7a-388">Этот атрибут с одним значением включает идентификатор устройства (URI SIP или URI TEL телефона, который используются в Lync для телефонной связи).</span><span class="sxs-lookup"><span data-stu-id="59c7a-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="59c7a-389">Этот атрибут помечен для репликации глобального каталога и является индексированным.</span><span class="sxs-lookup"><span data-stu-id="59c7a-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="59c7a-390">Если для пользователя разрешена Корпоративная голосовая связь, этот атрибут сохраняет нормализованную версию E. 164 для номера телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-391">Новые возможности Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-392">msRTCSIP-Линесервер</span><span class="sxs-lookup"><span data-stu-id="59c7a-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="59c7a-393">Этот атрибут с одним значением включает URI SIP сервера шлюза КСТА-SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="59c7a-394">Этот атрибут помечен для репликации глобального каталога, но не индексирован.</span><span class="sxs-lookup"><span data-stu-id="59c7a-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-395">Новые возможности Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-396">msRTCSIP-Локалнормализатиондата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-397">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-398">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-399">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-400">msRTCSIP-Локалнормализатионлинкс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-401">Этот многозначный атрибут включает список локальных имен, различающих нормализацию (DN), связанных с этим профилем расположения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="59c7a-402">Тип этого атрибута — двоичный DN.</span><span class="sxs-lookup"><span data-stu-id="59c7a-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="59c7a-403">Существует связь "один ко многим" между профилем места и локальными правилами нормализации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="59c7a-404">Упорядочение списка локальных DNs-имен для нормализации должно поддерживаться в соответствии с порядком, указанным администратором.</span><span class="sxs-lookup"><span data-stu-id="59c7a-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="59c7a-405">Сохранение порядка поддерживается двоичной частью РАЗЛИЧАЮЩЕГОСЯ двоичного кода, указывающей индекс порядка.</span><span class="sxs-lookup"><span data-stu-id="59c7a-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="59c7a-406">Ссылка "вперед": <strong>ИД ссылки 11034</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="59c7a-407">Для обратной ссылки на этот атрибут прямой ссылки будет задано значение <strong>msRTCSIP-локатионпрофилебл</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-408">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-409">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-410">msRTCSIP-Локалнормализатионоптионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="59c7a-411">Этот атрибут включает список параметров для правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-412">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-413">msRTCSIP-Локатионнаме (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-414">Этот атрибут с одним значением содержит понятное имя для профиля расположения, показывающее, какое расположение представляет этот профиль.</span><span class="sxs-lookup"><span data-stu-id="59c7a-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="59c7a-415">Так как может быть несколько профилей местоположения, администратору нужно способ отличать различные профили.</span><span class="sxs-lookup"><span data-stu-id="59c7a-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-416">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-417">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-418">msRTCSIP-Локатионпрофилебл (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-419">Этот атрибут с несколькими значениями включает список различающихся имен для профиля расположения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="59c7a-420">Этот атрибут определяет обратную ссылку на один или несколько профилей местоположений.</span><span class="sxs-lookup"><span data-stu-id="59c7a-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="59c7a-421">Обратная ссылка: <strong>идентификатор ссылки 11035</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="59c7a-422">Этот атрибут соответствует ссылке "вперед" <strong>msRTCSIP-локалнормализатионлинкс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-423">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-424">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-425">msRTCSIP-Локатионпрофиледата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-426">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-427">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-428">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-429">msRTCSIP-Локатионпрофилеоптионс</span><span class="sxs-lookup"><span data-stu-id="59c7a-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="59c7a-430">Этот атрибут включает параметры для профиля расположения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-431">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-432">msRTCSIP-Маппингконтакт</span><span class="sxs-lookup"><span data-stu-id="59c7a-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="59c7a-433">Этот атрибут с несколькими значениями содержит список контактов приложения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-434">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-435">msRTCSIP-Маппинглокатион</span><span class="sxs-lookup"><span data-stu-id="59c7a-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="59c7a-436">Этот атрибут с несколькими значениями содержит список профилей местоположения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-437">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-438">msRTCSIP-Макснумаутстандингсеарчперсервер (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-439">Этот атрибут представляет максимальное количество ожидающих запросов на поиск на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="59c7a-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-440">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-441">msRTCSIP-Макснумсубскриптионсперусер (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-442">Атрибут представляет максимальное число подписок на одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-443">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-444">msRTCSIP-Макспресенцесубскриптионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-445">Этот атрибут представляет окно максимального времени ожидания подписки.</span><span class="sxs-lookup"><span data-stu-id="59c7a-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-446">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-447">msRTCSIP-Максрегистратионстимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-448">Этот атрибут представляет окно "максимальное время ожидания регистрации".</span><span class="sxs-lookup"><span data-stu-id="59c7a-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-449">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-450">msRTCSIP-Максроамингдатасубскриптионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-451">Этот атрибут представляет максимальное время ожидания подписки на подписку данных в роуминге.</span><span class="sxs-lookup"><span data-stu-id="59c7a-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-452">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-453">msRTCSIP-Мкудата</span><span class="sxs-lookup"><span data-stu-id="59c7a-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-454">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-455">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-456">msRTCSIP-Мкуфакторяддресс</span><span class="sxs-lookup"><span data-stu-id="59c7a-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="59c7a-457">Этот атрибут является атрибутом точки управления службой в классе компьютера, который указывает ссылку на фабрику элементов управления MultiPoint (MCU), к которой она относится.</span><span class="sxs-lookup"><span data-stu-id="59c7a-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="59c7a-458">Эта точка управления службой и атрибут создаются для каждого приложения Microsoft MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="59c7a-459">Каждый из Microsoft MCU должен найти сервер пула, к которому он принадлежит, чтобы получить из него параметры уровня пула.</span><span class="sxs-lookup"><span data-stu-id="59c7a-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="59c7a-460">Значение этого атрибута — различающееся имя (DN) фабрики MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="59c7a-461">Это атрибут с одним значением и помеченный для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="59c7a-462">Ссылка "вперед": <strong>ИД ссылки 11026</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="59c7a-463">Для обратной ссылки на этот атрибут прямой ссылки будет задано значение <strong>msRTCSIP-мкусерверс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-464">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-465">msRTCSIP-Мкуфакторидата</span><span class="sxs-lookup"><span data-stu-id="59c7a-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-466">Это многострочный атрибут, зарезервированный.</span><span class="sxs-lookup"><span data-stu-id="59c7a-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="59c7a-467">Параметры, хранящиеся в этом атрибуте, представлены в виде пар "имя = значение".</span><span class="sxs-lookup"><span data-stu-id="59c7a-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="59c7a-468">В настоящее время определены следующие пары name = value:</span><span class="sxs-lookup"><span data-stu-id="59c7a-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-469">Факторюрл = &lt;URL-адрес&gt;</span><span class="sxs-lookup"><span data-stu-id="59c7a-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-470">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-471">msRTCSIP-Мкуфакторипас</span><span class="sxs-lookup"><span data-stu-id="59c7a-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="59c7a-472">Это однозначный атрибут, который содержит различающееся имя (DN) одной фабрики MCU, связанной с пулом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="59c7a-473">Ссылка "вперед": <strong>ИД ссылки 11024</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="59c7a-474">Для обратной ссылки на этот атрибут прямой ссылки будет задано значение <strong>msRTCSIP-пуладдрессес</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-475">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-476">msRTCSIP-Мкуфакторипровидерид</span><span class="sxs-lookup"><span data-stu-id="59c7a-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="59c7a-477">Этот атрибут является однозначной строкой, которая определяет GUID поставщика фабрики MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="59c7a-478">На основе значения GUID процесс фабрики MCU определяет, нужно ли обслуживать этот тип MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="59c7a-479">Если значение GUID — <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, процесс фабрики MCU (доступен по умолчанию в Lync Server) будет обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="59c7a-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="59c7a-480">Для любого другого значения GUID процесс фабрики MCU не будет обслуживать тип MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-481">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-482">msRTCSIP-Мкусерверс</span><span class="sxs-lookup"><span data-stu-id="59c7a-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="59c7a-483">Этот атрибут представляет собой список различающихся имен (DN) с несколькими значениями.</span><span class="sxs-lookup"><span data-stu-id="59c7a-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="59c7a-484">Этот атрибут представляет список всех серверов MCU одного и того же типа и поставщика, связанных с этой фабрикой MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="59c7a-485">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="59c7a-486">Обратная ссылка: идентификатор ссылки 11027</span><span class="sxs-lookup"><span data-stu-id="59c7a-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="59c7a-487">Соответствующая ссылка "вперед" на эту ссылку <strong>msRTCSIP-мкуфакторяддресс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-488">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-489">msRTCSIP-Мкутипе</span><span class="sxs-lookup"><span data-stu-id="59c7a-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="59c7a-490">Этот атрибут является однозначной строкой, указывающей на то, что MCU может обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="59c7a-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="59c7a-491">Поддерживаются следующие допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="59c7a-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-492">зала</span><span class="sxs-lookup"><span data-stu-id="59c7a-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="59c7a-493">аудио-видео</span><span class="sxs-lookup"><span data-stu-id="59c7a-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="59c7a-494">сеанс</span><span class="sxs-lookup"><span data-stu-id="59c7a-494">chat</span></span></p></li>
<li><p><span data-ttu-id="59c7a-495">Phone-CONF</span><span class="sxs-lookup"><span data-stu-id="59c7a-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-496">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-497">msRTCSIP-Мкувендор</span><span class="sxs-lookup"><span data-stu-id="59c7a-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="59c7a-498">Этот атрибут является однозначной строкой, указывающей имя поставщика MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="59c7a-499">В Microsoft Мкус этот атрибут будет указан в <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-500">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-501">msRTCSIP-Митингфлагс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-502">Этот атрибут определяет различные параметры собрания, которые включаются глобально для всех пользователей или объектов контактов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="59c7a-503">Этот атрибут является значением битовой маски целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="59c7a-504">Допустимые значения (и связанные с ними битовые положения) приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-505">0: АлловорганиземитингвисанонимауспартиЦипантс имеет значение None (не разрешать пользователям приглашать анонимных пользователей для собраний) (никакие биты не установлены).</span><span class="sxs-lookup"><span data-stu-id="59c7a-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-506">4: АлловорганиземитингвисанонимауспартиЦипантс — все пользователи (разрешающие собрания анонимных пользователей) (разрядное расположение 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-507">8: АлловорганиземитингвисанонимауспартиЦипантс — Усеперусерсеттинг (разрешите пользователям приглашать анонимных пользователей для собраний на основе параметров пользователя) (разрядное положение 3).</span><span class="sxs-lookup"><span data-stu-id="59c7a-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-508">16: Усерперусермитингполици (определена политика собраний для пользователей) (битовая разряда 4)</span><span class="sxs-lookup"><span data-stu-id="59c7a-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-509">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-510">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-511">msRTCSIP-Митингполици (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-512">Этот атрибут указывает различающееся имя (DN) политики, назначенной администратором для этого пользователя в качестве атрибута с одним значением.</span><span class="sxs-lookup"><span data-stu-id="59c7a-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-513">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-514">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-515">msRTCSIP-Минпресенцесубскриптионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-516">Этот атрибут представляет окно минимального времени ожидания подписки на присутствие.</span><span class="sxs-lookup"><span data-stu-id="59c7a-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-517">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-518">msRTCSIP-Минрегистратионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-519">Этот атрибут представляет окно минимального времени ожидания регистрации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-520">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-521">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-522">msRTCSIP-Минроамингдатасубскриптионтимеаут (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-523">Этот атрибут представляет временное время ожидания подписки на подписку данных в роуминге.</span><span class="sxs-lookup"><span data-stu-id="59c7a-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-524">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-525">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-526">msRTCSIP-Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="59c7a-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="59c7a-527">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="59c7a-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-528">Новые возможности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59c7a-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-529">msRTCSIP-Мобилитифлагс</span><span class="sxs-lookup"><span data-stu-id="59c7a-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="59c7a-530">Этот атрибут включает параметры и флаги, определяющие параметры мобильности.</span><span class="sxs-lookup"><span data-stu-id="59c7a-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-531">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-532">msRTCSIP-Мобилитиполици</span><span class="sxs-lookup"><span data-stu-id="59c7a-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="59c7a-533">Этот атрибут включает DN для объекта политики мобильности.</span><span class="sxs-lookup"><span data-stu-id="59c7a-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-534">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-535">msRTCSIP-Нумдевицесперусер (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-536">Этот атрибут представляет допустимое количество устройств, на которые пользователь может зарегистрироваться для связи с SIP, и оформить подписку на состояние присутствия.</span><span class="sxs-lookup"><span data-stu-id="59c7a-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-537">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-538">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-539">msRTCSIP-Оптионфлагс</span><span class="sxs-lookup"><span data-stu-id="59c7a-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="59c7a-540">Этот атрибут определяет параметры, доступные для объекта пользователя или контакта.</span><span class="sxs-lookup"><span data-stu-id="59c7a-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="59c7a-541">Этот атрибут является значением битовой маски типа Integer.</span><span class="sxs-lookup"><span data-stu-id="59c7a-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="59c7a-542">Каждый параметр представлен битом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-542">Each option is represented by a bit.</span></span> <span data-ttu-id="59c7a-543">Этот атрибут помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="59c7a-544">Допустимые значения (и связанные с ними битовые положения) приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-545">1: включено для общедоступной службы обмена мгновенными сообщениями (с битовой позицией 0)</span><span class="sxs-lookup"><span data-stu-id="59c7a-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-546">2: зарезервировано (разрядное расположение 1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-547">4: зарезервировано (разрядное расположение 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-548">8: зарезервировано (разрядное расположение 3)</span><span class="sxs-lookup"><span data-stu-id="59c7a-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-549">16: удаленное управление звонками включено [телефония] (разрядность 4)</span><span class="sxs-lookup"><span data-stu-id="59c7a-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-550">64: АлловорганиземитингвисанонимауспартиЦипантс (разрешите пользователям приглашать анонимных пользователей к собраниям (разрядное расположение 6)</span><span class="sxs-lookup"><span data-stu-id="59c7a-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-551">128: Уценаблед (разрешение пользователей на UC) (разрядность 7)</span><span class="sxs-lookup"><span data-stu-id="59c7a-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-552">256: Енабледфоренханцедпресенце (включение пользователей для общедоступной службы обмена мгновенными сообщениями) (разрядное расположение 8)</span><span class="sxs-lookup"><span data-stu-id="59c7a-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-553">512: Ремотекаллконтролдуалмоде (разрядность 9)</span><span class="sxs-lookup"><span data-stu-id="59c7a-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-554">Новые возможности Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="59c7a-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="59c7a-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="59c7a-556">Этот атрибут используется в топологиях ресурсов и центральных лесах для включения единого входа, если пользователь ObjectSID из учетной записи участника Windows NT Server копируется в этот атрибут соответствующего объекта пользователя или контакта в ресурсе или центральном лесе.</span><span class="sxs-lookup"><span data-stu-id="59c7a-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="59c7a-557">Служба Communicator Web Access осуществляет поиск пользователя в доменных СЛУЖБах Active Directory с помощью этого атрибута или ObjectSID пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="59c7a-558">Этот атрибут помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-559">msRTCSIP-Овнерурн</span><span class="sxs-lookup"><span data-stu-id="59c7a-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="59c7a-560">Этот атрибут представляет собой унифицированное имя ресурса (URN) владельца для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-561">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-562">Шаблон msRTCSIP (устаревший)</span><span class="sxs-lookup"><span data-stu-id="59c7a-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-563">Этот однозначный атрибут String включает шаблон, используемый для сопоставления номеров набора с форматом E. 164.</span><span class="sxs-lookup"><span data-stu-id="59c7a-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="59c7a-564">Если номер набора номера соответствует этому шаблону, для набора номера применяется перевод.</span><span class="sxs-lookup"><span data-stu-id="59c7a-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-565">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-566">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-567">msRTCSIP-Фонераутебл (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-568">Этот атрибут с несколькими значениями имеет список различающихся имен для маршрутных маршрутов (DN).</span><span class="sxs-lookup"><span data-stu-id="59c7a-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="59c7a-569">Этот атрибут определяет обратную ссылку на один или несколько телефонных маршрутов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="59c7a-570">Обратная ссылка: <strong>идентификатор ссылки 11033</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="59c7a-571">Этот атрибут соответствует ссылке "вперед" <strong>msRTCSIP-раутеусажелинкс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-572">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-573">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-574">msRTCSIP-Фонераутедата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-575">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-576">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-577">msRTCSIP-Фонераутенаме (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-578">Этот однозначный строковый атрибут Юникода определяет понятное имя маршрута, поэтому на него может легко ссылаться администратор.</span><span class="sxs-lookup"><span data-stu-id="59c7a-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-579">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-580">msRTCSIP-Фонеусажедата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-581">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-582">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-583">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-584">msRTCSIP-Полициконтент (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-585">Этот атрибут является строкой Юникода с одним значением.</span><span class="sxs-lookup"><span data-stu-id="59c7a-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="59c7a-586">Этот атрибут String включает определение политики в формате XML.</span><span class="sxs-lookup"><span data-stu-id="59c7a-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="59c7a-587">Определение схемы XML является общим для разных типов политик, но для каждого типа политики различаются только параметры.</span><span class="sxs-lookup"><span data-stu-id="59c7a-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="59c7a-588">Определение схемы XML (XSD) определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59c7a-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="59c7a-589">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-590">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-591">msRTCSIP-Полицидата (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-592">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-593">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-594">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-595">msRTCSIP-Полицитипе (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-596">Этот однозначный атрибут строки Юникод включает тип политики.</span><span class="sxs-lookup"><span data-stu-id="59c7a-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="59c7a-597">Ниже указаны допустимые типы политик.</span><span class="sxs-lookup"><span data-stu-id="59c7a-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-598">зала</span><span class="sxs-lookup"><span data-stu-id="59c7a-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="59c7a-599">телефонии</span><span class="sxs-lookup"><span data-stu-id="59c7a-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-600">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-601">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-602">msRTCSIP-Пуладдресс</span><span class="sxs-lookup"><span data-stu-id="59c7a-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="59c7a-603">Этот атрибут указывает ссылку обратно в пул, к которому принадлежит компьютер.</span><span class="sxs-lookup"><span data-stu-id="59c7a-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="59c7a-604">Этот атрибут задается независимо от того, работает ли на компьютере выпуск Standard Edition или выпуск Enterprise Edition для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59c7a-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="59c7a-605">Этот атрибут помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="59c7a-606">Допустимым значением является доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="59c7a-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="59c7a-607">Ссылка "вперед": <strong>ИД ссылки 11022</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="59c7a-608">Для обратной ссылки на этот атрибут прямой ссылки будет задано значение <strong>msRTCSIP-фронтендсерверс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-609">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-610">msRTCSIP-Пуладдрессес</span><span class="sxs-lookup"><span data-stu-id="59c7a-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="59c7a-611">Это многозначный атрибут, содержащий список различающихся имен (DN) пулов, с которым связана фабрика MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="59c7a-612">Обратная ссылка: <strong>идентификатор ссылки 11025</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="59c7a-613">Соответствующая ссылка "вперед" на эту ссылку <strong>msRTCSIP-мкуфакторипас</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-614">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-615">msRTCSIP-Пулдата</span><span class="sxs-lookup"><span data-stu-id="59c7a-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-616">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-617">Новые возможности Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="59c7a-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-618">msRTCSIP-Пулдисплайнаме</span><span class="sxs-lookup"><span data-stu-id="59c7a-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="59c7a-619">Этот атрибут указывает произвольное имя для пула, отображаемого на консоли управления.</span><span class="sxs-lookup"><span data-stu-id="59c7a-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="59c7a-620">Это имя может быть изменено администратором.</span><span class="sxs-lookup"><span data-stu-id="59c7a-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="59c7a-621">Допустимым значением является строка, представляющая имя пула.</span><span class="sxs-lookup"><span data-stu-id="59c7a-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-622">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-623">msRTCSIP-Пулдомаинфкдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-624">Этот атрибут представляет собой строковое значение с одним значением.</span><span class="sxs-lookup"><span data-stu-id="59c7a-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="59c7a-625">Значение этого атрибута (при наличии) представляет доменное имя домена пула, если администратор хочет создать пул переднего плана с полным доменным именем, не соответствующим структуре домена Active Directory, для которой создается пул переднего плана (например, SIP). пространство имен, исключенное из пространства имен DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="59c7a-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="59c7a-626">Мы рекомендуем сопоставить полное доменное имя домена пула с именем домена в качестве домена Active Directory, в котором находится пул.</span><span class="sxs-lookup"><span data-stu-id="59c7a-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="59c7a-627">Таким образом, если в этом атрибуте значение не указано, то ДОМЕНное имя пула переднего плана по умолчанию будет представлять собой структуру доменных имен Active Directory, как указано в атрибуте <strong>dnsHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="59c7a-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-628">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-629">msRTCSIP-Пулфунктионалити</span><span class="sxs-lookup"><span data-stu-id="59c7a-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="59c7a-630">Многозначный список доменных имен всех серверов Lync Server, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="59c7a-631">Этот атрибут типа Integer определяет, может ли пул обмениваться мгновенными сообщениями и сведениями о присутствии и собраниях.</span><span class="sxs-lookup"><span data-stu-id="59c7a-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="59c7a-632">Возможны следующие допустимые типы значений:</span><span class="sxs-lookup"><span data-stu-id="59c7a-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-633">Не определено: служба обмена мгновенными сообщениями и сведениями о присутствии (сервер Live Communications Server 2005 и 2003)</span><span class="sxs-lookup"><span data-stu-id="59c7a-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-634">1: служба мгновенных сообщений и присутствие (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="59c7a-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-635">2: обмен мгновенными сообщениями и служба сведений о присутствии и собраниях (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="59c7a-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-636">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-637">msRTCSIP-Пултипе</span><span class="sxs-lookup"><span data-stu-id="59c7a-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="59c7a-638">Этот атрибут указывает, работает ли серверный пул на сервере Standard Edition Server или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="59c7a-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="59c7a-639">Этот атрибут является значением битовой маски типа Integer.</span><span class="sxs-lookup"><span data-stu-id="59c7a-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="59c7a-640">Каждый параметр представлен битом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="59c7a-641">Допустимые значения (и связанные с ними битовые положения) приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-642">1: сервер Standard Edition, пользователи hosts (разрядное расположение 0)</span><span class="sxs-lookup"><span data-stu-id="59c7a-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-643">2: выпуск Enterprise Edition, пользователи hosts (разрядное расположение 1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-644">4: сервер Standard Edition, приложения hosts (разрядное расположение 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-645">8: сервер Enterprise Edition, приложения hosts (разрядное расположение 3)</span><span class="sxs-lookup"><span data-stu-id="59c7a-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="59c7a-646">Поскольку Lync Server не поддерживает пулы, в которых размещаются только приложения, допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="59c7a-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-647">5: Standard Edition Server, узлы пользователей и приложения (битовые позиции 0 и 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-648">10: Enterprise Edition Server, узлы пользователей и приложения (битовые позиции 1 и 3)</span><span class="sxs-lookup"><span data-stu-id="59c7a-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-649">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-650">msRTCSIP-Пулверсион</span><span class="sxs-lookup"><span data-stu-id="59c7a-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="59c7a-651">Этот атрибут определяет версию пула.</span><span class="sxs-lookup"><span data-stu-id="59c7a-651">This attribute defines the pool version.</span></span> <span data-ttu-id="59c7a-652">Это целочисленный тип, который увеличивается при использовании каждого основного выпуска продукта.</span><span class="sxs-lookup"><span data-stu-id="59c7a-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="59c7a-653">Возможны следующие допустимые типы значений:</span><span class="sxs-lookup"><span data-stu-id="59c7a-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-654">0: сервер Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="59c7a-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="59c7a-655">1: сервер Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="59c7a-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="59c7a-656">2: сервер Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="59c7a-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="59c7a-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="59c7a-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="59c7a-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="59c7a-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="59c7a-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-660">Сервер Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="59c7a-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-661">msRTCSIP-Пресенцефлагс</span><span class="sxs-lookup"><span data-stu-id="59c7a-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="59c7a-662">Этот атрибут включает параметры и флаги, определяющие параметры присутствия.</span><span class="sxs-lookup"><span data-stu-id="59c7a-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-663">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-664">msRTCSIP-Пресенцеполици</span><span class="sxs-lookup"><span data-stu-id="59c7a-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="59c7a-665">Этот атрибут включает DN для объекта политики присутствия.</span><span class="sxs-lookup"><span data-stu-id="59c7a-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-666">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-667">msRTCSIP-Примарихомесервер</span><span class="sxs-lookup"><span data-stu-id="59c7a-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="59c7a-668">Этот атрибут позволяет пользователю или контакту для обмена сообщениями SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="59c7a-669">Он добавляется в класс Contact, так как в топологии центрального леса, объекты контактов, а не пользовательские объекты — включена поддержка SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="59c7a-670">Допустимым значением является различающееся имя пула переднего плана сервера Standard Edition или корпоративного выпуска Enterprise Edition, где находится пользователь.</span><span class="sxs-lookup"><span data-stu-id="59c7a-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-671">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="59c7a-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="59c7a-673">Этот атрибут включает адрес SIP определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-674">msRTCSIP-Привателине</span><span class="sxs-lookup"><span data-stu-id="59c7a-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="59c7a-675">Этот атрибут представляет идентификатор устройства для частной линии устройства.</span><span class="sxs-lookup"><span data-stu-id="59c7a-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-676">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-677">msRTCSIP с маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="59c7a-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="59c7a-678">Этот атрибут является логическим атрибутом, используемым для определения того, авторизован ли Lync Server для маршрутизации к этой службе с помощью ее адреса ГРУУ.</span><span class="sxs-lookup"><span data-stu-id="59c7a-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="59c7a-679">Если для этого параметра установлено значение <strong>true</strong>, Lync Server авторизован для маршрутизации к этой службе.</span><span class="sxs-lookup"><span data-stu-id="59c7a-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="59c7a-680">Если для этого параметра задано значение <strong>false</strong>, Lync Server не уполномочен для маршрутизации к этой службе.</span><span class="sxs-lookup"><span data-stu-id="59c7a-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-681">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-682">msRTCSIP-Раутеусажеаттрибуте (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-683">Этот однозначный атрибут String Юникода определяет атрибут, который позволяет определять использование для телефонного маршрута.</span><span class="sxs-lookup"><span data-stu-id="59c7a-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="59c7a-684">Выбор номера телефона определяется на основе двух элементов: атрибута использования, назначенного для телефонного маршрута, и атрибутов использования, разрешенных вызывающим участником.</span><span class="sxs-lookup"><span data-stu-id="59c7a-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="59c7a-685">Первый телефонный маршрут с атрибутом использования, соответствующим разрешенному использованию вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="59c7a-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-686">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-687">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-688">msRTCSIP-Раутеусажелинкс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-689">Этот атрибут различающегося многозначного имени (DN) включает список различающихся имен, используемых маршрутами.</span><span class="sxs-lookup"><span data-stu-id="59c7a-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="59c7a-690">Ссылка "вперед": <strong>ИД ссылки 11032</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="59c7a-691">Этот атрибут является прямой ссылкой на соответствующую обратную ссылку <strong>msRTCSIP-фонераутебл</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-692">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-693">msRTCSIP-Раутингпулдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-694">Этот атрибут включает DN, указывающий на пул, который должен пройти весь трафик SIP, адресованный данной MCU или доверенной службе.</span><span class="sxs-lookup"><span data-stu-id="59c7a-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-695">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-696">msRTCSIP-Руленаме (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-697">Этот однозначный строковый атрибут Юникода задает понятное имя правила нормализации, поэтому на него может легко ссылаться администратор.</span><span class="sxs-lookup"><span data-stu-id="59c7a-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-698">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-699">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="59c7a-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="59c7a-701">Этот атрибут представляет версию схемы, которая в данный момент развернута в Организации.</span><span class="sxs-lookup"><span data-stu-id="59c7a-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-702">msRTCSIP-Сеарчмаксрекуестс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-703">Этот атрибут ограничивает число результатов поиска, возвращаемое при поиске в каталоге, когда пользователь осуществляет поиск контакта с помощью Communicator.</span><span class="sxs-lookup"><span data-stu-id="59c7a-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="59c7a-704">Этот атрибут будет переопределять значение, указанное клиентом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-705">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-706">msRTCSIP-Сеарчмаксресултс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-707">Этот атрибут ограничивает количество возвращаемых запросов поиска.</span><span class="sxs-lookup"><span data-stu-id="59c7a-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-708">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-709">msRTCSIP-Сервербл</span><span class="sxs-lookup"><span data-stu-id="59c7a-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="59c7a-710">Этот атрибут с несколькими значениями является обратной ссылкой, которая содержит список различающихся имен (DN).</span><span class="sxs-lookup"><span data-stu-id="59c7a-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="59c7a-711">Эти точки DNs для пула или объекта <strong>трустедсервице</strong> .</span><span class="sxs-lookup"><span data-stu-id="59c7a-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="59c7a-712">Этот атрибут соответствует ссылке "вперед" <strong>msRTCSIP-трустедсервицелинкс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-713">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-714">msRTCSIP-Сервердата</span><span class="sxs-lookup"><span data-stu-id="59c7a-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-715">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-716">msRTCSIP-Серверреференцебл (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-717">Этот атрибут с несколькими значениями включает список различающихся имен.</span><span class="sxs-lookup"><span data-stu-id="59c7a-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="59c7a-718">Эти отличительные имена представляют собой обратные ссылки, которые ссылаются на другие объекты сервера, которые можно назначить профилю расположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="59c7a-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="59c7a-719">Обратная ссылка: <strong>идентификатор ссылки 11037</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="59c7a-720">Соответствующая ссылка "вперед" на эту ссылку <strong>msRTCSIP-дефаултлокатионпрофилелинк</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="59c7a-721">Этот атрибут обратной связи указывает только на пулы и серверы исправлений.</span><span class="sxs-lookup"><span data-stu-id="59c7a-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-722">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-723">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-724">msRTCSIP-Серверверсион</span><span class="sxs-lookup"><span data-stu-id="59c7a-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="59c7a-725">Этот атрибут определяет сведения о версии сервера.</span><span class="sxs-lookup"><span data-stu-id="59c7a-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="59c7a-726">Этот номер версии действует для всех ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="59c7a-726">This version number applies to all server roles.</span></span> <span data-ttu-id="59c7a-727">Это монотонаусли увеличивает целое число, которое увеличивается при использовании каждого официального выпуска продукта.</span><span class="sxs-lookup"><span data-stu-id="59c7a-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="59c7a-728">Возможны следующие допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="59c7a-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-729">Не определено: сервер Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="59c7a-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="59c7a-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="59c7a-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="59c7a-731">                 Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="59c7a-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="59c7a-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="59c7a-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="59c7a-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="59c7a-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="59c7a-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="59c7a-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="59c7a-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c7a-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-736">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-737">msRTCSIP-Саурцеобжекттипе</span><span class="sxs-lookup"><span data-stu-id="59c7a-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="59c7a-738">Этот атрибут с одним значением целочисленного типа задает тип объекта, на который указывает <strong>msDS-саурцеобжектдн</strong> , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-739">NULL | 0x00000001: предоставляет объект пользователя-участника Windows NT Server из другого леса.</span><span class="sxs-lookup"><span data-stu-id="59c7a-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="59c7a-740">Следующие атрибуты представляют типы групп из другого леса для развертывания групп рассылки.</span><span class="sxs-lookup"><span data-stu-id="59c7a-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-741">0x00000002: АДС_ГРАУП_ТИПЕ_ГЛОБАЛ_ГРАУП</span><span class="sxs-lookup"><span data-stu-id="59c7a-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="59c7a-742">0x00000004: АДС_ГРАУП_ТИПЕ_ДОМАИН_ЛОКАЛ_ГРАУП</span><span class="sxs-lookup"><span data-stu-id="59c7a-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="59c7a-743">0x00000004: АДС_ГРАУП_ТИПЕ_ЛОКАЛ_ГРАУП</span><span class="sxs-lookup"><span data-stu-id="59c7a-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="59c7a-744">0x00000008: АДС_ГРАУП_ТИПЕ_УНИВЕРСАЛ_ГРАУП</span><span class="sxs-lookup"><span data-stu-id="59c7a-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="59c7a-745">0x80000000: АДС_ГРАУП_ТИПЕ_СЕКУРИТИ_ЕНАБЛЕД</span><span class="sxs-lookup"><span data-stu-id="59c7a-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="59c7a-746">0x90000000: представляет объект автоматического ассистента или абонентского доступа из того же леса или другого леса.</span><span class="sxs-lookup"><span data-stu-id="59c7a-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-747">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-748">msRTCSIP-Субскриптионаусрекуиред (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-749">Новые возможности Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="59c7a-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="59c7a-750">Устаревшие возможности для сервера Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-751">msRTCSIP-Таржесомесервер</span><span class="sxs-lookup"><span data-stu-id="59c7a-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="59c7a-752">Этот атрибут позволяет переместить пользователя или объект контакта из одного пула сервера Lync Server в другой.</span><span class="sxs-lookup"><span data-stu-id="59c7a-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="59c7a-753">Этот атрибут добавляется в класс Contact, так как в топологии центрального леса, объекты контактов, а не объекты пользователя, включены модули SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="59c7a-754">Допустимым значением является DN сервера назначения Standard Edition или переднего плана, в который нужно переместить пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-755">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-756">msRTCSIP-Таржетфоненумбер (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-757">Этот однозначный атрибут String включает шаблон номера телефона или диапазон, который направляется на указанные шлюзы, определенные в <strong>msRTCSIP-Gateway</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-758">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-759">msRTCSIP-ТаржетусерполиЦиес</span><span class="sxs-lookup"><span data-stu-id="59c7a-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="59c7a-760">Этот атрибут хранит пары "имя-значение" для конечных политик пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59c7a-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-761">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="59c7a-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="59c7a-763">Этот атрибут хранит уникальный идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="59c7a-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-764">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-765">msRTCSIP-трансляция (устаревшая)</span><span class="sxs-lookup"><span data-stu-id="59c7a-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-766">Этот атрибут используется функцией голосовой связи в Lync Server и содержит строку перевода, применяемую при наборе номера, если найдено соответствие.</span><span class="sxs-lookup"><span data-stu-id="59c7a-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-767">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="59c7a-768">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-769">msRTCSIP-Трустедмкудата</span><span class="sxs-lookup"><span data-stu-id="59c7a-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-770">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-771">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-772">msRTCSIP-Трустедмкуфкдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-773">Этот атрибут представляет собой строковое значение, содержащее полное доменное имя MCU.</span><span class="sxs-lookup"><span data-stu-id="59c7a-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="59c7a-774">Это атрибут с одним значением.</span><span class="sxs-lookup"><span data-stu-id="59c7a-774">This is a single-valued attribute.</span></span> <span data-ttu-id="59c7a-775">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-776">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-777">msRTCSIP-Трустедпроксидата</span><span class="sxs-lookup"><span data-stu-id="59c7a-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-778">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-779">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-780">msRTCSIP-Трустедпроксифкдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-781">Этот атрибут представляет собой строковое значение, содержащее полное доменное имя сервера, на котором запущен прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="59c7a-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="59c7a-782">Этот атрибут является однозначным.</span><span class="sxs-lookup"><span data-stu-id="59c7a-782">This attribute is single-valued.</span></span> <span data-ttu-id="59c7a-783">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-784">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-785">msRTCSIP-Трустедсервердата</span><span class="sxs-lookup"><span data-stu-id="59c7a-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-786">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-787">msRTCSIP-Трустедсерверфкдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-788">Этот атрибут является атрибутом с одним значением, представляющим полное доменное имя доверенного сервера.</span><span class="sxs-lookup"><span data-stu-id="59c7a-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-789">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-790">msRTCSIP-Трустедсерверверсион</span><span class="sxs-lookup"><span data-stu-id="59c7a-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="59c7a-791">Этот атрибут указывает номер версии сервера в списке надежных серверов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="59c7a-792">Возможны следующие допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="59c7a-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-793">NULL: сервер Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="59c7a-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="59c7a-794">2: сервер Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="59c7a-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="59c7a-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="59c7a-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="59c7a-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="59c7a-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="59c7a-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="59c7a-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="59c7a-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c7a-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-799">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-800">msRTCSIP-Трустедсервицефлагс</span><span class="sxs-lookup"><span data-stu-id="59c7a-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="59c7a-801">Этот атрибут определяет параметры, включенные для доверенной службы.</span><span class="sxs-lookup"><span data-stu-id="59c7a-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-802">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-803">msRTCSIP-Трустедсервицелинкс</span><span class="sxs-lookup"><span data-stu-id="59c7a-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="59c7a-804">Этот атрибут с несколькими значениями включает список отличительных имен (DN), которые ссылаются на доверенный объект службы, например службу проверки подлинности мультимедиа-ретрансляции.</span><span class="sxs-lookup"><span data-stu-id="59c7a-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="59c7a-805">Служба проверки подлинности мультимедиа-ретрансляции (которая физически размещена на пограничном сервере, выполняющем службу конференц-связи) должна быть связана с пулом, чтобы поддерживать звуковые сценарии для удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="59c7a-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="59c7a-806">Для обратной ссылки на этот атрибут прямой ссылки будет задано значение <strong>msRTCSIP-сервербл</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-807">ПЛАТФОРМЫ</span><span class="sxs-lookup"><span data-stu-id="59c7a-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-808">msRTCSIP-Трустедсервицепорт</span><span class="sxs-lookup"><span data-stu-id="59c7a-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="59c7a-809">Этот атрибут является целым числом, определяющим номер порта, который используется для подключения к этой службе ГРУУ.</span><span class="sxs-lookup"><span data-stu-id="59c7a-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-810">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-811">msRTCSIP-Трустедсервицетипе</span><span class="sxs-lookup"><span data-stu-id="59c7a-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="59c7a-812">Этот атрибут представляет собой строковое значение, определяющее тип ГРУУ службы.</span><span class="sxs-lookup"><span data-stu-id="59c7a-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="59c7a-813">Допустимые типы служб ГРУУ описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="59c7a-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="59c7a-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="59c7a-815">Шлюз</span><span class="sxs-lookup"><span data-stu-id="59c7a-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="59c7a-816">Служба проверки подлинности мультимедиа-ретрансляции (МРАС)</span><span class="sxs-lookup"><span data-stu-id="59c7a-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="59c7a-817">Косм</span><span class="sxs-lookup"><span data-stu-id="59c7a-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="59c7a-818">msRTCSIP — Усерекстенсион кВА</span><span class="sxs-lookup"><span data-stu-id="59c7a-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-819">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-820">msRTCSIP-Трустедвебкомпонентссервердата</span><span class="sxs-lookup"><span data-stu-id="59c7a-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-821">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-822">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-823">msRTCSIP-Трустедвебкомпонентссерверфкдн</span><span class="sxs-lookup"><span data-stu-id="59c7a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="59c7a-824">Этот атрибут представляет собой строковое значение, содержащее полные доменные имена для IIS, на котором выполняются веб-службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59c7a-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="59c7a-825">Это атрибут с одним значением.</span><span class="sxs-lookup"><span data-stu-id="59c7a-825">This is a single-valued attribute.</span></span> <span data-ttu-id="59c7a-826">Допустимые значения для каждого сегмента — 63 символов; допустимое значение полного доменного имени — 255 символов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-827">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-828">msRTCSIP-Укфлагс (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-829">Этот атрибут определяет различные параметры UC, которые включаются глобально для всех пользователей и объектов контактов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="59c7a-830">Этот атрибут является значением битовой маски целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="59c7a-831">Каждый вариант представляется наличием бита.</span><span class="sxs-lookup"><span data-stu-id="59c7a-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="59c7a-832">Возможны следующие допустимые значения (и связанное расположение битов).</span><span class="sxs-lookup"><span data-stu-id="59c7a-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-833">4: Усеперусерукполици (разрядное расположение 2)</span><span class="sxs-lookup"><span data-stu-id="59c7a-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="59c7a-834">Если задан этот бит, политика UC определена для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-835">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-836">msRTCSIP-Укполици (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-837">Этот атрибут с одним значением содержит различающееся имя (DN) политики UC, которой назначен администратор для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-838">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-839">msRTCSIP-Усердомаинлист (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="59c7a-840">Этот атрибут предоставляет список всех доменов в лесу, которые размещает пользователей с поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="59c7a-841">По умолчанию это пустой список, указывающий на то, что все домены в лесу включены с поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="59c7a-842">Допустимые значения — это несколько строк, представляющих доменные имена отдельных доменов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-843">Новые возможности Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="59c7a-844">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="59c7a-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="59c7a-846">Этот атрибут определяет, разрешено ли в данный момент пользователь Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59c7a-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-847">msRTCSIP-Усерекстенсион</span><span class="sxs-lookup"><span data-stu-id="59c7a-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="59c7a-848">Этот атрибут с несколькими значениями включает список пар "имя-значение" в формате &quot;name = value. &quot; Этот атрибут помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="59c7a-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-849">Новые возможности Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="59c7a-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-850">msRTCSIP-Усерлокатионпрофиле</span><span class="sxs-lookup"><span data-stu-id="59c7a-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="59c7a-851">Этот атрибут включает различающееся имя (DN), которое указывает на объект профиля расположения.</span><span class="sxs-lookup"><span data-stu-id="59c7a-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-852">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="59c7a-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-853">msRTCSIP-УсерполиЦиес</span><span class="sxs-lookup"><span data-stu-id="59c7a-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="59c7a-854">Этот атрибут хранит пары "имя-значение" для политик пользователей.</span><span class="sxs-lookup"><span data-stu-id="59c7a-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-855">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59c7a-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-856">msRTCSIP-Усерполици</span><span class="sxs-lookup"><span data-stu-id="59c7a-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="59c7a-857">Это многозначный атрибут, содержащий список различающихся имен с двоичной (ДН_ВИС_БИНАРИ), указывающей на глобальные политики пользователей различных типов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="59c7a-858">Двоичная часть указывает тип политики, на которую указывает область DN.</span><span class="sxs-lookup"><span data-stu-id="59c7a-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="59c7a-859">Допустимы следующие двоичные значения:</span><span class="sxs-lookup"><span data-stu-id="59c7a-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-860">0x00000001: политика собраний</span><span class="sxs-lookup"><span data-stu-id="59c7a-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="59c7a-861">0x00000002: политика UC</span><span class="sxs-lookup"><span data-stu-id="59c7a-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="59c7a-862">0x00000005: политика присутствия</span><span class="sxs-lookup"><span data-stu-id="59c7a-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-863">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-864">msRTCSIP-Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="59c7a-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="59c7a-865">Это идентификатор группы маршрутизации SIP.</span><span class="sxs-lookup"><span data-stu-id="59c7a-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="59c7a-866">Пользователи в одной группе будут регистрироваться на одном и том же внешнем сервере.</span><span class="sxs-lookup"><span data-stu-id="59c7a-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-867">Новые возможности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59c7a-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-868">msRTCSIP-Вебкомпонентсдата</span><span class="sxs-lookup"><span data-stu-id="59c7a-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="59c7a-869">Это атрибут с несколькими значениями.</span><span class="sxs-lookup"><span data-stu-id="59c7a-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="59c7a-870">Этот атрибут зарезервирован для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="59c7a-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-871">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-872">msRTCSIP-Вебкомпонентспуладдресс</span><span class="sxs-lookup"><span data-stu-id="59c7a-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="59c7a-873">Этот атрибут с одним значением указывает на сервер пула или стандартный выпуск, к которому относятся веб-компоненты.</span><span class="sxs-lookup"><span data-stu-id="59c7a-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="59c7a-874">Ссылка "вперед": <strong>ИД ссылки 11028</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="59c7a-875">Для обратной ссылки на этот атрибут прямой ссылки будет задано значение <strong>msRTCSIP-вебкомпонентссерверс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-876">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-877">msRTCSIP-Вебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="59c7a-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="59c7a-878">Этот атрибут представляет собой список различающихся имен, одновременно допускающего несколько значений.</span><span class="sxs-lookup"><span data-stu-id="59c7a-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="59c7a-879">Этот атрибут включает список всех веб-серверов, связанных с этим пулом.</span><span class="sxs-lookup"><span data-stu-id="59c7a-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="59c7a-880">Обратная ссылка: <strong>идентификатор ссылки 11029</strong></span><span class="sxs-lookup"><span data-stu-id="59c7a-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="59c7a-881">Соответствующая ссылка "вперед" на эту ссылку <strong>msRTCSIP-вебкомпонентспуладдресс</strong>.</span><span class="sxs-lookup"><span data-stu-id="59c7a-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-882">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="59c7a-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-883">msRTCSIP-Вмиинстанцеид (устарело)</span><span class="sxs-lookup"><span data-stu-id="59c7a-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="59c7a-884">Новые возможности Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="59c7a-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="59c7a-885">Устаревшие возможности для сервера Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="59c7a-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-886">Осерипфоне</span><span class="sxs-lookup"><span data-stu-id="59c7a-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="59c7a-887">Этот существующий атрибут Active Directory используется телефонией для указания списка альтернативных TCP/IP-адресов для телефона.</span><span class="sxs-lookup"><span data-stu-id="59c7a-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-888">Новые возможности операционной системы Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="59c7a-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-889">Фонеоффицеосер</span><span class="sxs-lookup"><span data-stu-id="59c7a-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="59c7a-890">Этот существующий атрибут Active Directory используется в Lync Server для доступа к объектам контакта только в целях маршрутизации обращений к функциям автоматического ассистента единой системы обмена сообщениями и номерам абонентов.</span><span class="sxs-lookup"><span data-stu-id="59c7a-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="59c7a-891">Адрес для переадресации неусловного звонка сохраняется в атрибуте с несколькими значениями.</span><span class="sxs-lookup"><span data-stu-id="59c7a-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="59c7a-892">Эта учетная запись создается для определенной цели автоматического ассистента и абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="59c7a-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="59c7a-893">Атрибуты этой учетной записи не должны изменяться администраторами.</span><span class="sxs-lookup"><span data-stu-id="59c7a-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-894">Новые возможности в операционной системе Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="59c7a-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c7a-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="59c7a-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="59c7a-896">Этот существующий многозначный атрибут Active Directory является частью базовой схемы Active Directory, представленной в Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="59c7a-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="59c7a-897">Этот атрибут включает различные адреса X400, X500 и SMTP для электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="59c7a-898">В реальном Communications Server 2003 и более поздних версиях URI пользователя SIP добавляется в этот список с помощью тега &quot;SIP:&quot; .</span><span class="sxs-lookup"><span data-stu-id="59c7a-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="59c7a-899">Следующие приложения выполняйте поиск URI пользователя SIP из этого атрибута:</span><span class="sxs-lookup"><span data-stu-id="59c7a-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="59c7a-900">Клиент обмена сообщениями и совместной работы в Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="59c7a-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="59c7a-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="59c7a-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="59c7a-902">Новые возможности в операционной системе Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="59c7a-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c7a-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="59c7a-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="59c7a-904">Этот существующий атрибут Active Directory включает номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="59c7a-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="59c7a-905">Новые возможности в операционной системе Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="59c7a-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


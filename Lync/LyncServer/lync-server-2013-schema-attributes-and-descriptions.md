---
title: 'Lync Server 2013: атрибуты и описания схемы'
description: 'Lync Server 2013: атрибуты и описания схемы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557195"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="bed14-103">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed14-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed14-104">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bed14-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bed14-105">В этом разделе описываются все атрибуты схемы, используемые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bed14-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="bed14-106">Классы, связанные с атрибутами, приведены [в статье атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="bed14-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="bed14-107">Список классов и атрибутов, которые являются новыми в Lync Server 2013, представлен в статье [изменения схемы в Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="bed14-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="bed14-p102">Связанные атрибуты указываются в виде прямых или обратных ссылок. Атрибут, который ссылается на другой объект, является прямой ссылкой, а атрибут другого объекта, который ссылается на первичный объект, является обратной ссылкой. Прямые ссылки поддерживают обновление, а обратные ссылки — только чтение.</span><span class="sxs-lookup"><span data-stu-id="bed14-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="bed14-p103">Значения некоторых атрибутов задаются с помощью битовой маски. В этом случае каждый параметр представляется в виде бита, а десятичное значение соответствует позиции бита. Отсчет позиции бита начинается с 0 разряда. Например, для 1 в двоичной системе счисления установлен 0 бит, а для 10000 в двоичной системе счисления задан 4 бит. Каждый бит представляет свойство. Примеры:</span><span class="sxs-lookup"><span data-stu-id="bed14-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="bed14-117">10000 (двоичное) соответствует десятичному значению 16 (т. е. задан 4 бит).</span><span class="sxs-lookup"><span data-stu-id="bed14-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="bed14-118">100000000 (двоичное) соответствует десятичному значению 256 (т. е. задан 8 бит).</span><span class="sxs-lookup"><span data-stu-id="bed14-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="bed14-119">1100 (двоичное) соответствует десятичному значению 12 (т. е. заданы 2 и 3 биты; включены свойства, соответствующие обоим битам).</span><span class="sxs-lookup"><span data-stu-id="bed14-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="bed14-120">1111000001 (двоичное) соответствует десятичному значению 961 (т. е. заданы биты 0, 6, 7, 8 и 9; включены свойства, соответствующие каждому из этих битов).</span><span class="sxs-lookup"><span data-stu-id="bed14-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="bed14-121">Атрибуты схемы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed14-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed14-122">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bed14-122">Attribute</span></span></th>
<th><span data-ttu-id="bed14-123">Описание</span><span class="sxs-lookup"><span data-stu-id="bed14-123">Description</span></span></th>
<th><span data-ttu-id="bed14-124">Comments</span><span class="sxs-lookup"><span data-stu-id="bed14-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed14-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="bed14-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="bed14-126">Существующий атрибут в доменных службах Active Directory, который теперь связан с классами <strong>msRTCSIP-Pool</strong> и <strong>msRTCSIP-мониторингсервер</strong> .</span><span class="sxs-lookup"><span data-stu-id="bed14-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="bed14-127">Этот атрибут указывает полное доменное имя (FQDN) пула или сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="bed14-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="bed14-128">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-129">Новые средства Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-130">msDS — Саурцеобжектдн</span><span class="sxs-lookup"><span data-stu-id="bed14-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-p105">Этот атрибут содержит строковое представление различающегося имени объекта в другом лесу, который соответствует этому объекту. Этот атрибут используется для расширения групп рассылки и функции автосекретаря. Этот атрибут определен в схеме Active Directory по умолчанию для Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="bed14-134">Чтобы избежать необходимости обновления доменных служб Active Directory до Windows Server 2003 R2, схема Active Directory дополняет схему Windows Server 2003 этим определением атрибута.</span><span class="sxs-lookup"><span data-stu-id="bed14-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="bed14-135">Новые данные в Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="bed14-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="bed14-137">Этот атрибут, поддерживающий несколько значений, задает параметры голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="bed14-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="bed14-138">Общий доступ к этому атрибуту осуществляется с помощью единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="bed14-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="bed14-139">Новые в Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="bed14-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="bed14-141">Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="bed14-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="bed14-142">Политики хранения определяют срок хранения элементов почтового ящика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="bed14-143">Этот атрибут используется совместно с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="bed14-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="bed14-144">Новые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bed14-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-145">msRTCSIP — Акпинфо</span><span class="sxs-lookup"><span data-stu-id="bed14-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="bed14-146">Этот атрибут используется для хранения сведений о поставщике услуг аудиоконференций для пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="bed14-147">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-148">msRTCSIP — Аппликатиондестинатион</span><span class="sxs-lookup"><span data-stu-id="bed14-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="bed14-149">Этот атрибут указывает запись доверенной службы для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="bed14-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="bed14-150">Новые данные в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-151">msRTCSIP — Аппликатионлист</span><span class="sxs-lookup"><span data-stu-id="bed14-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="bed14-152">Этот атрибут содержит список размещенных приложений на сервере приложений.</span><span class="sxs-lookup"><span data-stu-id="bed14-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="bed14-153">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-154">msRTCSIP — Аппликатионоптионс</span><span class="sxs-lookup"><span data-stu-id="bed14-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="bed14-155">Этот атрибут задает параметры контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="bed14-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="bed14-156">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-157">msRTCSIP — Аппликатионпримарилангуаже</span><span class="sxs-lookup"><span data-stu-id="bed14-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="bed14-158">Этот атрибут содержит основной язык для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="bed14-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="bed14-159">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-160">msRTCSIP — Аппликатионсекондарилангуажес</span><span class="sxs-lookup"><span data-stu-id="bed14-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="bed14-161">Этот атрибут, поддерживающий несколько значений, содержит дополнительные языки для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="bed14-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="bed14-162">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-163">msRTCSIP — Аппликатионсервербл</span><span class="sxs-lookup"><span data-stu-id="bed14-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="bed14-p108">Этот атрибут содержит список серверов приложений, которые принадлежат этому пулу. Прямая ссылка: <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-166">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-167">msRTCSIP — Аппликатионсерверпуллинк</span><span class="sxs-lookup"><span data-stu-id="bed14-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="bed14-168">Этот атрибут указывает пул, которому принадлежит этот сервер приложений.</span><span class="sxs-lookup"><span data-stu-id="bed14-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="bed14-169">Это прямая ссылка.</span><span class="sxs-lookup"><span data-stu-id="bed14-169">This is the forward link.</span></span> <span data-ttu-id="bed14-170">Обратная ссылка: <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-171">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-172">msRTCSIP-ArchiveDefault (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-173">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-174">Устаревшие данные в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-175">msRTCSIP-ArchiveDefaultFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p110">Этот атрибут задает глобальное значение по умолчанию в пределах границы леса для функции архивации всех коммуникаций пользователей. Этот атрибут задается принудительно агентом архивации. Этот атрибут может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-179"><strong>TRUE</strong>: архивировать коммуникации всех пользователей</span><span class="sxs-lookup"><span data-stu-id="bed14-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="bed14-180"><strong>FALSE</strong>: не архивировать коммуникации всех пользователей</span><span class="sxs-lookup"><span data-stu-id="bed14-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="bed14-181">Этот атрибут управляет архивацией коммуникаций пользователей во внутренней сети на глобальном уровне (в пределах границы леса).</span><span class="sxs-lookup"><span data-stu-id="bed14-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="bed14-182"><strong>Для Live Communications Server 2005 (в настоящее время не поддерживается)</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="bed14-183">Этот атрибут может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-184">0: архивировать текст сообщения [бит 0]</span><span class="sxs-lookup"><span data-stu-id="bed14-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="bed14-185">1: не архивировать текст сообщения [бит 0]</span><span class="sxs-lookup"><span data-stu-id="bed14-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="bed14-186"><strong>Для Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="bed14-187">Этот атрибут может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-188">0: ArchiveFederationDefaultWithoutBody (не поддерживается)</span><span class="sxs-lookup"><span data-stu-id="bed14-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="bed14-189">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="bed14-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="bed14-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="bed14-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="bed14-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="bed14-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="bed14-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="bed14-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="bed14-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="bed14-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="bed14-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="bed14-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="bed14-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="bed14-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="bed14-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="bed14-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="bed14-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="bed14-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="bed14-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="bed14-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="bed14-199">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="bed14-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="bed14-200">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="bed14-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="bed14-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="bed14-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="bed14-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="bed14-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-203">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-204">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-205">msRTCSIP-ArchiveFederationDefault (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-206">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-207">Устаревшие данные в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-208">msRTCSIP-ArchiveFederationDefaultFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-209">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-210">Устаревшие данные в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-211">msRTCSIP — Арчивинженаблед</span><span class="sxs-lookup"><span data-stu-id="bed14-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="bed14-p111">Этот атрибут является целым значением, используемым в качестве битового поля, которое указывает, архивируются ли коммуникации отдельного пользователя. Этот атрибут задается принудительно агентом архивации. Он помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="bed14-215">Область этого атрибута относится к одному пользователю или контакту.</span><span class="sxs-lookup"><span data-stu-id="bed14-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="bed14-216">Допустимые значения (и сопоставленные битовые позиции) в Lync Server приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="bed14-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-217">0: не архивировать (бит не задан)</span><span class="sxs-lookup"><span data-stu-id="bed14-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="bed14-218">1: не поддерживается (0 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="bed14-219">2: не поддерживается (1 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="bed14-220">4: архивировать внутренние коммуникации (2 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="bed14-221">8: архивировать федеративные коммуникации (3 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="bed14-222">Ранее допустимые значения в Live Communications Server 2005 следующие:</span><span class="sxs-lookup"><span data-stu-id="bed14-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-223">0: использовать значение по умолчанию, заданное атрибутами <strong>msRTCSIP-ArchiveDefault</strong> и <strong>msRTCSIP-ArchiveFederation</strong>, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="bed14-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-224">1: архивировать</span><span class="sxs-lookup"><span data-stu-id="bed14-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="bed14-225">2: не архивировать</span><span class="sxs-lookup"><span data-stu-id="bed14-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="bed14-226">3: архивировать без текста сообщения</span><span class="sxs-lookup"><span data-stu-id="bed14-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="bed14-227">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-228">msRTCSIP-ArchivingServerData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-229">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-230">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-231">msRTCSIP-ArchivingServerVersion (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p113">Этот атрибут задает версию службы архивации. Этот атрибут представляет собой целое значение, которое увеличивается на 1 с каждым официальным выпуском продукта. Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-235">Не определено: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="bed14-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="bed14-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="bed14-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="bed14-237">                 Live Communications Server 2005 с SP1</span><span class="sxs-lookup"><span data-stu-id="bed14-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="bed14-238">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="bed14-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="bed14-239">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bed14-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-240">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-241">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-242">msRTCSIP — Баккендсервер</span><span class="sxs-lookup"><span data-stu-id="bed14-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="bed14-p114">Этот атрибут задает полное доменное имя внутреннего сервера пула. Поскольку в одном пуле может быть только один внутренний сервер, этот атрибут может иметь только одно значение.</span><span class="sxs-lookup"><span data-stu-id="bed14-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="bed14-245">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-246">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-247">msRTCSIP — Конференцедиректорихомепул</span><span class="sxs-lookup"><span data-stu-id="bed14-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="bed14-248">Этот атрибут содержит идентификатор пула, содержащего каталог конференции.</span><span class="sxs-lookup"><span data-stu-id="bed14-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="bed14-249">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-250">msRTCSIP — Конференцедиректорид</span><span class="sxs-lookup"><span data-stu-id="bed14-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="bed14-251">Этот атрибут содержит идентификатор каталога конференции.</span><span class="sxs-lookup"><span data-stu-id="bed14-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="bed14-252">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-253">msRTCSIP — Конференцедиректоритаржетпул</span><span class="sxs-lookup"><span data-stu-id="bed14-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="bed14-254">Этот атрибут содержит идентификатор пула, в который перемещается каталог конференции.</span><span class="sxs-lookup"><span data-stu-id="bed14-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="bed14-255">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-256">msRTCSIP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bed14-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="bed14-257">Этот логический атрибут определяет, относится ли использование телефона к использованию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bed14-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="bed14-258">Если атрибут имеет значение <strong>TRUE</strong>, использование телефона относится к использованию по умолчанию и оно не может быть удалено администратором.</span><span class="sxs-lookup"><span data-stu-id="bed14-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="bed14-259">Если атрибут имеет значение <strong>FALSE</strong>, использование телефона может быть удалено.</span><span class="sxs-lookup"><span data-stu-id="bed14-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="bed14-260">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-261">msRTCSIP — Дефаулткваекстерналурл</span><span class="sxs-lookup"><span data-stu-id="bed14-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="bed14-262">Этот атрибут определяет URL-адрес Communicator Web Access для пользователей, находящихся за пререшениями Организации.</span><span class="sxs-lookup"><span data-stu-id="bed14-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="bed14-263">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-264">msRTCSIP — Дефаулткваинтерналурл</span><span class="sxs-lookup"><span data-stu-id="bed14-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="bed14-265">Этот атрибут определяет URL-адрес веб-клиента Communicator для пользователей, находящихся внутри Организации.</span><span class="sxs-lookup"><span data-stu-id="bed14-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="bed14-266">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-267">msRTCSIP-DefaultLocationProfileLink (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-268">Этот атрибут, который может иметь только одно значение, содержит различающееся имя объекта класса профиля местоположения, назначенное ему.</span><span class="sxs-lookup"><span data-stu-id="bed14-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="bed14-269">Прямая ссылка: <strong>ИД ссылки 11036</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="bed14-270">Обратная ссылка: <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-271">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-272">msRTCSIP-DefaultPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-273">Этот логический атрибут указывает, является ли политика политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bed14-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="bed14-274">Для политики по умолчанию атрибут имеет значение <strong>TRUE</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-275">Новые средства Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="bed14-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="bed14-276">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-277">msRTCSIP-DefaultRouteToEdgeProxy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-278">Этот атрибут указывает полное доменное имя пограничного сервера, на котором запущена служба пограничного доступа, если к нему возможен прямой доступ, или от аппаратного балансировщика нагрузки для пула серверов, на которых работает пограничная служба доступа.</span><span class="sxs-lookup"><span data-stu-id="bed14-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="bed14-279">Если доступ к серверам с пограничной службой доступа возможен только через одного или нескольких директоров, этот атрибут задает полное доменное имя и (необязательно) номер порта для директора или аппаратного балансировщика нагрузки, обслуживающего пул директоров.</span><span class="sxs-lookup"><span data-stu-id="bed14-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="bed14-280">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-281">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-282">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-283">msRTCSIP-DefaultRouteToEdgeProxyPort (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-284">Этот атрибут представляет номер порта, который следует использовать для подключения к серверу с пограничной службой доступа.</span><span class="sxs-lookup"><span data-stu-id="bed14-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="bed14-285">Допустимым является целое значение, указывающее номер используемого порта.</span><span class="sxs-lookup"><span data-stu-id="bed14-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="bed14-286">По умолчанию используется значение 5061.</span><span class="sxs-lookup"><span data-stu-id="bed14-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="bed14-287">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-288">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-289">msRTCSIP-DefPresenceSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-290">Этот атрибут указывает период времени ожидания по умолчанию для подписки на сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="bed14-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="bed14-291">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-292">msRTCSIP-DefRegistrationTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-293">Этот атрибут указывает период времени ожидания по умолчанию для регистрации.</span><span class="sxs-lookup"><span data-stu-id="bed14-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-294">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-296">Этот атрибут указывает период времени ожидания по умолчанию для перемещения данных подписки.</span><span class="sxs-lookup"><span data-stu-id="bed14-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-297">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-298">msRTCSIP — Деплойментлокатор</span><span class="sxs-lookup"><span data-stu-id="bed14-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="bed14-299">Этот атрибут используется в технологии расщепления домена и содержит полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="bed14-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="bed14-300">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-301">msRTCSIP-Description (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-302">Этот строковый атрибут (Юникод), который может иметь только одно значение, содержит понятное описание маршрута телефона или правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="bed14-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="bed14-303">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-304">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-305">msRTCSIP — Домаиндата</span><span class="sxs-lookup"><span data-stu-id="bed14-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="bed14-306">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-307">msRTCSIP — имя_домена</span><span class="sxs-lookup"><span data-stu-id="bed14-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="bed14-308">Этот атрибут указывает домен, заданный для регистратора.</span><span class="sxs-lookup"><span data-stu-id="bed14-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-309">msRTCSIP — Еджепроксидата</span><span class="sxs-lookup"><span data-stu-id="bed14-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="bed14-310">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-311">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-312">msRTCSIP — Еджепроксифкдн</span><span class="sxs-lookup"><span data-stu-id="bed14-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-313">Этот атрибут задает полное доменное имя сервера, на котором запущена пограничная служба доступа.</span><span class="sxs-lookup"><span data-stu-id="bed14-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="bed14-314">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-315">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-316">msRTCSIP-EnableBestEffortNotify (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p119">Этот атрибут указывает, создает ли сервер запрос Best Effort NOTIFY (BENOTIFY) вместо запроса NOTIFY в ответ на запрос SUBSCRIBE, полученный от клиента. BENOTIFY — это расширение для подтверждения уведомления о подписке, которое позволяет повысить производительность за счет создания запросов BENOTIFY вместо обычных запросов NOTIFY. Преимущество производительности заключается в том, что запрос BENOTIFY не требует ответа 200 OK от клиента в отличие от запроса NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="bed14-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="bed14-320">Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bed14-321">Live Communications Server 2003 не поддерживает запросы уведомления.</span><span class="sxs-lookup"><span data-stu-id="bed14-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="bed14-322">Для взаимодействия с серверными приложениями, написанными с помощью серверного API Live Communications Server 2003, работающего на серверах Live Communications Server 2005 и сторонних серверах, запросы уведомления можно отключить, задав для параметра значение <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bed14-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="bed14-323">В настоящее время запрос BENOTIFY не является частью стандартизации протокола SIP IETF.</span><span class="sxs-lookup"><span data-stu-id="bed14-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="bed14-324">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-325">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-326">msRTCSIP-EnableFederation (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p121">Этот атрибут является глобальным переключателем, с помощью которого администраторы могут указывать, могут ли пользователи их организации обмениваться данными с пользователями из других организаций. С помощью этого атрибута администратор может переопределить атрибут <strong>FederationEnabled</strong> отдельного пользователя. Этот атрибут позволяет защитить внутреннюю сеть от атак из Интернета, использующих вирусы-черви и другие типы вирусов, или целевых атак.</span><span class="sxs-lookup"><span data-stu-id="bed14-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="bed14-330">Допустимые значения и биты:</span><span class="sxs-lookup"><span data-stu-id="bed14-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-331">1: включен для общедоступных служб обмена мгновенными сообщениями (0 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="bed14-332">2: зарезервировано (1 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="bed14-333">4: зарезервировано (2 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="bed14-334">8: зарезервировано (3 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="bed14-335">16: удаленное управление звонками включено [телефония] (4 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="bed14-336">64: AllowOrganizeMeetingWithAnonymousParticipants (разрешает пользователям приглашать анонимных пользователей на собрания (6 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="bed14-337">128: UCEnabled (включает объединенные коммуникации для пользователей) (7 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="bed14-338">256: EnabledForEnhancedPresence (предоставляет пользователям возможность подключения к общедоступным службам обмена мгновенными сообщениями) (8 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="bed14-339">512: RemoteCallControlDualMode (9 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-340">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-341">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-342">msRTCSIP — EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="bed14-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="bed14-343">Этот атрибут указывает, загружены ли службы Enterprise Services на заданном сервере.</span><span class="sxs-lookup"><span data-stu-id="bed14-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-344">msRTCSIP — Екстенсиондата</span><span class="sxs-lookup"><span data-stu-id="bed14-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="bed14-345">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-346">msRTCSIP — Екстерналакцесскоде</span><span class="sxs-lookup"><span data-stu-id="bed14-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="bed14-347">Этот атрибут содержит код быстрого набора для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="bed14-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="bed14-348">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-349">msRTCSIP — Федератионенаблед</span><span class="sxs-lookup"><span data-stu-id="bed14-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="bed14-p122">Этот атрибут указывает, включена ли федерация для отдельного пользователя. Этот атрибут задается службами Enterprise Services. Он отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="bed14-353">Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-354">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-355">msRTCSIP — Фронтендсерверс</span><span class="sxs-lookup"><span data-stu-id="bed14-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="bed14-356">Этот атрибут представляет список имен доменов всех серверов Enterprise Edition, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="bed14-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="bed14-357">Обратная ссылка: <strong>ИД ссылки 11023</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="bed14-358">Прямая ссылка: <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-359">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-360">msRTCSIP-Gateways (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-361">Этот строковый атрибут, поддерживающий несколько значений, содержит список шлюзов и портов (для каждого шлюза).</span><span class="sxs-lookup"><span data-stu-id="bed14-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="bed14-362">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-363">msRTCSIP-GlobalSettingsData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p123">Этот атрибут содержит пары "имя:значение". Для параметра <strong>разрешить опрос сведений о присутствии</strong> пара имя:значение уже определена.</span><span class="sxs-lookup"><span data-stu-id="bed14-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="bed14-366">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-367">msRTCSIP — Граупингид</span><span class="sxs-lookup"><span data-stu-id="bed14-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="bed14-368">Этот атрибут является уникальным идентификатором группы, используемой для группировки записей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="bed14-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="bed14-369">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-370">msRTCSIP-HomeServer (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-371">Новый сервер Live Communications Server 2003 (не используется).</span><span class="sxs-lookup"><span data-stu-id="bed14-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="bed14-372">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-373">msRTCSIP-HomeServerString (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-374">Новые средства Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="bed14-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="bed14-375">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-376">msRTCSIP-HomeUsers (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-377">Новый сервер Live Communications Server 2003 (не используется).</span><span class="sxs-lookup"><span data-stu-id="bed14-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="bed14-378">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-379">msRTCSIP — Интернетакцессенаблед</span><span class="sxs-lookup"><span data-stu-id="bed14-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="bed14-p124">Этот атрибут указывает, разрешен ли отдельному пользователю внешний доступ. Этот атрибут задается службами Enterprise Services. Он отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="bed14-383">Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-384">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-385">msRTCSIP-IsMaster (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-386">Новые средства Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="bed14-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="bed14-387">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-388">msRTCSIP — Line</span><span class="sxs-lookup"><span data-stu-id="bed14-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="bed14-389">Этот атрибут с одним значением содержит идентификатор устройства (URI SIP или TEL URI телефона, который пользовательские элементы управления) использует Lync для телефонии.</span><span class="sxs-lookup"><span data-stu-id="bed14-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="bed14-390">Этот атрибут помечен для репликации глобального каталога и индексируется.</span><span class="sxs-lookup"><span data-stu-id="bed14-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="bed14-391">Если для пользователя включена поддержка корпоративной голосовой связи, то этот атрибут используется для хранения номера телефона пользователя в формате E.164.</span><span class="sxs-lookup"><span data-stu-id="bed14-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="bed14-392">Новые средства Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bed14-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-393">msRTCSIP — Линесервер</span><span class="sxs-lookup"><span data-stu-id="bed14-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="bed14-p126">Этот атрибут, поддерживающий одно значение, содержит URI SIP сервера шлюза CSTA-SIP. Этот атрибут помечен для репликации глобального каталога, но не индексируется.</span><span class="sxs-lookup"><span data-stu-id="bed14-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="bed14-396">Новые средства Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bed14-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-397">msRTCSIP-LocalNormalizationData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-398">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-399">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-400">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-401">msRTCSIP-LocalNormalizationLinks (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p127">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен с локальной нормализацией, связанных с этим профилем местоположения. Этот атрибут имеет тип "двоичное DN". Между профилем местоположения и локальными правилами нормализации существует отношение "один ко многим". Порядок обработки списка различающихся имен с локальной нормализацией должен совпадать с порядком, заданным администратором. Сохранение порядка задается двоичной частью типа "двоичное DN", которая указывает индекс порядка.</span><span class="sxs-lookup"><span data-stu-id="bed14-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="bed14-407">Прямая ссылка: <strong>ИД ссылки 11034</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="bed14-408">Соответствующая обратная ссылка: <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-409">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-410">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-411">msRTCSIP — Локалнормализатионоптионс</span><span class="sxs-lookup"><span data-stu-id="bed14-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="bed14-412">Этот атрибут содержит список параметров для правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="bed14-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="bed14-413">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-414">msRTCSIP-LocationName (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p128">Этот атрибут, поддерживающий одно значение, содержит понятное имя профиля местоположения, указывающее местоположение, которое представляет этот профиль. Поскольку профилей местоположения может быть несколько, администратору требуется способ, позволяющий легко различать разные профили.</span><span class="sxs-lookup"><span data-stu-id="bed14-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="bed14-417">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-418">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-419">msRTCSIP-locationProfileBL (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p129">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен профилей местоположения. Этот атрибут указывает обратную ссылку на профили местоположения.</span><span class="sxs-lookup"><span data-stu-id="bed14-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="bed14-422">Обратная ссылка: <strong>ИД ссылки 11035</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="bed14-423">Этот атрибут указывает прямую ссылку на <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-424">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-425">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-426">msRTCSIP-LocationProfileData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-427">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-428">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-429">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-430">msRTCSIP — Локатионпрофилеоптионс</span><span class="sxs-lookup"><span data-stu-id="bed14-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="bed14-431">Этот атрибут содержит параметры профиля местоположения.</span><span class="sxs-lookup"><span data-stu-id="bed14-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="bed14-432">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-433">msRTCSIP — Маппингконтакт</span><span class="sxs-lookup"><span data-stu-id="bed14-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="bed14-434">Этот атрибут, поддерживающий несколько значений, содержит список контактов приложения.</span><span class="sxs-lookup"><span data-stu-id="bed14-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="bed14-435">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-436">msRTCSIP — Маппинглокатион</span><span class="sxs-lookup"><span data-stu-id="bed14-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="bed14-437">Этот атрибут, поддерживающий несколько значений, содержит список профилей местоположения.</span><span class="sxs-lookup"><span data-stu-id="bed14-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="bed14-438">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-439">msRTCSIP-MaxNumOutstandingSearchPerServer (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-440">Этот атрибут представляет максимальное число ожидающих запросов на поиск для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="bed14-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="bed14-441">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-442">msRTCSIP-MaxNumSubscriptionsPerUser (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-443">Этот атрибут представляет максимальное число подписок для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="bed14-444">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-445">msRTCSIP-MaxPresenceSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-446">Этот атрибут представляет максимальное время ожидания подписки.</span><span class="sxs-lookup"><span data-stu-id="bed14-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-447">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-448">msRTCSIP-MaxRegistrationsTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-449">Этот атрибут представляет максимальное время ожидания регистрации.</span><span class="sxs-lookup"><span data-stu-id="bed14-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-450">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-452">Этот атрибут представляет максимальное время ожидания перемещения данных подписки.</span><span class="sxs-lookup"><span data-stu-id="bed14-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-453">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-454">msRTCSIP — Мкудата</span><span class="sxs-lookup"><span data-stu-id="bed14-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="bed14-455">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-456">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-457">msRTCSIP — Мкуфакторяддресс</span><span class="sxs-lookup"><span data-stu-id="bed14-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="bed14-p130">Этот атрибут представляет точку управления службой в классе компьютера, которая указывает обратную ссылку на фабрику многоточечного управляющего узла, к которой она принадлежит. Эта точка управления службой и атрибут создаются для каждого многоточечного управляющего узла Майкрософт. Каждый многоточечный управляющий узел Майкрософт должен найти внутренний сервер пула, к которому он принадлежит, чтобы получить у него параметры уровня пула.</span><span class="sxs-lookup"><span data-stu-id="bed14-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="bed14-p131">Значением этого атрибута является различающееся имя фабрики многоточечного управляющего узла. Этот атрибут поддерживает одно значение и помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="bed14-463">Прямая ссылка: <strong>ИД ссылки 11026</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="bed14-464">Соответствующая обратная ссылка: <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-465">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-466">msRTCSIP — Мкуфакторидата</span><span class="sxs-lookup"><span data-stu-id="bed14-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="bed14-p132">Это зарезервированный атрибут, который может принимать несколько строковых значений. Параметры, сохраняемые в этом атрибуте, представляют пары имя=значение. В настоящее время определены следующие пары имя=значение:</span><span class="sxs-lookup"><span data-stu-id="bed14-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-470">Факторюрл = &lt; URL-адрес&gt;</span><span class="sxs-lookup"><span data-stu-id="bed14-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-471">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-472">msRTCSIP — Мкуфакторипас</span><span class="sxs-lookup"><span data-stu-id="bed14-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="bed14-473">Этот атрибут, поддерживающий одно значение, содержит различающееся имя одной фабрики многоточечного управляющего узла, связанной с пулом.</span><span class="sxs-lookup"><span data-stu-id="bed14-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="bed14-474">Прямая ссылка: <strong>ИД ссылки 11024</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="bed14-475">Соответствующая обратная ссылка: <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-476">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-477">msRTCSIP — Мкуфакторипровидерид</span><span class="sxs-lookup"><span data-stu-id="bed14-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="bed14-478">Этот атрибут, поддерживающий одно строковое значение, указывает глобальный уникальный ИД поставщика фабрики многоточечного управляющего узла.</span><span class="sxs-lookup"><span data-stu-id="bed14-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="bed14-479">На основании значения глобального уникального ИД фабрика многоточечного управляющего узла определяет, требуется ли обслуживать определенный тип многоточечного управляющего узла.</span><span class="sxs-lookup"><span data-stu-id="bed14-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="bed14-480">Если GUID имеет значение <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, процесс фабрики MCU (доступен по умолчанию в Lync Server) будет обрабатывать его.</span><span class="sxs-lookup"><span data-stu-id="bed14-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="bed14-481">В противном случае процесс фабрики не будет обслуживать многоточечный управляющий узел.</span><span class="sxs-lookup"><span data-stu-id="bed14-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="bed14-482">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-483">msRTCSIP — Мкусерверс</span><span class="sxs-lookup"><span data-stu-id="bed14-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="bed14-p134">Этот атрибут, поддерживающий несколько значений, представляет список различающихся имен. Этот атрибут содержит список всех серверов многоточечного управляющего узла одного типа, имеющих одинакового поставщика, связанного с этой фабрикой многоточечного управляющего узла. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="bed14-487">Обратная ссылка: ИД ссылки 11027</span><span class="sxs-lookup"><span data-stu-id="bed14-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="bed14-488">Соответствующая обратная ссылка: <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-489">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-490">msRTCSIP — Мкутипе</span><span class="sxs-lookup"><span data-stu-id="bed14-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="bed14-491">Этот строковый атрибут, поддерживающий одно значение, указывает тип данных, которые может обработать многоточечный управляющий узел.</span><span class="sxs-lookup"><span data-stu-id="bed14-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="bed14-492">Допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="bed14-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-493">назначить</span><span class="sxs-lookup"><span data-stu-id="bed14-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="bed14-494">аудио и видео</span><span class="sxs-lookup"><span data-stu-id="bed14-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="bed14-495">чат</span><span class="sxs-lookup"><span data-stu-id="bed14-495">chat</span></span></p></li>
<li><p><span data-ttu-id="bed14-496">Телефон — CONF</span><span class="sxs-lookup"><span data-stu-id="bed14-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-497">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-498">msRTCSIP — Мкувендор</span><span class="sxs-lookup"><span data-stu-id="bed14-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="bed14-p135">Этот строковый атрибут, поддерживающий одно значение, указывает имя поставщика многоточечного управляющего узла. Для всех многоточечных управляющих узлов Майкрософт этот атрибут будет иметь значение <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-501">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-502">msRTCSIP-MeetingFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p136">Этот атрибут определяет различные параметры собрания, которые включены глобально для всех пользователей или контактных объектов. Этот атрибут представляет собой битовую маску целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="bed14-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="bed14-505">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="bed14-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (запретить пользователям приглашать на собрания анонимных пользователей) (биты не заданы)</span><span class="sxs-lookup"><span data-stu-id="bed14-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="bed14-507">4: Alloworganizemeetingwithanonymousparticipants is — все пользователи (разрешают всем пользователям приглашать анонимных пользователей для собраний) (Битовая позиция 2)</span><span class="sxs-lookup"><span data-stu-id="bed14-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="bed14-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (разрешить пользователям приглашать на собрания анонимных пользователей с учетом параметров пользователя) (3 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="bed14-509">16: UserPerUserMeetingPolicy (политика собрания определяется для каждого пользователя) (4 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-510">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-511">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-512">msRTCSIP-MeetingPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-513">Этот атрибут задает различающееся имя политики, назначенной администратором для этого пользователя в качестве атрибута с одним значением.</span><span class="sxs-lookup"><span data-stu-id="bed14-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="bed14-514">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-515">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-516">msRTCSIP-MinPresenceSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-517">Этот атрибут указывает минимальное время ожидания для подписки на сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="bed14-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-518">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-519">msRTCSIP-MinRegistrationTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-520">Этот атрибут указывает минимальное время ожидания регистрации.</span><span class="sxs-lookup"><span data-stu-id="bed14-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-521">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-522">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-524">Этот атрибут задает минимальное время ожидания для перемещения данных подписки.</span><span class="sxs-lookup"><span data-stu-id="bed14-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="bed14-525">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-526">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-527">msRTCSIP — Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="bed14-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="bed14-528">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="bed14-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="bed14-529">Новые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bed14-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-530">msRTCSIP — Мобилитифлагс</span><span class="sxs-lookup"><span data-stu-id="bed14-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="bed14-531">Этот атрибут содержит параметры и флаги, определяющие параметры мобильности.</span><span class="sxs-lookup"><span data-stu-id="bed14-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="bed14-532">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-533">msRTCSIP — Мобилитиполици</span><span class="sxs-lookup"><span data-stu-id="bed14-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="bed14-534">Этот атрибут содержит различающееся имя для объекта политики мобильности.</span><span class="sxs-lookup"><span data-stu-id="bed14-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="bed14-535">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-536">msRTCSIP-NumDevicesPerUser (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-537">Этот атрибут указывает максимальное число устройств, на которых пользователь может зарегистрироваться и подписаться на сведения о присутствии для коммуникаций SIP.</span><span class="sxs-lookup"><span data-stu-id="bed14-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="bed14-538">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-539">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-540">msRTCSIP — Оптионфлагс</span><span class="sxs-lookup"><span data-stu-id="bed14-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="bed14-p137">Этот атрибут указывает параметры, включенные для пользователя или контактного объекта. Этот атрибут является битовой маской целочисленного типа. Каждому параметру соответствует определенный бит. Этот атрибут отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="bed14-545">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="bed14-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-546">1: включен для подключения к общедоступным службам обмена мгновенными сообщениями (0 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="bed14-547">2: зарезервировано (1 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="bed14-548">4: зарезервировано (2 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="bed14-549">8: зарезервировано (3 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="bed14-550">16: удаленное управление звонками включено [телефония] (4 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="bed14-551">64: AllowOrganizeMeetingWithAnonymousParticipants (разрешает пользователям приглашать на собрания анонимных пользователей (6 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="bed14-552">128: UCEnabled (включает объединенные коммуникации для пользователей) (7 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="bed14-553">256: EnabledForEnhancedPresence (включает для пользователей возможность подключения к общедоступным службам обмена мгновенными сообщениями) (8 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="bed14-554">512: RemoteCallControlDualMode (9 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-555">Новые средства Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="bed14-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-556">msRTCSIP — Оригинаторсид</span><span class="sxs-lookup"><span data-stu-id="bed14-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="bed14-557">Этот атрибут используется в топологии с лесом ресурсов и центральной топологии леса для включения функции единого входа при копировании ObjectSID пользователя из учетной записи субъекта безопасности Windows NT Server в этот атрибут соответствующего пользователя или контактного объекта в лесу ресурсов или центрального леса.</span><span class="sxs-lookup"><span data-stu-id="bed14-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="bed14-558">Веб-клиент Communicator ищет пользователя в доменных СЛУЖБах Active Directory, используя этот атрибут или ObjectSID пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="bed14-559">Этот атрибут отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-560">msRTCSIP — Овнерурн</span><span class="sxs-lookup"><span data-stu-id="bed14-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="bed14-561">Этот атрибут представляет унифицированное имя ресурса (URN) владельца контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="bed14-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="bed14-562">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-563">msRTCSIP-Pattern (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p139">Этот строковый атрибут, поддерживающий одно значение, содержит шаблон, используемый для поиска соответствия набираемых номеров формату E.164. Если набираемый номер соответствует этому шаблону, к нему применяется преобразование.</span><span class="sxs-lookup"><span data-stu-id="bed14-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="bed14-566">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-567">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-568">msRTCSIP-PhoneRouteBL (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p140">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен телефонных маршрутов. Этот атрибут указывает обратные ссылки на телефонные маршруты.</span><span class="sxs-lookup"><span data-stu-id="bed14-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="bed14-571">Обратная ссылка: <strong>ИД ссылки 11033</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="bed14-572">Прямая ссылка: <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-573">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-574">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-575">msRTCSIP-PhoneRouteData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-576">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-577">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-578">msRTCSIP-PhoneRouteName (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-579">Этот строковый (Юникод) атрибут, поддерживающий одно значение, указывает понятное имя телефонного маршрута для простоты идентификации.</span><span class="sxs-lookup"><span data-stu-id="bed14-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="bed14-580">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-581">msRTCSIP-PhoneUsageData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-582">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-583">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-584">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-585">msRTCSIP-PolicyContent (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p141">Это строковый (Юникод) атрибут, поддерживающий одно значение. Этот строковый атрибут содержит определение политики в формате XML. Определение схемы XML идентично для разных типов политик. Разные типы политик отличаются только параметрами.</span><span class="sxs-lookup"><span data-stu-id="bed14-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="bed14-589">Определение схемы XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="bed14-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="bed14-590">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-591">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-592">msRTCSIP-PolicyData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-593">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-594">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-595">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-596">msRTCSIP-PolicyType (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p142">Этот строковый (Юникод) атрибут, поддерживающий одно значение, содержит тип политики. Допустимые типы политик:</span><span class="sxs-lookup"><span data-stu-id="bed14-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-599">назначить</span><span class="sxs-lookup"><span data-stu-id="bed14-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="bed14-600">телефонии</span><span class="sxs-lookup"><span data-stu-id="bed14-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-601">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-602">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-603">msRTCSIP — Пуладдресс</span><span class="sxs-lookup"><span data-stu-id="bed14-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="bed14-604">Этот атрибут указывает обратную ссылку на пул, к которому принадлежит компьютер.</span><span class="sxs-lookup"><span data-stu-id="bed14-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="bed14-605">Этот атрибут задается независимо от того, работает ли на компьютере выпуск Standard Edition или корпоративный выпуск Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed14-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="bed14-606">Этот атрибут отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="bed14-607">Допустимым значением является доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="bed14-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="bed14-608">Прямая ссылка: <strong>ИД ссылки 11022</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="bed14-609">Обратная ссылка: <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-610">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-611">msRTCSIP — Пуладдрессес</span><span class="sxs-lookup"><span data-stu-id="bed14-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="bed14-612">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен пулов, с которыми связана фабрика многоточечного управляющего узла.</span><span class="sxs-lookup"><span data-stu-id="bed14-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="bed14-613">Обратная ссылка: <strong>ИД ссылки 11025</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="bed14-614">Прямая ссылка: <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-615">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-616">msRTCSIP — Пулдата</span><span class="sxs-lookup"><span data-stu-id="bed14-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="bed14-617">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-618">Новые средства Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="bed14-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-619">msRTCSIP — Пулдисплайнаме</span><span class="sxs-lookup"><span data-stu-id="bed14-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="bed14-p144">Этот атрибут задает произвольное имя пула, отображаемое в консоли управления. Это имя может быть изменено администратором.</span><span class="sxs-lookup"><span data-stu-id="bed14-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="bed14-622">Допустимым значением является строка, представляющая имя пула.</span><span class="sxs-lookup"><span data-stu-id="bed14-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="bed14-623">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-624">msRTCSIP — Пулдомаинфкдн</span><span class="sxs-lookup"><span data-stu-id="bed14-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-p145">Это строковый атрибут, который поддерживает одно значение. Этот атрибут содержит полное доменное имя пула в том случае, если администратор хочет создать интерфейсный пул с полным доменным именем, которое не соответствует структуре домена Active Directory, в которой создан интерфейсный пул (например, пространство имен SIP отсоединено от пространства имен DNS).</span><span class="sxs-lookup"><span data-stu-id="bed14-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="bed14-p146">Майкрософт рекомендует сопоставить полное доменное имя интерфейсного пула части доменного имени в качестве домена Active Directory, в котором расположен пул. Следовательно, если для этого атрибута не задано значение, то полное доменное имя интерфейсного пула будет по умолчанию равно структуре доменного имени Active Directory, как задано атрибутом <strong>dnsHostName</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="bed14-629">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-630">msRTCSIP — Пулфунктионалити</span><span class="sxs-lookup"><span data-stu-id="bed14-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="bed14-631">Многозначный список доменных имен всех серверов Lync Server, корпоративных выпусков, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="bed14-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="bed14-632">Этот целочисленный атрибут указывает, поддерживает ли пул обмен мгновенными сообщениями, сведения о присутствии и собрания.</span><span class="sxs-lookup"><span data-stu-id="bed14-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="bed14-633">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-634">Undefined: служба обмена мгновенными сообщениями и сведениями о присутствии (Live Communications Server 2005 и 2003)</span><span class="sxs-lookup"><span data-stu-id="bed14-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="bed14-635">1: служба мгновенных сообщений и сведений о присутствии (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="bed14-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="bed14-636">2: обмен мгновенными сообщениями и сведения о присутствии и службе собраний (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="bed14-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-637">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-638">msRTCSIP — Пултипе</span><span class="sxs-lookup"><span data-stu-id="bed14-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="bed14-p148">Этот атрибут указывает выпуск, установленный в пуле серверов (Standard Edition или Enterprise Edition). Этот атрибут является битовой маской целочисленного типа. Каждому параметру соответствует определенный бит.</span><span class="sxs-lookup"><span data-stu-id="bed14-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="bed14-642">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="bed14-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-643">1: сервер Standard Edition, содержит пользователей (0 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="bed14-644">2: сервер Enterprise Edition, содержит пользователей (1 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="bed14-645">4: сервер Standard Edition, содержит приложения (2 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="bed14-646">8: сервер Enterprise Edition, содержит приложения (3 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="bed14-647">Так как Lync Server не поддерживает пулы, в которых размещаются только приложения, допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-648">5: сервер Standard Edition, содержит пользователей и приложения (0 и 2 биты)</span><span class="sxs-lookup"><span data-stu-id="bed14-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="bed14-649">10: сервер Enterprise Edition, содержит пользователей и приложения (1 и 3 биты)</span><span class="sxs-lookup"><span data-stu-id="bed14-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-650">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-651">msRTCSIP — Пулверсион</span><span class="sxs-lookup"><span data-stu-id="bed14-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="bed14-p149">Этот атрибут указывает версию пула. Атрибут содержит целое значение, которое увеличивается на 1 с каждым новым выпуском продукта.</span><span class="sxs-lookup"><span data-stu-id="bed14-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="bed14-654">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-655">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="bed14-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="bed14-656">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="bed14-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="bed14-657">2: Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="bed14-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="bed14-658">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="bed14-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="bed14-659">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bed14-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="bed14-660">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bed14-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-661">Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="bed14-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-662">msRTCSIP — Пресенцефлагс</span><span class="sxs-lookup"><span data-stu-id="bed14-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="bed14-663">Этот атрибут содержит параметры и флаги, описывающие параметры присутствия.</span><span class="sxs-lookup"><span data-stu-id="bed14-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="bed14-664">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-665">msRTCSIP — PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="bed14-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="bed14-666">Этот атрибут содержит различающееся имя для объекта политики присутствия.</span><span class="sxs-lookup"><span data-stu-id="bed14-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="bed14-667">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-668">msRTCSIP — Примарихомесервер</span><span class="sxs-lookup"><span data-stu-id="bed14-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="bed14-p150">Этот атрибут включает обмен сообщениями SIP для пользователя или контакта. Он добавлен в класс контакта, поскольку в топологии центрального леса, контактных объектах и объектах пользователей протокол SIP не включен.</span><span class="sxs-lookup"><span data-stu-id="bed14-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="bed14-671">Допустимым значением является различающееся имя сервера Standard Edition или интерфейсного пула Enterprise Edition, в котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="bed14-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="bed14-672">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-673">msRTCSIP — PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="bed14-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="bed14-674">Этот атрибут содержит SIP-адрес указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-675">msRTCSIP — PrivateLine</span><span class="sxs-lookup"><span data-stu-id="bed14-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="bed14-676">Этот атрибут содержит идентификатор устройства для телефонии.</span><span class="sxs-lookup"><span data-stu-id="bed14-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="bed14-677">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-678">msRTCSIP — поддерживает маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="bed14-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="bed14-679">Этот атрибут является логическим атрибутом, используемым для определения того, авторизован ли Lync Server для маршрутизации в эту службу с помощью своего адреса GRUU.</span><span class="sxs-lookup"><span data-stu-id="bed14-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="bed14-680">Если этому параметру присвоено значение <strong>true</strong>, то Lync Server авторизован для маршрутизации к этой службе.</span><span class="sxs-lookup"><span data-stu-id="bed14-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="bed14-681">Если этому параметру присвоено значение <strong>false</strong>, то Lync Server не авторизован для маршрутизации к этой службе.</span><span class="sxs-lookup"><span data-stu-id="bed14-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="bed14-682">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-683">msRTCSIP-RouteUsageAttribute (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p152">Этот строковый (Юникод) атрибут, поддерживающий одно значение, определяет атрибут, который задает использование телефонного маршрута. Телефонный маршрут выбирается с учетом двух элементов: атрибут использования, назначенный телефонному маршруту, и разрешенные атрибуты политики использования звонящего. Выбирается первый телефонный маршрут с атрибутами использования, которые совпадают с разрешенными атрибутами звонящего.</span><span class="sxs-lookup"><span data-stu-id="bed14-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="bed14-687">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-688">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-689">msRTCSIP-RouteUsageLinks (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-690">Это атрибут, поддерживающий несколько значений, содержит список различающихся имен использования маршрута.</span><span class="sxs-lookup"><span data-stu-id="bed14-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="bed14-691">Прямая ссылка: <strong>ИД ссылки 11032</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="bed14-692">Обратная ссылка: <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-693">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-694">msRTCSIP — Раутингпулдн</span><span class="sxs-lookup"><span data-stu-id="bed14-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-695">Этот атрибут содержит различающееся имя, которое указывает на пул, через который должен проходить весь трафик SIP для этого многоточечного управляющего узла или доверенной службы.</span><span class="sxs-lookup"><span data-stu-id="bed14-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="bed14-696">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-697">msRTCSIP-RuleName (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-698">Этот строковый (Юникод) атрибут, поддерживающий одно значение, указывает понятное имя правила нормализации для простоты идентификации.</span><span class="sxs-lookup"><span data-stu-id="bed14-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="bed14-699">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-700">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-701">msRTCSIP — SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="bed14-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="bed14-702">Этот атрибут представляет версию схемы, развернутой в организации.</span><span class="sxs-lookup"><span data-stu-id="bed14-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-703">msRTCSIP-SearchMaxRequests (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-704">Этот атрибут позволяет ограничить число результатов поиска, возвращаемых при поиске контакта в каталоге, когда пользователь выполняет поиск контакта с помощью Communicator.</span><span class="sxs-lookup"><span data-stu-id="bed14-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="bed14-705">Этот атрибут будет переопределять значение, указанное клиентом.</span><span class="sxs-lookup"><span data-stu-id="bed14-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="bed14-706">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-707">msRTCSIP-SearchMaxResults (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-708">Этот атрибут ограничивает число возвращаемых запросов поиска.</span><span class="sxs-lookup"><span data-stu-id="bed14-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="bed14-709">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-710">msRTCSIP — Сервербл</span><span class="sxs-lookup"><span data-stu-id="bed14-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="bed14-p154">Этот атрибут, поддерживающий несколько значений, представляет собой обратную ссылку, которая содержит список различающихся имен. Эти различающиеся имена указывают на пул или объект <strong>TrustedService</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="bed14-713">Прямая ссылка: <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-714">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-715">msRTCSIP — Сервердата</span><span class="sxs-lookup"><span data-stu-id="bed14-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="bed14-716">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-717">msRTCSIP-ServerReferenceBL (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p155">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен. Различающиеся имена представляют собой обратные ссылки на другие серверные объекты, которые могут быть назначены профилю местоположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bed14-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="bed14-720">Обратная ссылка: <strong>ИД ссылки 11037</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="bed14-721">Прямая ссылка: <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="bed14-722">Этот атрибут обратной ссылки указывает только пулы и серверы-посредники.</span><span class="sxs-lookup"><span data-stu-id="bed14-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="bed14-723">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-724">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-725">msRTCSIP — Серверверсион</span><span class="sxs-lookup"><span data-stu-id="bed14-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="bed14-p156">Этот атрибут указывает версию сервера. Номер версии применяется ко всем ролям сервера. Этот атрибут представляет собой целое значение, которое увеличивается на 1 с каждым официальным выпуском продукта.</span><span class="sxs-lookup"><span data-stu-id="bed14-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="bed14-729">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-730">Не определено: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="bed14-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="bed14-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="bed14-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="bed14-732">                 Live Communications Server 2005 с SP1</span><span class="sxs-lookup"><span data-stu-id="bed14-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="bed14-733">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="bed14-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="bed14-734">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bed14-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="bed14-735">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bed14-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="bed14-736">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed14-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-737">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-738">msRTCSIP — Саурцеобжекттипе</span><span class="sxs-lookup"><span data-stu-id="bed14-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="bed14-739">Этот целочисленный атрибут, поддерживающий только одно значение, задает тип объекта, на который указывает <strong>msDS-SourceObjectDN</strong>:</span><span class="sxs-lookup"><span data-stu-id="bed14-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-740">null | 0x00000001: объект субъекта пользователя Windows NT Server из другого леса</span><span class="sxs-lookup"><span data-stu-id="bed14-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="bed14-741">Следующие атрибуты представляют типы из другого леса для расширения группы рассылки:</span><span class="sxs-lookup"><span data-stu-id="bed14-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="bed14-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="bed14-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="bed14-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="bed14-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="bed14-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="bed14-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="bed14-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="bed14-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="bed14-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="bed14-747">0x90000000: представляет объект доступа автосекретаря или подписчика из того же леса или из другого леса</span><span class="sxs-lookup"><span data-stu-id="bed14-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="bed14-748">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-749">msRTCSIP-SubscriptionAuthRequired (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-750">Новые средства Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="bed14-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="bed14-751">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-752">msRTCSIP — Таржесомесервер</span><span class="sxs-lookup"><span data-stu-id="bed14-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="bed14-753">Этот атрибут позволяет переместить пользователя или контактного объекта из одного пула Lync Server в другой.</span><span class="sxs-lookup"><span data-stu-id="bed14-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="bed14-754">Этот атрибут добавляется в класс контакта, поскольку протокол SIP включен в центральной топологии леса для контактных объектов, а не объектов пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="bed14-755">Допустимым значением является различающееся имя конечного сервера Standard Edition или интерфейсного пула, в который перемещается пользователь.</span><span class="sxs-lookup"><span data-stu-id="bed14-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="bed14-756">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-757">msRTCSIP-TargetPhoneNumber (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-758">Этот строковый атрибут, который может содержать только одно значение, содержит шаблон номера телефона или диапазон номеров для маршрутизации на шлюзы, указанные с помощью атрибута <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-759">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-760">msRTCSIP — ТаржетусерполиЦиес</span><span class="sxs-lookup"><span data-stu-id="bed14-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="bed14-761">Этот атрибут хранит пары "имя — значение" для целевых политик для пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed14-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="bed14-762">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-763">msRTCSIP — TenantId</span><span class="sxs-lookup"><span data-stu-id="bed14-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="bed14-764">Этот атрибут содержит уникальный идентификатор для клиента.</span><span class="sxs-lookup"><span data-stu-id="bed14-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="bed14-765">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-766">msRTCSIP-Translation (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-767">Этот атрибут используется функцией голосовой связи в Lync Server и содержит строку преобразования, применяемую к набранному номеру, если найдено соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="bed14-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="bed14-768">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="bed14-769">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-770">msRTCSIP — Трустедмкудата</span><span class="sxs-lookup"><span data-stu-id="bed14-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="bed14-771">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-772">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-773">msRTCSIP — Трустедмкуфкдн</span><span class="sxs-lookup"><span data-stu-id="bed14-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-p158">Этот атрибут представляет строковое значение, содержащее полное доменное имя многоточечного управляющего узла. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-777">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-778">msRTCSIP — Трустедпроксидата</span><span class="sxs-lookup"><span data-stu-id="bed14-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="bed14-779">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-780">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-781">msRTCSIP — Трустедпроксифкдн</span><span class="sxs-lookup"><span data-stu-id="bed14-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-p159">Этот атрибут представляет строковое значение, содержащее полное доменное имя прокси-сервера. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-785">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-786">msRTCSIP — Трустедсервердата</span><span class="sxs-lookup"><span data-stu-id="bed14-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="bed14-787">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-788">msRTCSIP — Трустедсерверфкдн</span><span class="sxs-lookup"><span data-stu-id="bed14-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-789">Этот атрибут может принимать только одно значение и содержит полное доменное имя доверенного сервера.</span><span class="sxs-lookup"><span data-stu-id="bed14-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="bed14-790">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-791">msRTCSIP — Трустедсерверверсион</span><span class="sxs-lookup"><span data-stu-id="bed14-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="bed14-792">Этот атрибут указывает номер версии сервера в списке доверенных серверов.</span><span class="sxs-lookup"><span data-stu-id="bed14-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="bed14-793">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-794">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="bed14-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="bed14-795">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="bed14-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="bed14-796">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="bed14-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="bed14-797">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bed14-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="bed14-798">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bed14-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="bed14-799">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed14-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-800">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-801">msRTCSIP — Трустедсервицефлагс</span><span class="sxs-lookup"><span data-stu-id="bed14-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="bed14-802">Этот атрибут определяет параметры, доступные для доверенной службы.</span><span class="sxs-lookup"><span data-stu-id="bed14-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="bed14-803">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-804">msRTCSIP — Трустедсервицелинкс</span><span class="sxs-lookup"><span data-stu-id="bed14-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="bed14-805">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен, который ссылается на доверенный объект службы, например службу проверки подлинности при ретрансляции мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bed14-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="bed14-806">Служба проверки подлинности мультимедиа-ретрансляции (которая физически размещена на пограничном сервере, на которой работает служба аудио-и видеоконференций) должна быть связана с пулом для поддержки аудио сценариев для удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="bed14-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="bed14-807">Обратная ссылка: <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-808">Объединенных</span><span class="sxs-lookup"><span data-stu-id="bed14-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-809">msRTCSIP — Трустедсервицепорт</span><span class="sxs-lookup"><span data-stu-id="bed14-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="bed14-810">Этот атрибут представляет целое значение, которое определяет номера порта, используемого для подключения к службе GRUU.</span><span class="sxs-lookup"><span data-stu-id="bed14-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="bed14-811">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-812">msRTCSIP — Трустедсервицетипе</span><span class="sxs-lookup"><span data-stu-id="bed14-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="bed14-813">Этот строковый атрибут указывает тип представляемой службы GRUU.</span><span class="sxs-lookup"><span data-stu-id="bed14-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="bed14-814">Допустимые типы службы GRUU:</span><span class="sxs-lookup"><span data-stu-id="bed14-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="bed14-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="bed14-816">Шлюз</span><span class="sxs-lookup"><span data-stu-id="bed14-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="bed14-817">Media Relay Authentication Service (MRAS)</span><span class="sxs-lookup"><span data-stu-id="bed14-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="bed14-818">косм</span><span class="sxs-lookup"><span data-stu-id="bed14-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="bed14-819">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="bed14-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-820">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-821">msRTCSIP — Трустедвебкомпонентссервердата</span><span class="sxs-lookup"><span data-stu-id="bed14-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="bed14-822">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-823">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-824">msRTCSIP — Трустедвебкомпонентссерверфкдн</span><span class="sxs-lookup"><span data-stu-id="bed14-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="bed14-825">Этот атрибут представляет собой строковое значение, содержащее полное доменное имя служб IIS, на котором запущены веб-службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed14-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="bed14-826">Этот атрибут поддерживает только одно значение.</span><span class="sxs-lookup"><span data-stu-id="bed14-826">This is a single-valued attribute.</span></span> <span data-ttu-id="bed14-827">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="bed14-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="bed14-828">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-829">msRTCSIP-UCFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p162">Этот атрибут определяет различные параметры объединенных коммуникаций, которые включены глобально для всех пользователей или контактных объектов. Этот атрибут представляет целочисленную битовую маску. Каждому параметру соответствует определенный бит.</span><span class="sxs-lookup"><span data-stu-id="bed14-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="bed14-833">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="bed14-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-834">4: UsePerUserUCPolicy (2 бит)</span><span class="sxs-lookup"><span data-stu-id="bed14-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="bed14-835">Если этот бит задан, политика объединенных коммуникаций определяется для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="bed14-836">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-837">msRTCSIP-UCPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-838">Этот атрибут, который может содержать только одно значение, содержит различающееся имя политики объединенных коммуникаций, заданной для этого пользователя администратором.</span><span class="sxs-lookup"><span data-stu-id="bed14-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="bed14-839">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-840">msRTCSIP-UserDomainList (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="bed14-p163">Этот атрибут предоставляет список всех доменов леса, содержащих пользователей, которые поддерживают SIP. По умолчанию этот атрибут содержит пустой список, который указывает, что все домены леса поддерживают SIP.</span><span class="sxs-lookup"><span data-stu-id="bed14-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="bed14-843">Допустимые значения — строки, представляющие имена отдельных доменов.</span><span class="sxs-lookup"><span data-stu-id="bed14-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="bed14-844">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="bed14-845">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-846">msRTCSIP — UserEnabled</span><span class="sxs-lookup"><span data-stu-id="bed14-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="bed14-847">Этот атрибут определяет, включен ли в данный момент пользователь для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed14-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-848">msRTCSIP — Усерекстенсион</span><span class="sxs-lookup"><span data-stu-id="bed14-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="bed14-849">Этот атрибут, поддерживающий несколько значений, содержит список пар "имя — значение" в формате " &quot; имя = значение". &quot; Этот атрибут помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="bed14-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="bed14-850">Новые средства Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="bed14-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-851">msRTCSIP — Усерлокатионпрофиле</span><span class="sxs-lookup"><span data-stu-id="bed14-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="bed14-852">Этот атрибут содержит различающееся имя, которое указывает на объект профиля местоположения.</span><span class="sxs-lookup"><span data-stu-id="bed14-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="bed14-853">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bed14-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-854">msRTCSIP — УсерполиЦиес</span><span class="sxs-lookup"><span data-stu-id="bed14-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="bed14-855">Этот атрибут используется для хранения пар "имя=значение" для политик пользователей.</span><span class="sxs-lookup"><span data-stu-id="bed14-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="bed14-856">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bed14-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-857">msRTCSIP — UserPolicy</span><span class="sxs-lookup"><span data-stu-id="bed14-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="bed14-p164">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен с двоичными (DN_WITH_BINARY) указателями на глобальные политики пользователей разных типов. Двоичные указатели указывают тип политики, на которую указывает часть различающегося имени.</span><span class="sxs-lookup"><span data-stu-id="bed14-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="bed14-860">Допустимые двоичные значения:</span><span class="sxs-lookup"><span data-stu-id="bed14-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-861">0x00000001: политика собрания</span><span class="sxs-lookup"><span data-stu-id="bed14-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="bed14-862">0x00000002: политика объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="bed14-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="bed14-863">0x00000005: политика присутствия</span><span class="sxs-lookup"><span data-stu-id="bed14-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-864">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-865">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="bed14-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="bed14-p165">Этот атрибут содержит ИД группы маршрутизации SIP. Пользователи одной группы будут регистрироваться на одном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="bed14-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="bed14-868">Новые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bed14-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-869">msRTCSIP — Вебкомпонентсдата</span><span class="sxs-lookup"><span data-stu-id="bed14-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="bed14-p166">Этот атрибут поддерживает несколько значений. Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="bed14-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="bed14-872">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-873">msRTCSIP — Вебкомпонентспуладдресс</span><span class="sxs-lookup"><span data-stu-id="bed14-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="bed14-874">Этот атрибут, поддерживающий одно значение, указывает на пул или сервер Standard Edition, к которым принадлежат веб-компоненты.</span><span class="sxs-lookup"><span data-stu-id="bed14-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="bed14-875">Прямая ссылка: <strong>ИД ссылки 11028</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="bed14-876">Обратная ссылка: <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-877">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-878">msRTCSIP — Вебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="bed14-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="bed14-p167">Этот атрибут, поддерживающий несколько значений, представляет список различающихся имен. Атрибут содержит список всех веб-серверов, связанных с этим пулом.</span><span class="sxs-lookup"><span data-stu-id="bed14-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="bed14-881">Обратная ссылка: <strong>ИД ссылки 11029</strong></span><span class="sxs-lookup"><span data-stu-id="bed14-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="bed14-882">Обратная ссылка: <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="bed14-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="bed14-883">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="bed14-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-884">msRTCSIP-WMIInstanceId (устаревший)</span><span class="sxs-lookup"><span data-stu-id="bed14-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bed14-885">Новые средства Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="bed14-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="bed14-886">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="bed14-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="bed14-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="bed14-888">Существующий атрибут Active Directory используется службами телефонии для указания списка альтернативных TCP/IP-адресов телефона.</span><span class="sxs-lookup"><span data-stu-id="bed14-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="bed14-889">Новый атрибут в ОС Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bed14-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-890">фонеоффицеосер</span><span class="sxs-lookup"><span data-stu-id="bed14-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="bed14-891">Этот существующий атрибут Active Directory используется компонентами голосовой связи в Lync Server только для объектов Contact, в целях маршрутизации вызовов для автосекретаря единой системы обмена сообщениями и номеров абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="bed14-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="bed14-892">В этом атрибуте, поддерживающем несколько значений, хранится адрес для переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="bed14-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="bed14-893">Эта учетная запись создана специально для доступа к автосекретарю и подписчику.</span><span class="sxs-lookup"><span data-stu-id="bed14-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="bed14-894">Администраторы не должны изменять атрибуты этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="bed14-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="bed14-895">Новый атрибут в ОС Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="bed14-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed14-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bed14-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="bed14-897">Этот существующий атрибут Active Directory, поддерживающий несколько значений, является частью базовой схемы Active Directory, представленной в Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="bed14-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="bed14-898">Этот атрибут содержит различные адреса X400, X500 и SMTP электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="bed14-899">В Live Communications Server 2003 и более поздних версий URI пользователя SIP добавляется в этот список с помощью &quot; тега SIP: &quot; .</span><span class="sxs-lookup"><span data-stu-id="bed14-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="bed14-900">Этот атрибут используется для поиска SIP URI пользователя следующими приложениями:</span><span class="sxs-lookup"><span data-stu-id="bed14-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="bed14-901">Клиент обмена сообщениями и совместной работы Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="bed14-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="bed14-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="bed14-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bed14-903">Новый атрибут в ОС Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="bed14-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed14-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="bed14-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="bed14-905">Этот существующий атрибут Active Directory содержит телефонный номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="bed14-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="bed14-906">Новый атрибут в ОС Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="bed14-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


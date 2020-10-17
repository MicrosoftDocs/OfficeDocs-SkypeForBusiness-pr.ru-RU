---
title: 'Lync Server 2013: атрибуты и описания схемы'
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
ms.openlocfilehash: bcd4c3f3da44be2721d1c6bfc1c1ceece47b6232
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510876"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="2cc5d-102">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc5d-102">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cc5d-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2cc5d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2cc5d-104">В этом разделе описываются все атрибуты схемы, используемые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="2cc5d-105">Классы, связанные с атрибутами, приведены [в статье атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="2cc5d-106">Список классов и атрибутов, которые являются новыми в Lync Server 2013, представлен в статье [изменения схемы в Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="2cc5d-p102">Связанные атрибуты указываются в виде прямых или обратных ссылок. Атрибут, который ссылается на другой объект, является прямой ссылкой, а атрибут другого объекта, который ссылается на первичный объект, является обратной ссылкой. Прямые ссылки поддерживают обновление, а обратные ссылки — только чтение.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="2cc5d-p103">Значения некоторых атрибутов задаются с помощью битовой маски. В этом случае каждый параметр представляется в виде бита, а десятичное значение соответствует позиции бита. Отсчет позиции бита начинается с 0 разряда. Например, для 1 в двоичной системе счисления установлен 0 бит, а для 10000 в двоичной системе счисления задан 4 бит. Каждый бит представляет свойство. Примеры:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="2cc5d-116">10000 (двоичное) соответствует десятичному значению 16 (т. е. задан 4 бит).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="2cc5d-117">100000000 (двоичное) соответствует десятичному значению 256 (т. е. задан 8 бит).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="2cc5d-118">1100 (двоичное) соответствует десятичному значению 12 (т. е. заданы 2 и 3 биты; включены свойства, соответствующие обоим битам).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="2cc5d-119">1111000001 (двоичное) соответствует десятичному значению 961 (т. е. заданы биты 0, 6, 7, 8 и 9; включены свойства, соответствующие каждому из этих битов).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="2cc5d-120">Атрибуты схемы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc5d-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cc5d-121">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2cc5d-121">Attribute</span></span></th>
<th><span data-ttu-id="2cc5d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2cc5d-122">Description</span></span></th>
<th><span data-ttu-id="2cc5d-123">Comments</span><span class="sxs-lookup"><span data-stu-id="2cc5d-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="2cc5d-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-125">Существующий атрибут в доменных службах Active Directory, который теперь связан с классами <strong>msRTCSIP-Pool</strong> и <strong>msRTCSIP-мониторингсервер</strong> .</span><span class="sxs-lookup"><span data-stu-id="2cc5d-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="2cc5d-126">Этот атрибут указывает полное доменное имя (FQDN) пула или сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="2cc5d-127">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-128">Новые средства Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-129">msDS — Саурцеобжектдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p105">Этот атрибут содержит строковое представление различающегося имени объекта в другом лесу, который соответствует этому объекту. Этот атрибут используется для расширения групп рассылки и функции автосекретаря. Этот атрибут определен в схеме Active Directory по умолчанию для Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="2cc5d-133">Чтобы избежать необходимости обновления доменных служб Active Directory до Windows Server 2003 R2, схема Active Directory дополняет схему Windows Server 2003 этим определением атрибута.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-134">Новые данные в Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="2cc5d-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-136">Этот атрибут, поддерживающий несколько значений, задает параметры голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="2cc5d-137">Общий доступ к этому атрибуту осуществляется с помощью единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-138">Новые в Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="2cc5d-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-140">Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="2cc5d-141">Политики хранения определяют срок хранения элементов почтового ящика для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="2cc5d-142">Этот атрибут используется совместно с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-143">Новые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-144">msRTCSIP — Акпинфо</span><span class="sxs-lookup"><span data-stu-id="2cc5d-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-145">Этот атрибут используется для хранения сведений о поставщике услуг аудиоконференций для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-146">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-147">msRTCSIP — Аппликатиондестинатион</span><span class="sxs-lookup"><span data-stu-id="2cc5d-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-148">Этот атрибут указывает запись доверенной службы для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-149">Новые данные в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-150">msRTCSIP — Аппликатионлист</span><span class="sxs-lookup"><span data-stu-id="2cc5d-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-151">Этот атрибут содержит список размещенных приложений на сервере приложений.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-152">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-153">msRTCSIP — Аппликатионоптионс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-154">Этот атрибут задает параметры контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-155">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-156">msRTCSIP — Аппликатионпримарилангуаже</span><span class="sxs-lookup"><span data-stu-id="2cc5d-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-157">Этот атрибут содержит основной язык для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-158">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-159">msRTCSIP — Аппликатионсекондарилангуажес</span><span class="sxs-lookup"><span data-stu-id="2cc5d-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-160">Этот атрибут, поддерживающий несколько значений, содержит дополнительные языки для контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-161">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-162">msRTCSIP — Аппликатионсервербл</span><span class="sxs-lookup"><span data-stu-id="2cc5d-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p108">Этот атрибут содержит список серверов приложений, которые принадлежат этому пулу. Прямая ссылка: <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-165">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-166">msRTCSIP — Аппликатионсерверпуллинк</span><span class="sxs-lookup"><span data-stu-id="2cc5d-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-167">Этот атрибут указывает пул, которому принадлежит этот сервер приложений.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="2cc5d-168">Это прямая ссылка.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-168">This is the forward link.</span></span> <span data-ttu-id="2cc5d-169">Обратная ссылка: <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-170">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-171">msRTCSIP-ArchiveDefault (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-172">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-173">Устаревшие данные в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-174">msRTCSIP-ArchiveDefaultFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p110">Этот атрибут задает глобальное значение по умолчанию в пределах границы леса для функции архивации всех коммуникаций пользователей. Этот атрибут задается принудительно агентом архивации. Этот атрибут может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-178"><strong>TRUE</strong>: архивировать коммуникации всех пользователей</span><span class="sxs-lookup"><span data-stu-id="2cc5d-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-179"><strong>FALSE</strong>: не архивировать коммуникации всех пользователей</span><span class="sxs-lookup"><span data-stu-id="2cc5d-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="2cc5d-180">Этот атрибут управляет архивацией коммуникаций пользователей во внутренней сети на глобальном уровне (в пределах границы леса).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="2cc5d-181"><strong>Для Live Communications Server 2005 (в настоящее время не поддерживается)</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="2cc5d-182">Этот атрибут может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-183">0: архивировать текст сообщения [бит 0]</span><span class="sxs-lookup"><span data-stu-id="2cc5d-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-184">1: не архивировать текст сообщения [бит 0]</span><span class="sxs-lookup"><span data-stu-id="2cc5d-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="2cc5d-185"><strong>Для Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="2cc5d-186">Этот атрибут может принимать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-187">0: ArchiveFederationDefaultWithoutBody (не поддерживается)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="2cc5d-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="2cc5d-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="2cc5d-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="2cc5d-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="2cc5d-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="2cc5d-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="2cc5d-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="2cc5d-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="2cc5d-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="2cc5d-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="2cc5d-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="2cc5d-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="2cc5d-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="2cc5d-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-202">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-203">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-204">msRTCSIP-ArchiveFederationDefault (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-205">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-206">Устаревшие данные в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-207">msRTCSIP-ArchiveFederationDefaultFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-208">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-209">Устаревшие данные в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-210">msRTCSIP — Арчивинженаблед</span><span class="sxs-lookup"><span data-stu-id="2cc5d-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p111">Этот атрибут является целым значением, используемым в качестве битового поля, которое указывает, архивируются ли коммуникации отдельного пользователя. Этот атрибут задается принудительно агентом архивации. Он помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2cc5d-214">Область этого атрибута относится к одному пользователю или контакту.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="2cc5d-215">Допустимые значения (и сопоставленные битовые позиции) в Lync Server приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-216">0: не архивировать (бит не задан)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-217">1: не поддерживается (0 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-218">2: не поддерживается (1 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-219">4: архивировать внутренние коммуникации (2 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-220">8: архивировать федеративные коммуникации (3 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="2cc5d-221">Ранее допустимые значения в Live Communications Server 2005 следующие:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-222">0: использовать значение по умолчанию, заданное атрибутами <strong>msRTCSIP-ArchiveDefault</strong> и <strong>msRTCSIP-ArchiveFederation</strong>, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-223">1: архивировать</span><span class="sxs-lookup"><span data-stu-id="2cc5d-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-224">2: не архивировать</span><span class="sxs-lookup"><span data-stu-id="2cc5d-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-225">3: архивировать без текста сообщения</span><span class="sxs-lookup"><span data-stu-id="2cc5d-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-226">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-227">msRTCSIP-ArchivingServerData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-228">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-229">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-230">msRTCSIP-ArchivingServerVersion (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p113">Этот атрибут задает версию службы архивации. Этот атрибут представляет собой целое значение, которое увеличивается на 1 с каждым официальным выпуском продукта. Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-234">Не определено: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2cc5d-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="2cc5d-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2cc5d-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="2cc5d-236">                 Live Communications Server 2005 с SP1</span><span class="sxs-lookup"><span data-stu-id="2cc5d-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2cc5d-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2cc5d-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-239">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-240">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-241">msRTCSIP — Баккендсервер</span><span class="sxs-lookup"><span data-stu-id="2cc5d-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p114">Этот атрибут задает полное доменное имя внутреннего сервера пула. Поскольку в одном пуле может быть только один внутренний сервер, этот атрибут может иметь только одно значение.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="2cc5d-244">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-245">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-246">msRTCSIP — Конференцедиректорихомепул</span><span class="sxs-lookup"><span data-stu-id="2cc5d-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-247">Этот атрибут содержит идентификатор пула, содержащего каталог конференции.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-248">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-249">msRTCSIP — Конференцедиректорид</span><span class="sxs-lookup"><span data-stu-id="2cc5d-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-250">Этот атрибут содержит идентификатор каталога конференции.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-251">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-252">msRTCSIP — Конференцедиректоритаржетпул</span><span class="sxs-lookup"><span data-stu-id="2cc5d-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-253">Этот атрибут содержит идентификатор пула, в который перемещается каталог конференции.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-254">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-255">msRTCSIP по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2cc5d-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-256">Этот логический атрибут определяет, относится ли использование телефона к использованию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="2cc5d-257">Если атрибут имеет значение <strong>TRUE</strong>, использование телефона относится к использованию по умолчанию и оно не может быть удалено администратором.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="2cc5d-258">Если атрибут имеет значение <strong>FALSE</strong>, использование телефона может быть удалено.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-259">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-260">msRTCSIP — Дефаулткваекстерналурл</span><span class="sxs-lookup"><span data-stu-id="2cc5d-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-261">Этот атрибут определяет URL-адрес Communicator Web Access для пользователей, находящихся за пререшениями Организации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-262">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-263">msRTCSIP — Дефаулткваинтерналурл</span><span class="sxs-lookup"><span data-stu-id="2cc5d-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-264">Этот атрибут определяет URL-адрес веб-клиента Communicator для пользователей, находящихся внутри Организации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-265">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-266">msRTCSIP-DefaultLocationProfileLink (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-267">Этот атрибут, который может иметь только одно значение, содержит различающееся имя объекта класса профиля местоположения, назначенное ему.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="2cc5d-268">Прямая ссылка: <strong>ИД ссылки 11036</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="2cc5d-269">Обратная ссылка: <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-270">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-271">msRTCSIP-DefaultPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-272">Этот логический атрибут указывает, является ли политика политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="2cc5d-273">Для политики по умолчанию атрибут имеет значение <strong>TRUE</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-274">Новые средства Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2cc5d-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="2cc5d-275">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-276">msRTCSIP-DefaultRouteToEdgeProxy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-277">Этот атрибут указывает полное доменное имя пограничного сервера, на котором запущена служба пограничного доступа, если к нему возможен прямой доступ, или от аппаратного балансировщика нагрузки для пула серверов, на которых работает пограничная служба доступа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="2cc5d-278">Если доступ к серверам с пограничной службой доступа возможен только через одного или нескольких директоров, этот атрибут задает полное доменное имя и (необязательно) номер порта для директора или аппаратного балансировщика нагрузки, обслуживающего пул директоров.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="2cc5d-279">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-280">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-281">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-282">msRTCSIP-DefaultRouteToEdgeProxyPort (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-283">Этот атрибут представляет номер порта, который следует использовать для подключения к серверу с пограничной службой доступа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="2cc5d-284">Допустимым является целое значение, указывающее номер используемого порта.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="2cc5d-285">По умолчанию используется значение 5061.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-286">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-287">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-288">msRTCSIP-DefPresenceSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-289">Этот атрибут указывает период времени ожидания по умолчанию для подписки на сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-290">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-291">msRTCSIP-DefRegistrationTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-292">Этот атрибут указывает период времени ожидания по умолчанию для регистрации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-293">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-295">Этот атрибут указывает период времени ожидания по умолчанию для перемещения данных подписки.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-296">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-297">msRTCSIP — Деплойментлокатор</span><span class="sxs-lookup"><span data-stu-id="2cc5d-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-298">Этот атрибут используется в технологии расщепления домена и содержит полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-299">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-300">msRTCSIP-Description (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-301">Этот строковый атрибут (Юникод), который может иметь только одно значение, содержит понятное описание маршрута телефона или правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-302">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-303">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-304">msRTCSIP — Домаиндата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-305">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-306">msRTCSIP — имя_домена</span><span class="sxs-lookup"><span data-stu-id="2cc5d-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-307">Этот атрибут указывает домен, заданный для регистратора.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-308">msRTCSIP — Еджепроксидата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-309">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-310">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-311">msRTCSIP — Еджепроксифкдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-312">Этот атрибут задает полное доменное имя сервера, на котором запущена пограничная служба доступа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="2cc5d-313">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-314">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-315">msRTCSIP-EnableBestEffortNotify (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p119">Этот атрибут указывает, создает ли сервер запрос Best Effort NOTIFY (BENOTIFY) вместо запроса NOTIFY в ответ на запрос SUBSCRIBE, полученный от клиента. BENOTIFY — это расширение для подтверждения уведомления о подписке, которое позволяет повысить производительность за счет создания запросов BENOTIFY вместо обычных запросов NOTIFY. Преимущество производительности заключается в том, что запрос BENOTIFY не требует ответа 200 OK от клиента в отличие от запроса NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="2cc5d-319">Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2cc5d-320">Live Communications Server 2003 не поддерживает запросы уведомления.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="2cc5d-321">Для взаимодействия с серверными приложениями, написанными с помощью серверного API Live Communications Server 2003, работающего на серверах Live Communications Server 2005 и сторонних серверах, запросы уведомления можно отключить, задав для параметра значение <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="2cc5d-322">В настоящее время запрос BENOTIFY не является частью стандартизации протокола SIP IETF.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="2cc5d-323">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-324">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-325">msRTCSIP-EnableFederation (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p121">Этот атрибут является глобальным переключателем, с помощью которого администраторы могут указывать, могут ли пользователи их организации обмениваться данными с пользователями из других организаций. С помощью этого атрибута администратор может переопределить атрибут <strong>FederationEnabled</strong> отдельного пользователя. Этот атрибут позволяет защитить внутреннюю сеть от атак из Интернета, использующих вирусы-черви и другие типы вирусов, или целевых атак.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="2cc5d-329">Допустимые значения и биты:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-330">1: включен для общедоступных служб обмена мгновенными сообщениями (0 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-331">2: зарезервировано (1 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-332">4: зарезервировано (2 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-333">8: зарезервировано (3 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-334">16: удаленное управление звонками включено [телефония] (4 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-335">64: AllowOrganizeMeetingWithAnonymousParticipants (разрешает пользователям приглашать анонимных пользователей на собрания (6 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-336">128: UCEnabled (включает объединенные коммуникации для пользователей) (7 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-337">256: EnabledForEnhancedPresence (предоставляет пользователям возможность подключения к общедоступным службам обмена мгновенными сообщениями) (8 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-338">512: RemoteCallControlDualMode (9 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-339">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-340">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-341">msRTCSIP — EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="2cc5d-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-342">Этот атрибут указывает, загружены ли службы Enterprise Services на заданном сервере.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-343">msRTCSIP — Екстенсиондата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-344">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-345">msRTCSIP — Екстерналакцесскоде</span><span class="sxs-lookup"><span data-stu-id="2cc5d-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-346">Этот атрибут содержит код быстрого набора для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-347">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-348">msRTCSIP — Федератионенаблед</span><span class="sxs-lookup"><span data-stu-id="2cc5d-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p122">Этот атрибут указывает, включена ли федерация для отдельного пользователя. Этот атрибут задается службами Enterprise Services. Он отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2cc5d-352">Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-353">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-354">msRTCSIP — Фронтендсерверс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-355">Этот атрибут представляет список имен доменов всех серверов Enterprise Edition, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="2cc5d-356">Обратная ссылка: <strong>ИД ссылки 11023</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="2cc5d-357">Прямая ссылка: <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-358">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-359">msRTCSIP-Gateways (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-360">Этот строковый атрибут, поддерживающий несколько значений, содержит список шлюзов и портов (для каждого шлюза).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-361">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-362">msRTCSIP-GlobalSettingsData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p123">Этот атрибут содержит пары "имя:значение". Для параметра <strong>разрешить опрос сведений о присутствии</strong> пара имя:значение уже определена.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-365">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-366">msRTCSIP — Граупингид</span><span class="sxs-lookup"><span data-stu-id="2cc5d-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-367">Этот атрибут является уникальным идентификатором группы, используемой для группировки записей адресной книги.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-368">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-369">msRTCSIP-HomeServer (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-370">Новый сервер Live Communications Server 2003 (не используется).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="2cc5d-371">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-372">msRTCSIP-HomeServerString (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-373">Новые средства Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="2cc5d-374">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-375">msRTCSIP-HomeUsers (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-376">Новый сервер Live Communications Server 2003 (не используется).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="2cc5d-377">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-378">msRTCSIP — Интернетакцессенаблед</span><span class="sxs-lookup"><span data-stu-id="2cc5d-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p124">Этот атрибут указывает, разрешен ли отдельному пользователю внешний доступ. Этот атрибут задается службами Enterprise Services. Он отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2cc5d-382">Допустимые значения: <strong>TRUE</strong> или <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-383">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-384">msRTCSIP-IsMaster (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-385">Новые средства Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2cc5d-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="2cc5d-386">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-387">msRTCSIP — Line</span><span class="sxs-lookup"><span data-stu-id="2cc5d-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-388">Этот атрибут с одним значением содержит идентификатор устройства (URI SIP или TEL URI телефона, который пользовательские элементы управления) использует Lync для телефонии.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="2cc5d-389">Этот атрибут помечен для репликации глобального каталога и индексируется.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="2cc5d-390">Если для пользователя включена поддержка корпоративной голосовой связи, то этот атрибут используется для хранения номера телефона пользователя в формате E.164.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-391">Новые средства Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-392">msRTCSIP — Линесервер</span><span class="sxs-lookup"><span data-stu-id="2cc5d-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p126">Этот атрибут, поддерживающий одно значение, содержит URI SIP сервера шлюза CSTA-SIP. Этот атрибут помечен для репликации глобального каталога, но не индексируется.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-395">Новые средства Microsoft Office Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-396">msRTCSIP-LocalNormalizationData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-397">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-398">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-399">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-400">msRTCSIP-LocalNormalizationLinks (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p127">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен с локальной нормализацией, связанных с этим профилем местоположения. Этот атрибут имеет тип "двоичное DN". Между профилем местоположения и локальными правилами нормализации существует отношение "один ко многим". Порядок обработки списка различающихся имен с локальной нормализацией должен совпадать с порядком, заданным администратором. Сохранение порядка задается двоичной частью типа "двоичное DN", которая указывает индекс порядка.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="2cc5d-406">Прямая ссылка: <strong>ИД ссылки 11034</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="2cc5d-407">Соответствующая обратная ссылка: <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-408">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-409">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-410">msRTCSIP — Локалнормализатионоптионс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-411">Этот атрибут содержит список параметров для правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-412">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-413">msRTCSIP-LocationName (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p128">Этот атрибут, поддерживающий одно значение, содержит понятное имя профиля местоположения, указывающее местоположение, которое представляет этот профиль. Поскольку профилей местоположения может быть несколько, администратору требуется способ, позволяющий легко различать разные профили.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-416">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-417">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-418">msRTCSIP-locationProfileBL (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p129">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен профилей местоположения. Этот атрибут указывает обратную ссылку на профили местоположения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="2cc5d-421">Обратная ссылка: <strong>ИД ссылки 11035</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="2cc5d-422">Этот атрибут указывает прямую ссылку на <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-423">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-424">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-425">msRTCSIP-LocationProfileData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-426">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-427">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-428">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-429">msRTCSIP — Локатионпрофилеоптионс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-430">Этот атрибут содержит параметры профиля местоположения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-431">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-432">msRTCSIP — Маппингконтакт</span><span class="sxs-lookup"><span data-stu-id="2cc5d-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-433">Этот атрибут, поддерживающий несколько значений, содержит список контактов приложения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-434">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-435">msRTCSIP — Маппинглокатион</span><span class="sxs-lookup"><span data-stu-id="2cc5d-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-436">Этот атрибут, поддерживающий несколько значений, содержит список профилей местоположения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-437">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-438">msRTCSIP-MaxNumOutstandingSearchPerServer (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-439">Этот атрибут представляет максимальное число ожидающих запросов на поиск для каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-440">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-441">msRTCSIP-MaxNumSubscriptionsPerUser (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-442">Этот атрибут представляет максимальное число подписок для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-443">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-444">msRTCSIP-MaxPresenceSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-445">Этот атрибут представляет максимальное время ожидания подписки.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-446">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-447">msRTCSIP-MaxRegistrationsTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-448">Этот атрибут представляет максимальное время ожидания регистрации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-449">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-451">Этот атрибут представляет максимальное время ожидания перемещения данных подписки.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-452">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-453">msRTCSIP — Мкудата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-454">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-455">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-456">msRTCSIP — Мкуфакторяддресс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p130">Этот атрибут представляет точку управления службой в классе компьютера, которая указывает обратную ссылку на фабрику многоточечного управляющего узла, к которой она принадлежит. Эта точка управления службой и атрибут создаются для каждого многоточечного управляющего узла Майкрософт. Каждый многоточечный управляющий узел Майкрософт должен найти внутренний сервер пула, к которому он принадлежит, чтобы получить у него параметры уровня пула.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="2cc5d-p131">Значением этого атрибута является различающееся имя фабрики многоточечного управляющего узла. Этот атрибут поддерживает одно значение и помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2cc5d-462">Прямая ссылка: <strong>ИД ссылки 11026</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="2cc5d-463">Соответствующая обратная ссылка: <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-464">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-465">msRTCSIP — Мкуфакторидата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p132">Это зарезервированный атрибут, который может принимать несколько строковых значений. Параметры, сохраняемые в этом атрибуте, представляют пары имя=значение. В настоящее время определены следующие пары имя=значение:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-469">Факторюрл = &lt; URL-адрес&gt;</span><span class="sxs-lookup"><span data-stu-id="2cc5d-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-470">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-471">msRTCSIP — Мкуфакторипас</span><span class="sxs-lookup"><span data-stu-id="2cc5d-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-472">Этот атрибут, поддерживающий одно значение, содержит различающееся имя одной фабрики многоточечного управляющего узла, связанной с пулом.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="2cc5d-473">Прямая ссылка: <strong>ИД ссылки 11024</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="2cc5d-474">Соответствующая обратная ссылка: <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-475">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-476">msRTCSIP — Мкуфакторипровидерид</span><span class="sxs-lookup"><span data-stu-id="2cc5d-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-477">Этот атрибут, поддерживающий одно строковое значение, указывает глобальный уникальный ИД поставщика фабрики многоточечного управляющего узла.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="2cc5d-478">На основании значения глобального уникального ИД фабрика многоточечного управляющего узла определяет, требуется ли обслуживать определенный тип многоточечного управляющего узла.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="2cc5d-479">Если GUID имеет значение <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, процесс фабрики MCU (доступен по умолчанию в Lync Server) будет обрабатывать его.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="2cc5d-480">В противном случае процесс фабрики не будет обслуживать многоточечный управляющий узел.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-481">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-482">msRTCSIP — Мкусерверс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p134">Этот атрибут, поддерживающий несколько значений, представляет список различающихся имен. Этот атрибут содержит список всех серверов многоточечного управляющего узла одного типа, имеющих одинакового поставщика, связанного с этой фабрикой многоточечного управляющего узла. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="2cc5d-486">Обратная ссылка: ИД ссылки 11027</span><span class="sxs-lookup"><span data-stu-id="2cc5d-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="2cc5d-487">Соответствующая обратная ссылка: <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-488">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-489">msRTCSIP — Мкутипе</span><span class="sxs-lookup"><span data-stu-id="2cc5d-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-490">Этот строковый атрибут, поддерживающий одно значение, указывает тип данных, которые может обработать многоточечный управляющий узел.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="2cc5d-491">Допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-492">назначить</span><span class="sxs-lookup"><span data-stu-id="2cc5d-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-493">аудио и видео</span><span class="sxs-lookup"><span data-stu-id="2cc5d-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-494">чат</span><span class="sxs-lookup"><span data-stu-id="2cc5d-494">chat</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-495">Телефон — CONF</span><span class="sxs-lookup"><span data-stu-id="2cc5d-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-496">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-497">msRTCSIP — Мкувендор</span><span class="sxs-lookup"><span data-stu-id="2cc5d-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p135">Этот строковый атрибут, поддерживающий одно значение, указывает имя поставщика многоточечного управляющего узла. Для всех многоточечных управляющих узлов Майкрософт этот атрибут будет иметь значение <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-500">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-501">msRTCSIP-MeetingFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p136">Этот атрибут определяет различные параметры собрания, которые включены глобально для всех пользователей или контактных объектов. Этот атрибут представляет собой битовую маску целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="2cc5d-504">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (запретить пользователям приглашать на собрания анонимных пользователей) (биты не заданы)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-506">4: Alloworganizemeetingwithanonymousparticipants is — все пользователи (разрешают всем пользователям приглашать анонимных пользователей для собраний) (Битовая позиция 2)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (разрешить пользователям приглашать на собрания анонимных пользователей с учетом параметров пользователя) (3 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-508">16: UserPerUserMeetingPolicy (политика собрания определяется для каждого пользователя) (4 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-509">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-510">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-511">msRTCSIP-MeetingPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-512">Этот атрибут задает различающееся имя политики, назначенной администратором для этого пользователя в качестве атрибута с одним значением.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-513">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-514">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-515">msRTCSIP-MinPresenceSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-516">Этот атрибут указывает минимальное время ожидания для подписки на сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-517">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-518">msRTCSIP-MinRegistrationTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-519">Этот атрибут указывает минимальное время ожидания регистрации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-520">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-521">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-523">Этот атрибут задает минимальное время ожидания для перемещения данных подписки.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-524">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-525">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-526">msRTCSIP — Миррорбаккендсервер</span><span class="sxs-lookup"><span data-stu-id="2cc5d-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-527">Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-528">Новые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-529">msRTCSIP — Мобилитифлагс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-530">Этот атрибут содержит параметры и флаги, определяющие параметры мобильности.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-531">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-532">msRTCSIP — Мобилитиполици</span><span class="sxs-lookup"><span data-stu-id="2cc5d-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-533">Этот атрибут содержит различающееся имя для объекта политики мобильности.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-534">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-535">msRTCSIP-NumDevicesPerUser (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-536">Этот атрибут указывает максимальное число устройств, на которых пользователь может зарегистрироваться и подписаться на сведения о присутствии для коммуникаций SIP.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-537">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-538">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-539">msRTCSIP — Оптионфлагс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p137">Этот атрибут указывает параметры, включенные для пользователя или контактного объекта. Этот атрибут является битовой маской целочисленного типа. Каждому параметру соответствует определенный бит. Этот атрибут отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2cc5d-544">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-545">1: включен для подключения к общедоступным службам обмена мгновенными сообщениями (0 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-546">2: зарезервировано (1 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-547">4: зарезервировано (2 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-548">8: зарезервировано (3 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-549">16: удаленное управление звонками включено [телефония] (4 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-550">64: AllowOrganizeMeetingWithAnonymousParticipants (разрешает пользователям приглашать на собрания анонимных пользователей (6 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-551">128: UCEnabled (включает объединенные коммуникации для пользователей) (7 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-552">256: EnabledForEnhancedPresence (включает для пользователей возможность подключения к общедоступным службам обмена мгновенными сообщениями) (8 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-553">512: RemoteCallControlDualMode (9 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-554">Новые средства Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-555">msRTCSIP — Оригинаторсид</span><span class="sxs-lookup"><span data-stu-id="2cc5d-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-556">Этот атрибут используется в топологии с лесом ресурсов и центральной топологии леса для включения функции единого входа при копировании ObjectSID пользователя из учетной записи субъекта безопасности Windows NT Server в этот атрибут соответствующего пользователя или контактного объекта в лесу ресурсов или центрального леса.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="2cc5d-557">Веб-клиент Communicator ищет пользователя в доменных СЛУЖБах Active Directory, используя этот атрибут или ObjectSID пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="2cc5d-558">Этот атрибут отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-559">msRTCSIP — Овнерурн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-560">Этот атрибут представляет унифицированное имя ресурса (URN) владельца контакта приложения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-561">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-562">msRTCSIP-Pattern (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p139">Этот строковый атрибут, поддерживающий одно значение, содержит шаблон, используемый для поиска соответствия набираемых номеров формату E.164. Если набираемый номер соответствует этому шаблону, к нему применяется преобразование.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-565">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-566">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-567">msRTCSIP-PhoneRouteBL (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p140">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен телефонных маршрутов. Этот атрибут указывает обратные ссылки на телефонные маршруты.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="2cc5d-570">Обратная ссылка: <strong>ИД ссылки 11033</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="2cc5d-571">Прямая ссылка: <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-572">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-573">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-574">msRTCSIP-PhoneRouteData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-575">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-576">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-577">msRTCSIP-PhoneRouteName (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-578">Этот строковый (Юникод) атрибут, поддерживающий одно значение, указывает понятное имя телефонного маршрута для простоты идентификации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-579">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-580">msRTCSIP-PhoneUsageData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-581">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-582">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-583">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-584">msRTCSIP-PolicyContent (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p141">Это строковый (Юникод) атрибут, поддерживающий одно значение. Этот строковый атрибут содержит определение политики в формате XML. Определение схемы XML идентично для разных типов политик. Разные типы политик отличаются только параметрами.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="2cc5d-588">Определение схемы XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="2cc5d-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="2cc5d-589">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-590">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-591">msRTCSIP-PolicyData (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-592">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-593">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-594">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-595">msRTCSIP-PolicyType (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p142">Этот строковый (Юникод) атрибут, поддерживающий одно значение, содержит тип политики. Допустимые типы политик:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-598">назначить</span><span class="sxs-lookup"><span data-stu-id="2cc5d-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-599">телефонии</span><span class="sxs-lookup"><span data-stu-id="2cc5d-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-600">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-601">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-602">msRTCSIP — Пуладдресс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-603">Этот атрибут указывает обратную ссылку на пул, к которому принадлежит компьютер.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="2cc5d-604">Этот атрибут задается независимо от того, работает ли на компьютере выпуск Standard Edition или корпоративный выпуск Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="2cc5d-605">Этот атрибут отмечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="2cc5d-606">Допустимым значением является доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="2cc5d-607">Прямая ссылка: <strong>ИД ссылки 11022</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="2cc5d-608">Обратная ссылка: <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-609">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-610">msRTCSIP — Пуладдрессес</span><span class="sxs-lookup"><span data-stu-id="2cc5d-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-611">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен пулов, с которыми связана фабрика многоточечного управляющего узла.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="2cc5d-612">Обратная ссылка: <strong>ИД ссылки 11025</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="2cc5d-613">Прямая ссылка: <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-614">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-615">msRTCSIP — Пулдата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-616">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-617">Новые средства Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-618">msRTCSIP — Пулдисплайнаме</span><span class="sxs-lookup"><span data-stu-id="2cc5d-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p144">Этот атрибут задает произвольное имя пула, отображаемое в консоли управления. Это имя может быть изменено администратором.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="2cc5d-621">Допустимым значением является строка, представляющая имя пула.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-622">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-623">msRTCSIP — Пулдомаинфкдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p145">Это строковый атрибут, который поддерживает одно значение. Этот атрибут содержит полное доменное имя пула в том случае, если администратор хочет создать интерфейсный пул с полным доменным именем, которое не соответствует структуре домена Active Directory, в которой создан интерфейсный пул (например, пространство имен SIP отсоединено от пространства имен DNS).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="2cc5d-p146">Майкрософт рекомендует сопоставить полное доменное имя интерфейсного пула части доменного имени в качестве домена Active Directory, в котором расположен пул. Следовательно, если для этого атрибута не задано значение, то полное доменное имя интерфейсного пула будет по умолчанию равно структуре доменного имени Active Directory, как задано атрибутом <strong>dnsHostName</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-628">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-629">msRTCSIP — Пулфунктионалити</span><span class="sxs-lookup"><span data-stu-id="2cc5d-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-630">Многозначный список доменных имен всех серверов Lync Server, корпоративных выпусков, связанных с пулом.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="2cc5d-631">Этот целочисленный атрибут указывает, поддерживает ли пул обмен мгновенными сообщениями, сведения о присутствии и собрания.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="2cc5d-632">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-633">Undefined: служба обмена мгновенными сообщениями и сведениями о присутствии (Live Communications Server 2005 и 2003)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-634">1: служба мгновенных сообщений и сведений о присутствии (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-635">2: обмен мгновенными сообщениями и сведения о присутствии и службе собраний (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-636">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-637">msRTCSIP — Пултипе</span><span class="sxs-lookup"><span data-stu-id="2cc5d-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p148">Этот атрибут указывает выпуск, установленный в пуле серверов (Standard Edition или Enterprise Edition). Этот атрибут является битовой маской целочисленного типа. Каждому параметру соответствует определенный бит.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="2cc5d-641">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-642">1: сервер Standard Edition, содержит пользователей (0 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-643">2: сервер Enterprise Edition, содержит пользователей (1 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-644">4: сервер Standard Edition, содержит приложения (2 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-645">8: сервер Enterprise Edition, содержит приложения (3 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="2cc5d-646">Так как Lync Server не поддерживает пулы, в которых размещаются только приложения, допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-647">5: сервер Standard Edition, содержит пользователей и приложения (0 и 2 биты)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-648">10: сервер Enterprise Edition, содержит пользователей и приложения (1 и 3 биты)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-649">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-650">msRTCSIP — Пулверсион</span><span class="sxs-lookup"><span data-stu-id="2cc5d-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p149">Этот атрибут указывает версию пула. Атрибут содержит целое значение, которое увеличивается на 1 с каждым новым выпуском продукта.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="2cc5d-653">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2cc5d-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2cc5d-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-656">2: Live Communications Server 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2cc5d-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2cc5d-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2cc5d-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-660">Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-661">msRTCSIP — Пресенцефлагс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-662">Этот атрибут содержит параметры и флаги, описывающие параметры присутствия.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-663">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-664">msRTCSIP — PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="2cc5d-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-665">Этот атрибут содержит различающееся имя для объекта политики присутствия.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-666">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-667">msRTCSIP — Примарихомесервер</span><span class="sxs-lookup"><span data-stu-id="2cc5d-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p150">Этот атрибут включает обмен сообщениями SIP для пользователя или контакта. Он добавлен в класс контакта, поскольку в топологии центрального леса, контактных объектах и объектах пользователей протокол SIP не включен.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="2cc5d-670">Допустимым значением является различающееся имя сервера Standard Edition или интерфейсного пула Enterprise Edition, в котором расположен пользователь.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-671">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-672">msRTCSIP — PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="2cc5d-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-673">Этот атрибут содержит SIP-адрес указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-674">msRTCSIP — PrivateLine</span><span class="sxs-lookup"><span data-stu-id="2cc5d-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-675">Этот атрибут содержит идентификатор устройства для телефонии.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-676">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-677">msRTCSIP — поддерживает маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="2cc5d-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-678">Этот атрибут является логическим атрибутом, используемым для определения того, авторизован ли Lync Server для маршрутизации в эту службу с помощью своего адреса GRUU.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="2cc5d-679">Если этому параметру присвоено значение <strong>true</strong>, то Lync Server авторизован для маршрутизации к этой службе.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="2cc5d-680">Если этому параметру присвоено значение <strong>false</strong>, то Lync Server не авторизован для маршрутизации к этой службе.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-681">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-682">msRTCSIP-RouteUsageAttribute (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p152">Этот строковый (Юникод) атрибут, поддерживающий одно значение, определяет атрибут, который задает использование телефонного маршрута. Телефонный маршрут выбирается с учетом двух элементов: атрибут использования, назначенный телефонному маршруту, и разрешенные атрибуты политики использования звонящего. Выбирается первый телефонный маршрут с атрибутами использования, которые совпадают с разрешенными атрибутами звонящего.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-686">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-687">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-688">msRTCSIP-RouteUsageLinks (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-689">Это атрибут, поддерживающий несколько значений, содержит список различающихся имен использования маршрута.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="2cc5d-690">Прямая ссылка: <strong>ИД ссылки 11032</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="2cc5d-691">Обратная ссылка: <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-692">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-693">msRTCSIP — Раутингпулдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-694">Этот атрибут содержит различающееся имя, которое указывает на пул, через который должен проходить весь трафик SIP для этого многоточечного управляющего узла или доверенной службы.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-695">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-696">msRTCSIP-RuleName (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-697">Этот строковый (Юникод) атрибут, поддерживающий одно значение, указывает понятное имя правила нормализации для простоты идентификации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-698">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-699">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-700">msRTCSIP — SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="2cc5d-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-701">Этот атрибут представляет версию схемы, развернутой в организации.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-702">msRTCSIP-SearchMaxRequests (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-703">Этот атрибут позволяет ограничить число результатов поиска, возвращаемых при поиске контакта в каталоге, когда пользователь выполняет поиск контакта с помощью Communicator.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="2cc5d-704">Этот атрибут будет переопределять значение, указанное клиентом.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-705">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-706">msRTCSIP-SearchMaxResults (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-707">Этот атрибут ограничивает число возвращаемых запросов поиска.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-708">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-709">msRTCSIP — Сервербл</span><span class="sxs-lookup"><span data-stu-id="2cc5d-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p154">Этот атрибут, поддерживающий несколько значений, представляет собой обратную ссылку, которая содержит список различающихся имен. Эти различающиеся имена указывают на пул или объект <strong>TrustedService</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="2cc5d-712">Прямая ссылка: <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-713">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-714">msRTCSIP — Сервердата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-715">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-716">msRTCSIP-ServerReferenceBL (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p155">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен. Различающиеся имена представляют собой обратные ссылки на другие серверные объекты, которые могут быть назначены профилю местоположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="2cc5d-719">Обратная ссылка: <strong>ИД ссылки 11037</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="2cc5d-720">Прямая ссылка: <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="2cc5d-721">Этот атрибут обратной ссылки указывает только пулы и серверы-посредники.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-722">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-723">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-724">msRTCSIP — Серверверсион</span><span class="sxs-lookup"><span data-stu-id="2cc5d-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p156">Этот атрибут указывает версию сервера. Номер версии применяется ко всем ролям сервера. Этот атрибут представляет собой целое значение, которое увеличивается на 1 с каждым официальным выпуском продукта.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="2cc5d-728">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-729">Не определено: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2cc5d-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="2cc5d-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2cc5d-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="2cc5d-731">                 Live Communications Server 2005 с SP1</span><span class="sxs-lookup"><span data-stu-id="2cc5d-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2cc5d-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2cc5d-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2cc5d-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc5d-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-736">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-737">msRTCSIP — Саурцеобжекттипе</span><span class="sxs-lookup"><span data-stu-id="2cc5d-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-738">Этот целочисленный атрибут, поддерживающий только одно значение, задает тип объекта, на который указывает <strong>msDS-SourceObjectDN</strong>:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-739">null | 0x00000001: объект субъекта пользователя Windows NT Server из другого леса</span><span class="sxs-lookup"><span data-stu-id="2cc5d-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-740">Следующие атрибуты представляют типы из другого леса для расширения группы рассылки:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2cc5d-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2cc5d-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2cc5d-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="2cc5d-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="2cc5d-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-746">0x90000000: представляет объект доступа автосекретаря или подписчика из того же леса или из другого леса</span><span class="sxs-lookup"><span data-stu-id="2cc5d-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-747">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-748">msRTCSIP-SubscriptionAuthRequired (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-749">Новые средства Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="2cc5d-750">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-751">msRTCSIP — Таржесомесервер</span><span class="sxs-lookup"><span data-stu-id="2cc5d-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-752">Этот атрибут позволяет переместить пользователя или контактного объекта из одного пула Lync Server в другой.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="2cc5d-753">Этот атрибут добавляется в класс контакта, поскольку протокол SIP включен в центральной топологии леса для контактных объектов, а не объектов пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="2cc5d-754">Допустимым значением является различающееся имя конечного сервера Standard Edition или интерфейсного пула, в который перемещается пользователь.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-755">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-756">msRTCSIP-TargetPhoneNumber (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-757">Этот строковый атрибут, который может содержать только одно значение, содержит шаблон номера телефона или диапазон номеров для маршрутизации на шлюзы, указанные с помощью атрибута <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-758">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-759">msRTCSIP — ТаржетусерполиЦиес</span><span class="sxs-lookup"><span data-stu-id="2cc5d-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-760">Этот атрибут хранит пары "имя — значение" для целевых политик для пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-761">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-762">msRTCSIP — TenantId</span><span class="sxs-lookup"><span data-stu-id="2cc5d-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-763">Этот атрибут содержит уникальный идентификатор для клиента.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-764">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-765">msRTCSIP-Translation (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-766">Этот атрибут используется функцией голосовой связи в Lync Server и содержит строку преобразования, применяемую к набранному номеру, если найдено соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-767">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="2cc5d-768">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-769">msRTCSIP — Трустедмкудата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-770">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-771">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-772">msRTCSIP — Трустедмкуфкдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p158">Этот атрибут представляет строковое значение, содержащее полное доменное имя многоточечного управляющего узла. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-776">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-777">msRTCSIP — Трустедпроксидата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-778">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-779">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-780">msRTCSIP — Трустедпроксифкдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p159">Этот атрибут представляет строковое значение, содержащее полное доменное имя прокси-сервера. Этот атрибут поддерживает только одно значение. Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-784">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-785">msRTCSIP — Трустедсервердата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-786">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-787">msRTCSIP — Трустедсерверфкдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-788">Этот атрибут может принимать только одно значение и содержит полное доменное имя доверенного сервера.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-789">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-790">msRTCSIP — Трустедсерверверсион</span><span class="sxs-lookup"><span data-stu-id="2cc5d-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-791">Этот атрибут указывает номер версии сервера в списке доверенных серверов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="2cc5d-792">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="2cc5d-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="2cc5d-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2cc5d-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2cc5d-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2cc5d-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc5d-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-799">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-800">msRTCSIP — Трустедсервицефлагс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-801">Этот атрибут определяет параметры, доступные для доверенной службы.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-802">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-803">msRTCSIP — Трустедсервицелинкс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-804">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен, который ссылается на доверенный объект службы, например службу проверки подлинности при ретрансляции мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="2cc5d-805">Служба проверки подлинности мультимедиа-ретрансляции (которая физически размещена на пограничном сервере, на которой работает служба аудио-и видеоконференций) должна быть связана с пулом для поддержки аудио сценариев для удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="2cc5d-806">Обратная ссылка: <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-807">Объединенных</span><span class="sxs-lookup"><span data-stu-id="2cc5d-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-808">msRTCSIP — Трустедсервицепорт</span><span class="sxs-lookup"><span data-stu-id="2cc5d-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-809">Этот атрибут представляет целое значение, которое определяет номера порта, используемого для подключения к службе GRUU.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-810">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-811">msRTCSIP — Трустедсервицетипе</span><span class="sxs-lookup"><span data-stu-id="2cc5d-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-812">Этот строковый атрибут указывает тип представляемой службы GRUU.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="2cc5d-813">Допустимые типы службы GRUU:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="2cc5d-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-815">Шлюз</span><span class="sxs-lookup"><span data-stu-id="2cc5d-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-816">Media Relay Authentication Service (MRAS)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-817">косм</span><span class="sxs-lookup"><span data-stu-id="2cc5d-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="2cc5d-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-819">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-820">msRTCSIP — Трустедвебкомпонентссервердата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-821">Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-822">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-823">msRTCSIP — Трустедвебкомпонентссерверфкдн</span><span class="sxs-lookup"><span data-stu-id="2cc5d-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-824">Этот атрибут представляет собой строковое значение, содержащее полное доменное имя служб IIS, на котором запущены веб-службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="2cc5d-825">Этот атрибут поддерживает только одно значение.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-825">This is a single-valued attribute.</span></span> <span data-ttu-id="2cc5d-826">Максимальная длина каждого сегмента 63 символа, а максимальная длина всего полного доменного имени 255 символов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-827">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-828">msRTCSIP-UCFlags (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p162">Этот атрибут определяет различные параметры объединенных коммуникаций, которые включены глобально для всех пользователей или контактных объектов. Этот атрибут представляет целочисленную битовую маску. Каждому параметру соответствует определенный бит.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="2cc5d-832">Допустимые значения и соответствующие биты:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-833">4: UsePerUserUCPolicy (2 бит)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="2cc5d-834">Если этот бит задан, политика объединенных коммуникаций определяется для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-835">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-836">msRTCSIP-UCPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-837">Этот атрибут, который может содержать только одно значение, содержит различающееся имя политики объединенных коммуникаций, заданной для этого пользователя администратором.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-838">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-839">msRTCSIP-UserDomainList (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p163">Этот атрибут предоставляет список всех доменов леса, содержащих пользователей, которые поддерживают SIP. По умолчанию этот атрибут содержит пустой список, который указывает, что все домены леса поддерживают SIP.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="2cc5d-842">Допустимые значения — строки, представляющие имена отдельных доменов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-843">Новые средства Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="2cc5d-844">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-845">msRTCSIP — UserEnabled</span><span class="sxs-lookup"><span data-stu-id="2cc5d-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-846">Этот атрибут определяет, включен ли в данный момент пользователь для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-847">msRTCSIP — Усерекстенсион</span><span class="sxs-lookup"><span data-stu-id="2cc5d-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-848">Этот атрибут, поддерживающий несколько значений, содержит список пар "имя — значение" в формате " &quot; имя = значение". &quot; Этот атрибут помечен для репликации глобального каталога.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-849">Новые средства Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="2cc5d-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-850">msRTCSIP — Усерлокатионпрофиле</span><span class="sxs-lookup"><span data-stu-id="2cc5d-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-851">Этот атрибут содержит различающееся имя, которое указывает на объект профиля местоположения.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-852">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-853">msRTCSIP — УсерполиЦиес</span><span class="sxs-lookup"><span data-stu-id="2cc5d-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-854">Этот атрибут используется для хранения пар "имя=значение" для политик пользователей.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-855">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-856">msRTCSIP — UserPolicy</span><span class="sxs-lookup"><span data-stu-id="2cc5d-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p164">Этот атрибут, поддерживающий несколько значений, содержит список различающихся имен с двоичными (DN_WITH_BINARY) указателями на глобальные политики пользователей разных типов. Двоичные указатели указывают тип политики, на которую указывает часть различающегося имени.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="2cc5d-859">Допустимые двоичные значения:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-860">0x00000001: политика собрания</span><span class="sxs-lookup"><span data-stu-id="2cc5d-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-861">0x00000002: политика объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="2cc5d-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-862">0x00000005: политика присутствия</span><span class="sxs-lookup"><span data-stu-id="2cc5d-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-863">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-864">msRTCSIP — Усерраутингграупид</span><span class="sxs-lookup"><span data-stu-id="2cc5d-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p165">Этот атрибут содержит ИД группы маршрутизации SIP. Пользователи одной группы будут регистрироваться на одном сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-867">Новые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-868">msRTCSIP — Вебкомпонентсдата</span><span class="sxs-lookup"><span data-stu-id="2cc5d-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p166">Этот атрибут поддерживает несколько значений. Этот атрибут зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-871">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-872">msRTCSIP — Вебкомпонентспуладдресс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-873">Этот атрибут, поддерживающий одно значение, указывает на пул или сервер Standard Edition, к которым принадлежат веб-компоненты.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="2cc5d-874">Прямая ссылка: <strong>ИД ссылки 11028</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="2cc5d-875">Обратная ссылка: <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-876">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-877">msRTCSIP — Вебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="2cc5d-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-p167">Этот атрибут, поддерживающий несколько значений, представляет список различающихся имен. Атрибут содержит список всех веб-серверов, связанных с этим пулом.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="2cc5d-880">Обратная ссылка: <strong>ИД ссылки 11029</strong></span><span class="sxs-lookup"><span data-stu-id="2cc5d-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="2cc5d-881">Обратная ссылка: <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-882">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-883">msRTCSIP-WMIInstanceId (устаревший)</span><span class="sxs-lookup"><span data-stu-id="2cc5d-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2cc5d-884">Новые средства Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="2cc5d-885">Устаревшие данные в Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="2cc5d-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-887">Существующий атрибут Active Directory используется службами телефонии для указания списка альтернативных TCP/IP-адресов телефона.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-888">Новый атрибут в ОС Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-889">фонеоффицеосер</span><span class="sxs-lookup"><span data-stu-id="2cc5d-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-890">Этот существующий атрибут Active Directory используется компонентами голосовой связи в Lync Server только для объектов Contact, в целях маршрутизации вызовов для автосекретаря единой системы обмена сообщениями и номеров абонентского доступа.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="2cc5d-891">В этом атрибуте, поддерживающем несколько значений, хранится адрес для переадресации вызовов.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="2cc5d-892">Эта учетная запись создана специально для доступа к автосекретарю и подписчику.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="2cc5d-893">Администраторы не должны изменять атрибуты этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-894">Новый атрибут в ОС Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cc5d-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2cc5d-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-896">Этот существующий атрибут Active Directory, поддерживающий несколько значений, является частью базовой схемы Active Directory, представленной в Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="2cc5d-897">Этот атрибут содержит различные адреса X400, X500 и SMTP электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="2cc5d-898">В Live Communications Server 2003 и более поздних версий URI пользователя SIP добавляется в этот список с помощью &quot; тега SIP: &quot; .</span><span class="sxs-lookup"><span data-stu-id="2cc5d-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="2cc5d-899">Этот атрибут используется для поиска SIP URI пользователя следующими приложениями:</span><span class="sxs-lookup"><span data-stu-id="2cc5d-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cc5d-900">Клиент обмена сообщениями и совместной работы Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="2cc5d-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="2cc5d-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="2cc5d-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2cc5d-902">Новый атрибут в ОС Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cc5d-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="2cc5d-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-904">Этот существующий атрибут Active Directory содержит телефонный номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="2cc5d-905">Новый атрибут в ОС Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="2cc5d-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


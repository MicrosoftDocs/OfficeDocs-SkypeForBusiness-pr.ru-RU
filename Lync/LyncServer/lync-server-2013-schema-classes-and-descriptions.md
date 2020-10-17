---
title: 'Lync Server 2013: классы и описания схемы'
description: 'Lync Server 2013: классы и описания схемы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557105"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="947f9-103">Классы и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="947f9-103">Schema classes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="947f9-104">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="947f9-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="947f9-105">В этом разделе описываются все классы схемы, используемые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="947f9-105">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="947f9-106">Классы схемы и описания</span><span class="sxs-lookup"><span data-stu-id="947f9-106">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="947f9-107">Класс</span><span class="sxs-lookup"><span data-stu-id="947f9-107">Class</span></span></th>
<th><span data-ttu-id="947f9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="947f9-108">Description</span></span></th>
<th><span data-ttu-id="947f9-109">Comments</span><span class="sxs-lookup"><span data-stu-id="947f9-109">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="947f9-110">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="947f9-110">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="947f9-111">Получатель электронной почты единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="947f9-111">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="947f9-112">Этот вспомогательный класс предоставляется совместно с единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="947f9-112">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-113">msRTCSIP — Аппликатионконтактс</span><span class="sxs-lookup"><span data-stu-id="947f9-113">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="947f9-114">Этот класс является контейнером для нескольких контактов приложения и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-114">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-115">Новые данные в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-115">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-116">msRTCSIP — ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="947f9-116">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="947f9-117">Этот класс размещает запись точки управления службой для экземпляра служб Unified Communications Application Services (UCAS).</span><span class="sxs-lookup"><span data-stu-id="947f9-117">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="947f9-118">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-118">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-119">msRTCSIP — Аппликатионсерверсервице</span><span class="sxs-lookup"><span data-stu-id="947f9-119">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="947f9-120">Этот класс предоставляет связь из определенного пула со службой приложения.</span><span class="sxs-lookup"><span data-stu-id="947f9-120">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="947f9-121">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-121">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-122">msRTCSIP — Аппликатионсерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="947f9-122">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="947f9-123">Этот вспомогательный класс в msRTCSIP – ApplicationServer содержит атрибуты, представляющие параметры для экземпляров службы приложения.</span><span class="sxs-lookup"><span data-stu-id="947f9-123">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="947f9-124">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-124">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-125">msRTCSIP-Archive (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-125">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-126">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к архивации.</span><span class="sxs-lookup"><span data-stu-id="947f9-126">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="947f9-127">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-127">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-128">msRTCSIP-ArchivingServer (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-128">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-p101">Этот класс представляет один сервер архивации обмена мгновенными сообщениями. Экземпляр этого класса создается при активации компьютера в качестве сервера архивации обмена мгновенными сообщениями, например, компьютера с установленной службой архивации обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="947f9-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="947f9-131">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-131">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-132">msRTCSIP — ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="947f9-132">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="947f9-133">Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-133">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-134">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-134">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-135">msRTCSIP — Конференцедиректори</span><span class="sxs-lookup"><span data-stu-id="947f9-135">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="947f9-136">Этот класс содержит атрибуты, представляющие параметры для конкретного каталога конференций.</span><span class="sxs-lookup"><span data-stu-id="947f9-136">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="947f9-137">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-137">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-138">msRTCSIP — Коннектионпоинт</span><span class="sxs-lookup"><span data-stu-id="947f9-138">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="947f9-139">Общая точка управления службой (SCP) для указания компьютера в качестве сервера, на котором работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947f9-139">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="947f9-140">Новые в Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-140">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-141">msRTCSIP — Дефаултквабанк</span><span class="sxs-lookup"><span data-stu-id="947f9-141">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="947f9-142">Этот вспомогательный класс содержит параметры банка Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="947f9-142">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="947f9-143">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-143">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-144">msRTCSIP — domain</span><span class="sxs-lookup"><span data-stu-id="947f9-144">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="947f9-145">Этот класс содержит атрибуты, задающие настроенные домены регистратора SIP.</span><span class="sxs-lookup"><span data-stu-id="947f9-145">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-146">msRTCSIP — Еджепрокси</span><span class="sxs-lookup"><span data-stu-id="947f9-146">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="947f9-147">Этот контейнер класса представляет одну службу пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="947f9-147">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="947f9-148">Так как служба пограничного доступа разворачивается в сети периметра, а клиенты обычно не разрешают доменным службам Active Directory доступ из сети периметра, экземпляры пограничной службы доступа не присоединяются к сети Active Directory интрасети.</span><span class="sxs-lookup"><span data-stu-id="947f9-148">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="947f9-149">Следовательно, прокси-серверы доступа не регистрируются в AD DS автоматически.</span><span class="sxs-lookup"><span data-stu-id="947f9-149">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="947f9-150">Администратор должен вручную настроить существование каждого экземпляра службы пограничного доступа в AD DS.</span><span class="sxs-lookup"><span data-stu-id="947f9-150">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-151">msRTCSIP — Ентерприсемкусеттингс</span><span class="sxs-lookup"><span data-stu-id="947f9-151">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="947f9-152">Этот дополнительный к msRTCSIP-MCU класс содержит атрибуты, представляющие параметры для серверов конференций.</span><span class="sxs-lookup"><span data-stu-id="947f9-152">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="947f9-153">Новые данные в Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-153">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-154">msRTCSIP — Ентерприсемедиатионсерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="947f9-154">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="947f9-155">Этот дополнительный к msRTCSIP-MediationServer класс содержит атрибуты, представляющие параметры для серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="947f9-155">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="947f9-156">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-156">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-157">msRTCSIP — Ентерприсесерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="947f9-157">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="947f9-158">Этот дополнительный к msRTCSIP-Server класс содержит атрибуты, представляющие параметры для серверов SIP.</span><span class="sxs-lookup"><span data-stu-id="947f9-158">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-159">msRTCSIP — Федерация</span><span class="sxs-lookup"><span data-stu-id="947f9-159">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="947f9-160">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к федерации.</span><span class="sxs-lookup"><span data-stu-id="947f9-160">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-161">msRTCSIP — Globalcontainer класс</span><span class="sxs-lookup"><span data-stu-id="947f9-161">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="947f9-162">В этом классе хранятся все параметры, применяемые во время развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947f9-162">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-163">msRTCSIP-GlobalUserPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-163">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-164">Этот класс представляет одну политику собраний Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="947f9-164">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="947f9-165">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-165">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-166">msRTCSIP — Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="947f9-166">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="947f9-167">Локальный объект параметров глобальной топологии.</span><span class="sxs-lookup"><span data-stu-id="947f9-167">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="947f9-168">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-168">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-169">msRTCSIP — Глобалтопологисеттингс</span><span class="sxs-lookup"><span data-stu-id="947f9-169">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="947f9-170">Контейнер для хранения объектов параметров глобальной топологии.</span><span class="sxs-lookup"><span data-stu-id="947f9-170">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="947f9-171">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-171">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-172">msRTCSIP — Локалнормализатион</span><span class="sxs-lookup"><span data-stu-id="947f9-172">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="947f9-173">Этот класс является контейнером, представляющим экземпляр правила нормализации местонахождения.</span><span class="sxs-lookup"><span data-stu-id="947f9-173">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-174">msRTCSIP — Локатионконтактмаппинг</span><span class="sxs-lookup"><span data-stu-id="947f9-174">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="947f9-175">Этот класс создается приложением-помощником по конференц-связи и содержит атрибуты, используемые для категоризации телефонных номеров конференций по регионам.</span><span class="sxs-lookup"><span data-stu-id="947f9-175">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="947f9-176">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-176">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-177">msRTCSIP — Локатионконтактмаппингс</span><span class="sxs-lookup"><span data-stu-id="947f9-177">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="947f9-178">Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местонахождений и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-178">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-179">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-179">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-180">msRTCSIP — LocationProfile</span><span class="sxs-lookup"><span data-stu-id="947f9-180">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="947f9-181">Этот класс является контейнером, представляющим конкретный профиль местонахождения.</span><span class="sxs-lookup"><span data-stu-id="947f9-181">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-182">msRTCSIP-LocationProfiles (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-182">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-183">Этот класс является контейнером для нескольких профилей местонахождений и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-183">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-184">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-184">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-185">msRTCSIP-LocalNormalizations (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-185">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-186">Этот класс является контейнером для нескольких локальных правил нормализации и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-186">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-187">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-187">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-188">msRTCSIP — MCU</span><span class="sxs-lookup"><span data-stu-id="947f9-188">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="947f9-189">Этот класс представляет один сервер конференций.</span><span class="sxs-lookup"><span data-stu-id="947f9-189">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="947f9-190">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-190">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-191">msRTCSIP — Мкуфакториес</span><span class="sxs-lookup"><span data-stu-id="947f9-191">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="947f9-192">Этот класс размещает несколько классов msRTCSIP-MCUFactory и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-192">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-193">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-193">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-194">msRTCSIP — MCUFactory</span><span class="sxs-lookup"><span data-stu-id="947f9-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="947f9-p103">Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа среды передачи. Экземпляр этого класса создается, когда активируется первый сервер конференций для этого конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="947f9-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="947f9-197">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-197">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-198">msRTCSIP — Мкуфакторисервице</span><span class="sxs-lookup"><span data-stu-id="947f9-198">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="947f9-199">Этот класс предоставляет связь конкретного пула с его фабрикой серверов конференций.</span><span class="sxs-lookup"><span data-stu-id="947f9-199">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="947f9-200">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-200">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-201">msRTCSIP — MediationServer</span><span class="sxs-lookup"><span data-stu-id="947f9-201">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="947f9-202">В этом классе содержится запись точки управления службой для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="947f9-202">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="947f9-203">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-203">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-204">msRTCSIP-Meeting (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-204">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-205">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие настраиваемые параметры собрания.</span><span class="sxs-lookup"><span data-stu-id="947f9-205">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="947f9-206">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-206">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-207">msRTCSIP — мобильность</span><span class="sxs-lookup"><span data-stu-id="947f9-207">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="947f9-208">Контейнер, хранящий глобальные параметры мобильности.</span><span class="sxs-lookup"><span data-stu-id="947f9-208">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-209">msRTCSIP — Мониторингсервер</span><span class="sxs-lookup"><span data-stu-id="947f9-209">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="947f9-210">Этот класс содержит атрибуты, представляющие параметры для одного сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="947f9-210">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="947f9-211">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="947f9-211">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-212">msRTCSIP-PhoneRoute (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-212">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-p104">Этот класс является контейнером, представляющим экземпляр наименее затратного маршрута к шлюзу или ряду шлюзов. Данная информация используется всеми пулами или серверами Enterprise, на которых установлен выпуск Standard Edition, для маршрутизации исходящих вызовов в телефонную сеть общего пользования (ТСОП) по принципу наименьшей стоимости.</span><span class="sxs-lookup"><span data-stu-id="947f9-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="947f9-215">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-215">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-216">msRTCSIP-PhoneRoutes (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-216">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-217">Этот класс является контейнером для нескольких наименее затратных маршрутов и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-217">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-218">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-218">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-219">msRTCSIP-Policies (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-219">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-220">Этот класс содержит несколько классов политики Lync Server и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="947f9-220">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-221">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-221">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-222">msRTCSIP — пул</span><span class="sxs-lookup"><span data-stu-id="947f9-222">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="947f9-223">Этот класс представляет один пул Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947f9-223">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-224">msRTCSIP — пулы</span><span class="sxs-lookup"><span data-stu-id="947f9-224">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="947f9-225">Этот класс содержит несколько пулов Lync Server и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-225">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-226">msRTCSIP — Пулсервице</span><span class="sxs-lookup"><span data-stu-id="947f9-226">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="947f9-p105">Этот класс представляет точку управления службой пула. Атрибут msRTCSIP-PrimaryHomeServer пользователей, размещенных в пуле, указывает на экземпляр данного класса.</span><span class="sxs-lookup"><span data-stu-id="947f9-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-229">msRTCSIP — присутствие</span><span class="sxs-lookup"><span data-stu-id="947f9-229">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="947f9-230">Контейнер, хранящий глобальные параметры присутствия.</span><span class="sxs-lookup"><span data-stu-id="947f9-230">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-231">msRTCSIP — регистратор</span><span class="sxs-lookup"><span data-stu-id="947f9-231">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="947f9-232">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие пользовательские параметры, которые поддерживаются серверами регистратора SIP.</span><span class="sxs-lookup"><span data-stu-id="947f9-232">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-233">msRTCSIP-RouteUsage (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-233">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-p106">Этот класс является контейнером, представляющим экземпляр использования телефонных маршрутов. Класс использований телефонных маршрутов состоит из поля атрибута и поля описания. Поле атрибута определяет тип использования. В поле описания администраторы могут ввести описание использования для этого атрибута в телефонном маршруте.</span><span class="sxs-lookup"><span data-stu-id="947f9-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="947f9-238">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-238">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-239">msRTCSIP-RouteUsages (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-239">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-240">Этот класс содержит несколько экземпляров класса msRTCSIP-RouteUsage и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="947f9-240">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-241">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-242">msRTCSIP — Поиск</span><span class="sxs-lookup"><span data-stu-id="947f9-242">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="947f9-243">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, которые ограничивают область результатов поиска и управляют ею.</span><span class="sxs-lookup"><span data-stu-id="947f9-243">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-244">msRTCSIP — сервер</span><span class="sxs-lookup"><span data-stu-id="947f9-244">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="947f9-245">Этот класс представляет один сервер, на котором работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947f9-245">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-246">msRTCSIP — служба</span><span class="sxs-lookup"><span data-stu-id="947f9-246">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="947f9-247">Этот класс содержит контейнер глобальных параметров и объекты класса msRTCSIP-Domain.</span><span class="sxs-lookup"><span data-stu-id="947f9-247">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-248">msRTCSIP — Трустедмку</span><span class="sxs-lookup"><span data-stu-id="947f9-248">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="947f9-249">Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="947f9-249">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="947f9-250">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-250">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-251">msRTCSIP — Трустедмкус</span><span class="sxs-lookup"><span data-stu-id="947f9-251">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="947f9-252">Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedMCU и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="947f9-252">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-253">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-253">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-254">msRTCSIP — Трустедпроксиес</span><span class="sxs-lookup"><span data-stu-id="947f9-254">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="947f9-255">Этот класс содержит несколько экземпляров классов msRTCSIP-TrustedProxy и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="947f9-255">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-256">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-256">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-257">msRTCSIP — Трустедпрокси</span><span class="sxs-lookup"><span data-stu-id="947f9-257">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="947f9-p107">Этот класс является контейнером, представляющим сервер, на котором работает прокси-сервер. Экземпляр данного класса создается при активации нового прокси-сервера на компьютере, подключенном к AD DS.</span><span class="sxs-lookup"><span data-stu-id="947f9-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="947f9-260">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-260">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-261">msRTCSIP — TrustedServer</span><span class="sxs-lookup"><span data-stu-id="947f9-261">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="947f9-262">Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера.</span><span class="sxs-lookup"><span data-stu-id="947f9-262">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-263">msRTCSIP — Трустедсервице</span><span class="sxs-lookup"><span data-stu-id="947f9-263">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="947f9-264">Этот класс является контейнером, представляющим доверенную службу, которая маршрутизируется с помощью адреса GRUU.</span><span class="sxs-lookup"><span data-stu-id="947f9-264">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="947f9-265">Экземпляр этого класса создается при активации нового сервера, который является доверенным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="947f9-265">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="947f9-266">Этот доверенный сервер должен быть подключен к домену Active Directory.</span><span class="sxs-lookup"><span data-stu-id="947f9-266">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="947f9-267">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-267">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-268">msRTCSIP — Трустедсервицес</span><span class="sxs-lookup"><span data-stu-id="947f9-268">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="947f9-269">Этот класс является контейнером для нескольких серверов GRUU и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="947f9-269">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-270">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-270">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-271">msRTCSIP — Трустедвебкомпонентссервер</span><span class="sxs-lookup"><span data-stu-id="947f9-271">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="947f9-272">Этот класс содержит атрибуты, которые представляют параметры для доверенного веб-компонента.</span><span class="sxs-lookup"><span data-stu-id="947f9-272">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="947f9-273">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-273">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-274">msRTCSIP — Трустедвебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="947f9-274">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="947f9-275">Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedWebComponentServer и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="947f9-275">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="947f9-276">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-276">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-277">msRTCSIP-UnifiedCommunications (устаревший)</span><span class="sxs-lookup"><span data-stu-id="947f9-277">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="947f9-278">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, относящиеся к объединенным коммуникациям.</span><span class="sxs-lookup"><span data-stu-id="947f9-278">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="947f9-279">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="947f9-279">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-280">msRTCSIP — компоненты</span><span class="sxs-lookup"><span data-stu-id="947f9-280">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="947f9-p109">Этот класс содержит точку управления службой для сервера IIS. Он определяет сервер как сервер веб-компонентов.</span><span class="sxs-lookup"><span data-stu-id="947f9-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="947f9-283">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-283">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947f9-284">msRTCSIP — Вебкомпонентссервице</span><span class="sxs-lookup"><span data-stu-id="947f9-284">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="947f9-285">Этот класс предоставляет связь конкретного пула с веб-компонентом, который будет использовать этот пул.</span><span class="sxs-lookup"><span data-stu-id="947f9-285">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="947f9-286">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-286">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947f9-287">msRTCSIP — Вебкомпонентсеттингс</span><span class="sxs-lookup"><span data-stu-id="947f9-287">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="947f9-288">Этот дополнительный к msRTCSIP-WebComponents класс содержит атрибуты, представляющие параметры для веб-компонентов.</span><span class="sxs-lookup"><span data-stu-id="947f9-288">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="947f9-289">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="947f9-289">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


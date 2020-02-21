---
title: 'Lync Server 2013: классы и описания схемы'
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
ms.openlocfilehash: 4e7dd3deff8a64b1dd153a9717d0ce2be2f28de8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="1b617-102">Классы и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b617-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b617-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="1b617-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="1b617-104">В этом разделе описываются все классы схемы, используемые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b617-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="1b617-105">Классы схемы и описания</span><span class="sxs-lookup"><span data-stu-id="1b617-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b617-106">Класс</span><span class="sxs-lookup"><span data-stu-id="1b617-106">Class</span></span></th>
<th><span data-ttu-id="1b617-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1b617-107">Description</span></span></th>
<th><span data-ttu-id="1b617-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1b617-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b617-109">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="1b617-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="1b617-110">Получатель электронной почты единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b617-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="1b617-111">Этот вспомогательный класс предоставляется совместно с единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b617-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-112">msRTCSIP — Аппликатионконтактс</span><span class="sxs-lookup"><span data-stu-id="1b617-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="1b617-113">Этот класс является контейнером для нескольких контактов приложения и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-114">Новые данные в Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-115">msRTCSIP — ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="1b617-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="1b617-116">Этот класс размещает запись точки управления службой для экземпляра служб Unified Communications Application Services (UCAS).</span><span class="sxs-lookup"><span data-stu-id="1b617-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="1b617-117">Новое в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-118">msRTCSIP — Аппликатионсерверсервице</span><span class="sxs-lookup"><span data-stu-id="1b617-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="1b617-119">Этот класс предоставляет связь из определенного пула со службой приложения.</span><span class="sxs-lookup"><span data-stu-id="1b617-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="1b617-120">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-121">msRTCSIP — Аппликатионсерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="1b617-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="1b617-122">Этот вспомогательный класс в msRTCSIP – ApplicationServer содержит атрибуты, представляющие параметры для экземпляров службы приложения.</span><span class="sxs-lookup"><span data-stu-id="1b617-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="1b617-123">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-124">msRTCSIP-Archive (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-125">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к архивации.</span><span class="sxs-lookup"><span data-stu-id="1b617-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="1b617-126">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-127">msRTCSIP-ArchivingServer (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-p101">Этот класс представляет один сервер архивации обмена мгновенными сообщениями. Экземпляр этого класса создается при активации компьютера в качестве сервера архивации обмена мгновенными сообщениями, например, компьютера с установленной службой архивации обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1b617-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="1b617-130">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-131">msRTCSIP — ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="1b617-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="1b617-132">Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-133">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-134">msRTCSIP — Конференцедиректори</span><span class="sxs-lookup"><span data-stu-id="1b617-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="1b617-135">Этот класс содержит атрибуты, представляющие параметры для конкретного каталога конференций.</span><span class="sxs-lookup"><span data-stu-id="1b617-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="1b617-136">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-137">msRTCSIP — Коннектионпоинт</span><span class="sxs-lookup"><span data-stu-id="1b617-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="1b617-138">Общая точка управления службой (SCP) для указания компьютера в качестве сервера, на котором работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b617-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="1b617-139">Новые в Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-140">msRTCSIP — Дефаултквабанк</span><span class="sxs-lookup"><span data-stu-id="1b617-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="1b617-141">Этот вспомогательный класс содержит параметры банка Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="1b617-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="1b617-142">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-143">msRTCSIP — domain</span><span class="sxs-lookup"><span data-stu-id="1b617-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="1b617-144">Этот класс содержит атрибуты, задающие настроенные домены регистратора SIP.</span><span class="sxs-lookup"><span data-stu-id="1b617-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-145">msRTCSIP — Еджепрокси</span><span class="sxs-lookup"><span data-stu-id="1b617-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="1b617-146">Этот контейнер класса представляет одну службу пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="1b617-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="1b617-147">Так как служба пограничного доступа разворачивается в сети периметра, а клиенты обычно не разрешают доменным службам Active Directory доступ из сети периметра, экземпляры пограничной службы доступа не присоединяются к сети Active Directory интрасети.</span><span class="sxs-lookup"><span data-stu-id="1b617-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="1b617-148">Следовательно, прокси-серверы доступа не регистрируются в AD DS автоматически.</span><span class="sxs-lookup"><span data-stu-id="1b617-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="1b617-149">Администратор должен вручную настроить существование каждого экземпляра службы пограничного доступа в AD DS.</span><span class="sxs-lookup"><span data-stu-id="1b617-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-150">msRTCSIP — Ентерприсемкусеттингс</span><span class="sxs-lookup"><span data-stu-id="1b617-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="1b617-151">Этот дополнительный к msRTCSIP-MCU класс содержит атрибуты, представляющие параметры для серверов конференций.</span><span class="sxs-lookup"><span data-stu-id="1b617-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="1b617-152">Новые данные в Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-153">msRTCSIP — Ентерприсемедиатионсерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="1b617-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="1b617-154">Этот дополнительный к msRTCSIP-MediationServer класс содержит атрибуты, представляющие параметры для серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="1b617-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="1b617-155">Новые в Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-156">msRTCSIP — Ентерприсесерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="1b617-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="1b617-157">Этот дополнительный к msRTCSIP-Server класс содержит атрибуты, представляющие параметры для серверов SIP.</span><span class="sxs-lookup"><span data-stu-id="1b617-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-158">msRTCSIP — Федерация</span><span class="sxs-lookup"><span data-stu-id="1b617-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="1b617-159">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к федерации.</span><span class="sxs-lookup"><span data-stu-id="1b617-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-160">msRTCSIP — Globalcontainer класс</span><span class="sxs-lookup"><span data-stu-id="1b617-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="1b617-161">В этом классе хранятся все параметры, применяемые во время развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b617-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-162">msRTCSIP-GlobalUserPolicy (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-163">Этот класс представляет одну политику собраний Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="1b617-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="1b617-164">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-165">msRTCSIP — Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="1b617-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="1b617-166">Локальный объект параметров глобальной топологии.</span><span class="sxs-lookup"><span data-stu-id="1b617-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="1b617-167">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-168">msRTCSIP — Глобалтопологисеттингс</span><span class="sxs-lookup"><span data-stu-id="1b617-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="1b617-169">Контейнер для хранения объектов параметров глобальной топологии.</span><span class="sxs-lookup"><span data-stu-id="1b617-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="1b617-170">Новые в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-171">msRTCSIP — Локалнормализатион</span><span class="sxs-lookup"><span data-stu-id="1b617-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="1b617-172">Этот класс является контейнером, представляющим экземпляр правила нормализации местонахождения.</span><span class="sxs-lookup"><span data-stu-id="1b617-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-173">msRTCSIP — Локатионконтактмаппинг</span><span class="sxs-lookup"><span data-stu-id="1b617-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="1b617-174">Этот класс создается приложением-помощником по конференц-связи и содержит атрибуты, используемые для категоризации телефонных номеров конференций по регионам.</span><span class="sxs-lookup"><span data-stu-id="1b617-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="1b617-175">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-176">msRTCSIP — Локатионконтактмаппингс</span><span class="sxs-lookup"><span data-stu-id="1b617-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="1b617-177">Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местонахождений и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-178">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-179">msRTCSIP — LocationProfile</span><span class="sxs-lookup"><span data-stu-id="1b617-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="1b617-180">Этот класс является контейнером, представляющим конкретный профиль местонахождения.</span><span class="sxs-lookup"><span data-stu-id="1b617-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-181">msRTCSIP-LocationProfiles (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-182">Этот класс является контейнером для нескольких профилей местонахождений и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-183">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-184">msRTCSIP-LocalNormalizations (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-185">Этот класс является контейнером для нескольких локальных правил нормализации и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-186">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-187">msRTCSIP — MCU</span><span class="sxs-lookup"><span data-stu-id="1b617-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="1b617-188">Этот класс представляет один сервер конференций.</span><span class="sxs-lookup"><span data-stu-id="1b617-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="1b617-189">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-190">msRTCSIP — Мкуфакториес</span><span class="sxs-lookup"><span data-stu-id="1b617-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="1b617-191">Этот класс размещает несколько классов msRTCSIP-MCUFactory и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-192">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-193">msRTCSIP — MCUFactory</span><span class="sxs-lookup"><span data-stu-id="1b617-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="1b617-p103">Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа среды передачи. Экземпляр этого класса создается, когда активируется первый сервер конференций для этого конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="1b617-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="1b617-196">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-197">msRTCSIP — Мкуфакторисервице</span><span class="sxs-lookup"><span data-stu-id="1b617-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="1b617-198">Этот класс предоставляет связь конкретного пула с его фабрикой серверов конференций.</span><span class="sxs-lookup"><span data-stu-id="1b617-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="1b617-199">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-200">msRTCSIP — MediationServer</span><span class="sxs-lookup"><span data-stu-id="1b617-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="1b617-201">В этом классе содержится запись точки управления службой для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="1b617-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="1b617-202">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-203">msRTCSIP-Meeting (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-204">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие настраиваемые параметры собрания.</span><span class="sxs-lookup"><span data-stu-id="1b617-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="1b617-205">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-206">msRTCSIP — мобильность</span><span class="sxs-lookup"><span data-stu-id="1b617-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="1b617-207">Контейнер, хранящий глобальные параметры мобильности.</span><span class="sxs-lookup"><span data-stu-id="1b617-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-208">msRTCSIP — Мониторингсервер</span><span class="sxs-lookup"><span data-stu-id="1b617-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="1b617-209">Этот класс содержит атрибуты, представляющие параметры для одного сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="1b617-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="1b617-210">Новый сервер Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b617-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-211">msRTCSIP-PhoneRoute (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-p104">Этот класс является контейнером, представляющим экземпляр наименее затратного маршрута к шлюзу или ряду шлюзов. Данная информация используется всеми пулами или серверами Enterprise, на которых установлен выпуск Standard Edition, для маршрутизации исходящих вызовов в телефонную сеть общего пользования (ТСОП) по принципу наименьшей стоимости.</span><span class="sxs-lookup"><span data-stu-id="1b617-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="1b617-214">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-215">msRTCSIP-PhoneRoutes (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-216">Этот класс является контейнером для нескольких наименее затратных маршрутов и не содержит какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-217">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-218">msRTCSIP-Policies (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-219">Этот класс содержит несколько классов политики Lync Server и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1b617-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-220">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-221">msRTCSIP — пул</span><span class="sxs-lookup"><span data-stu-id="1b617-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="1b617-222">Этот класс представляет один пул Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b617-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-223">msRTCSIP — пулы</span><span class="sxs-lookup"><span data-stu-id="1b617-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="1b617-224">Этот класс содержит несколько пулов Lync Server и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-225">msRTCSIP — Пулсервице</span><span class="sxs-lookup"><span data-stu-id="1b617-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="1b617-p105">Этот класс представляет точку управления службой пула. Атрибут msRTCSIP-PrimaryHomeServer пользователей, размещенных в пуле, указывает на экземпляр данного класса.</span><span class="sxs-lookup"><span data-stu-id="1b617-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-228">msRTCSIP — присутствие</span><span class="sxs-lookup"><span data-stu-id="1b617-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="1b617-229">Контейнер, хранящий глобальные параметры присутствия.</span><span class="sxs-lookup"><span data-stu-id="1b617-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-230">msRTCSIP — регистратор</span><span class="sxs-lookup"><span data-stu-id="1b617-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="1b617-231">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие пользовательские параметры, которые поддерживаются серверами регистратора SIP.</span><span class="sxs-lookup"><span data-stu-id="1b617-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-232">msRTCSIP-RouteUsage (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-p106">Этот класс является контейнером, представляющим экземпляр использования телефонных маршрутов. Класс использований телефонных маршрутов состоит из поля атрибута и поля описания. Поле атрибута определяет тип использования. В поле описания администраторы могут ввести описание использования для этого атрибута в телефонном маршруте.</span><span class="sxs-lookup"><span data-stu-id="1b617-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="1b617-237">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-238">msRTCSIP-RouteUsages (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-239">Этот класс содержит несколько экземпляров класса msRTCSIP-RouteUsage и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1b617-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-240">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-241">msRTCSIP — Поиск</span><span class="sxs-lookup"><span data-stu-id="1b617-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="1b617-242">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, которые ограничивают область результатов поиска и управляют ею.</span><span class="sxs-lookup"><span data-stu-id="1b617-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-243">msRTCSIP — сервер</span><span class="sxs-lookup"><span data-stu-id="1b617-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="1b617-244">Этот класс представляет один сервер, на котором работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b617-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-245">msRTCSIP — служба</span><span class="sxs-lookup"><span data-stu-id="1b617-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="1b617-246">Этот класс содержит контейнер глобальных параметров и объекты класса msRTCSIP-Domain.</span><span class="sxs-lookup"><span data-stu-id="1b617-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-247">msRTCSIP — Трустедмку</span><span class="sxs-lookup"><span data-stu-id="1b617-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="1b617-248">Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="1b617-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="1b617-249">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-250">msRTCSIP — Трустедмкус</span><span class="sxs-lookup"><span data-stu-id="1b617-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="1b617-251">Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedMCU и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1b617-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-252">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-253">msRTCSIP — Трустедпроксиес</span><span class="sxs-lookup"><span data-stu-id="1b617-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="1b617-254">Этот класс содержит несколько экземпляров классов msRTCSIP-TrustedProxy и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1b617-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-255">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-256">msRTCSIP — Трустедпрокси</span><span class="sxs-lookup"><span data-stu-id="1b617-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="1b617-p107">Этот класс является контейнером, представляющим сервер, на котором работает прокси-сервер. Экземпляр данного класса создается при активации нового прокси-сервера на компьютере, подключенном к AD DS.</span><span class="sxs-lookup"><span data-stu-id="1b617-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="1b617-259">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-260">msRTCSIP — TrustedServer</span><span class="sxs-lookup"><span data-stu-id="1b617-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="1b617-261">Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера.</span><span class="sxs-lookup"><span data-stu-id="1b617-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-262">msRTCSIP — Трустедсервице</span><span class="sxs-lookup"><span data-stu-id="1b617-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="1b617-263">Этот класс является контейнером, представляющим доверенную службу, которая маршрутизируется с помощью адреса GRUU.</span><span class="sxs-lookup"><span data-stu-id="1b617-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="1b617-264">Экземпляр этого класса создается при активации нового сервера, который является доверенным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b617-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="1b617-265">Этот доверенный сервер должен быть подключен к домену Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1b617-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="1b617-266">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-267">msRTCSIP — Трустедсервицес</span><span class="sxs-lookup"><span data-stu-id="1b617-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="1b617-268">Этот класс является контейнером для нескольких серверов GRUU и не содержит никакие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b617-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-269">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-270">msRTCSIP — Трустедвебкомпонентссервер</span><span class="sxs-lookup"><span data-stu-id="1b617-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="1b617-271">Этот класс содержит атрибуты, которые представляют параметры для доверенного веб-компонента.</span><span class="sxs-lookup"><span data-stu-id="1b617-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="1b617-272">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-273">msRTCSIP — Трустедвебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="1b617-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="1b617-274">Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedWebComponentServer и не имеет никаких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1b617-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1b617-275">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-276">msRTCSIP-UnifiedCommunications (устаревший)</span><span class="sxs-lookup"><span data-stu-id="1b617-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b617-277">Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, относящиеся к объединенным коммуникациям.</span><span class="sxs-lookup"><span data-stu-id="1b617-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="1b617-278">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b617-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-279">msRTCSIP — компоненты</span><span class="sxs-lookup"><span data-stu-id="1b617-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="1b617-p109">Этот класс содержит точку управления службой для сервера IIS. Он определяет сервер как сервер веб-компонентов.</span><span class="sxs-lookup"><span data-stu-id="1b617-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="1b617-282">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b617-283">msRTCSIP — Вебкомпонентссервице</span><span class="sxs-lookup"><span data-stu-id="1b617-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="1b617-284">Этот класс предоставляет связь конкретного пула с веб-компонентом, который будет использовать этот пул.</span><span class="sxs-lookup"><span data-stu-id="1b617-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="1b617-285">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b617-286">msRTCSIP — Вебкомпонентсеттингс</span><span class="sxs-lookup"><span data-stu-id="1b617-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="1b617-287">Этот дополнительный к msRTCSIP-WebComponents класс содержит атрибуты, представляющие параметры для веб-компонентов.</span><span class="sxs-lookup"><span data-stu-id="1b617-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="1b617-288">Новый сервер Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1b617-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


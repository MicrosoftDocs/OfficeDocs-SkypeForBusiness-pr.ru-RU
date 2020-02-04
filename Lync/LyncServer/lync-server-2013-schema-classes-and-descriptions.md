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
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="89492-102">Классы схем и описания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89492-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89492-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="89492-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="89492-104">В этом разделе описаны все классы схем, используемые в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89492-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="89492-105">Классы и описания схемы</span><span class="sxs-lookup"><span data-stu-id="89492-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89492-106">Классов</span><span class="sxs-lookup"><span data-stu-id="89492-106">Class</span></span></th>
<th><span data-ttu-id="89492-107">Описание</span><span class="sxs-lookup"><span data-stu-id="89492-107">Description</span></span></th>
<th><span data-ttu-id="89492-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="89492-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89492-109">Почта-получатель</span><span class="sxs-lookup"><span data-stu-id="89492-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="89492-110">Сообщение электронной почты в единой системе обмена сообщениями Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="89492-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="89492-111">Этот вспомогательный класс предоставляется в единой системе обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="89492-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-112">msRTCSIP-Аппликатионконтактс</span><span class="sxs-lookup"><span data-stu-id="89492-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="89492-113">Этот класс является контейнером для нескольких контактов приложения и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-114">Новые возможности Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-115">msRTCSIP-Аппликатионсервер</span><span class="sxs-lookup"><span data-stu-id="89492-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="89492-116">Этот класс содержит запись для точки управления службой для экземпляра служб единой системы обмена сообщениями (укас).</span><span class="sxs-lookup"><span data-stu-id="89492-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="89492-117">Новые возможности Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-118">msRTCSIP-Аппликатионсерверсервице</span><span class="sxs-lookup"><span data-stu-id="89492-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="89492-119">Этот класс предоставляет ассоциацию от определенного пула к его службе приложения.</span><span class="sxs-lookup"><span data-stu-id="89492-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="89492-120">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-121">msRTCSIP-Аппликатионсерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="89492-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="89492-122">Этот вспомогательный класс для msRTCSIP-Аппликатионсервер содержит атрибуты, представляющие параметры для экземпляров службы приложения.</span><span class="sxs-lookup"><span data-stu-id="89492-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="89492-123">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-124">msRTCSIP — Архив (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-125">Этот вспомогательный класс в msRTCSIP-Глобалконтаинер содержит все параметры, связанные с архивацией.</span><span class="sxs-lookup"><span data-stu-id="89492-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="89492-126">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-127">msRTCSIP-Арчивингсервер (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-128">Этот класс представляет собой один сервер архивирования для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="89492-128">This class represents a single instant messaging Archiving Server.</span></span> <span data-ttu-id="89492-129">Экземпляр этого класса создается, когда компьютер активируется в качестве сервера архивации мгновенных сообщений, например с компьютера, на котором установлена служба архивации мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="89492-129">An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="89492-130">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-131">msRTCSIP-Конференцедиректориес</span><span class="sxs-lookup"><span data-stu-id="89492-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="89492-132">Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-133">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-134">msRTCSIP-Конференцедиректори</span><span class="sxs-lookup"><span data-stu-id="89492-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="89492-135">Этот класс содержит атрибуты, представляющие параметры для определенного каталога конференций.</span><span class="sxs-lookup"><span data-stu-id="89492-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="89492-136">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-137">msRTCSIP-Коннектионпоинт</span><span class="sxs-lookup"><span data-stu-id="89492-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="89492-138">Общая точка управления службой (SCP) для указания компьютера в качестве сервера, на котором работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89492-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="89492-139">Новые возможности в Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-140">msRTCSIP-Дефаултквабанк</span><span class="sxs-lookup"><span data-stu-id="89492-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="89492-141">Этот вспомогательный класс содержит параметры банка Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="89492-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="89492-142">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-143">msRTCSIP-Domain (домен)</span><span class="sxs-lookup"><span data-stu-id="89492-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="89492-144">Этот класс содержит атрибуты, определяющие настроенные домены регистратора SIP.</span><span class="sxs-lookup"><span data-stu-id="89492-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-145">msRTCSIP-Еджепрокси</span><span class="sxs-lookup"><span data-stu-id="89492-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="89492-146">Этот контейнер класса представляет одну службу пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="89492-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="89492-147">Поскольку служба Edge Access развернута в демилитаризованной зоне, а пользователи обычно не разрешают доступ доменных служб Active Directory из сети периметра, то экземпляры службы Edge Access не присоединяются к сети Active Directory в интрасети.</span><span class="sxs-lookup"><span data-stu-id="89492-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="89492-148">Таким образом, прокси-серверы доступа не регистрируются автоматически в доменных СЛУЖБах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89492-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="89492-149">Администратор должен вручную настроить существование каждого экземпляра службы пограничного доступа в AD DS.</span><span class="sxs-lookup"><span data-stu-id="89492-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-150">msRTCSIP-Ентерприсемкусеттингс</span><span class="sxs-lookup"><span data-stu-id="89492-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="89492-151">Этот вспомогательный класс для msRTCSIP-MCU содержит атрибуты, представляющие параметры серверов конференций.</span><span class="sxs-lookup"><span data-stu-id="89492-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="89492-152">Новые возможности Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-153">msRTCSIP-Ентерприсемедиатионсерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="89492-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="89492-154">Этот вспомогательный класс для msRTCSIP-Медиатионсервер содержит атрибуты, представляющие параметры серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="89492-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="89492-155">Новые возможности Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-156">msRTCSIP-Ентерприсесерверсеттингс</span><span class="sxs-lookup"><span data-stu-id="89492-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="89492-157">Этот вспомогательный класс для msRTCSIP-Server содержит атрибуты, представляющие параметры для серверов SIP.</span><span class="sxs-lookup"><span data-stu-id="89492-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-158">msRTCSIP-Federation</span><span class="sxs-lookup"><span data-stu-id="89492-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="89492-159">Этот вспомогательный класс для msRTCSIP-Глобалконтаинер содержит все параметры, связанные с интеграцией.</span><span class="sxs-lookup"><span data-stu-id="89492-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-160">msRTCSIP-Глобалконтаинер</span><span class="sxs-lookup"><span data-stu-id="89492-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="89492-161">Этот класс содержит все параметры, которые применяются во время развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89492-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-162">msRTCSIP-Глобалусерполици (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-163">Этот класс представляет одну политику собраний Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="89492-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="89492-164">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-165">msRTCSIP-Глобалтопологисеттинг</span><span class="sxs-lookup"><span data-stu-id="89492-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="89492-166">Объект локального глобального параметра топологии.</span><span class="sxs-lookup"><span data-stu-id="89492-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="89492-167">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-168">msRTCSIP-Глобалтопологисеттингс</span><span class="sxs-lookup"><span data-stu-id="89492-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="89492-169">Контейнер для размещения глобальных объектов параметров топологии.</span><span class="sxs-lookup"><span data-stu-id="89492-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="89492-170">Новые возможности Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-171">msRTCSIP-Локалнормализатион</span><span class="sxs-lookup"><span data-stu-id="89492-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="89492-172">Этот класс является контейнером, представляющим экземпляр правила нормализации расположения.</span><span class="sxs-lookup"><span data-stu-id="89492-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-173">msRTCSIP-Локатионконтактмаппинг</span><span class="sxs-lookup"><span data-stu-id="89492-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="89492-174">Этот класс создается приложением для проведения конференций и содержит атрибуты, которые используются для классификации телефонных номеров конференций по регионам.</span><span class="sxs-lookup"><span data-stu-id="89492-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="89492-175">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-176">msRTCSIP-Локатионконтактмаппингс</span><span class="sxs-lookup"><span data-stu-id="89492-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="89492-177">Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местоположения и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-178">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-179">msRTCSIP-Локатионпрофиле</span><span class="sxs-lookup"><span data-stu-id="89492-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="89492-180">Этот класс является контейнером, представляющим определенный профиль расположения.</span><span class="sxs-lookup"><span data-stu-id="89492-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-181">msRTCSIP-Локатионпрофилес (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-182">Этот класс является контейнером для нескольких профилей местоположения и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-183">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-184">msRTCSIP-Локалнормализатионс (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-185">Этот класс является контейнером для нескольких локальных правил нормализации и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-186">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="89492-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="89492-188">Этот класс представляет один сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="89492-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="89492-189">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-190">msRTCSIP-Мкуфакториес</span><span class="sxs-lookup"><span data-stu-id="89492-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="89492-191">Этот класс содержит несколько классов msRTCSIP-Мкуфактори и не имеет самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-192">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-193">msRTCSIP-Мкуфактори</span><span class="sxs-lookup"><span data-stu-id="89492-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="89492-194">Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа носителя.</span><span class="sxs-lookup"><span data-stu-id="89492-194">This class is a container representing a Conferencing Server Factory for a single medium type.</span></span> <span data-ttu-id="89492-195">Экземпляр этого класса создается при активации первого сервера конференций для этого конкретного типа и поставщика.</span><span class="sxs-lookup"><span data-stu-id="89492-195">An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="89492-196">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-197">msRTCSIP-Мкуфакторисервице</span><span class="sxs-lookup"><span data-stu-id="89492-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="89492-198">Этот класс обеспечивает связь определенного пула с его фабрикой серверов конференций.</span><span class="sxs-lookup"><span data-stu-id="89492-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="89492-199">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-200">msRTCSIP-Медиатионсервер</span><span class="sxs-lookup"><span data-stu-id="89492-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="89492-201">Этот класс содержит запись для точки управления службой для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="89492-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="89492-202">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-203">msRTCSIP — собрание (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-204">Этот вспомогательный класс для msRTCSIP-Глобалконтаинер содержит атрибуты, которые представляют настраиваемые параметры собрания.</span><span class="sxs-lookup"><span data-stu-id="89492-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="89492-205">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-206">msRTCSIP — мобильность</span><span class="sxs-lookup"><span data-stu-id="89492-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="89492-207">Контейнер, в котором хранятся глобальные параметры мобильности.</span><span class="sxs-lookup"><span data-stu-id="89492-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-208">msRTCSIP-Мониторингсервер</span><span class="sxs-lookup"><span data-stu-id="89492-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="89492-209">Этот класс содержит атрибуты, представляющие параметры для одного сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="89492-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="89492-210">Новые возможности коммуникационного сервера 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="89492-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-211">msRTCSIP-Фонерауте (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-212">Этот класс является контейнером, представляющим собой экземпляр наименее затратный маршрут к шлюзу или набору шлюзов.</span><span class="sxs-lookup"><span data-stu-id="89492-212">This class is a container representing an instance of a least cost route to a gateway or set of gateways.</span></span> <span data-ttu-id="89492-213">Эти сведения используются всеми корпоративными пулами или серверами Standard Edition для маршрутизации исходящих звонков в коммутируемую телефонную сеть общего пользования (PSTN) в наиболее экономичном виде.</span><span class="sxs-lookup"><span data-stu-id="89492-213">This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="89492-214">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-215">msRTCSIP-Фонераутес (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-216">Этот класс является контейнером для нескольких маршрутов с наименьшей стоимостью и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-217">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-218">msRTCSIP — стратегии (устаревшие)</span><span class="sxs-lookup"><span data-stu-id="89492-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-219">Этот класс содержит несколько классов политики Lync Server и не имеет самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-220">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-221">msRTCSIP — пул</span><span class="sxs-lookup"><span data-stu-id="89492-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="89492-222">Этот класс представляет один пул сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89492-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-223">msRTCSIP (пулы)</span><span class="sxs-lookup"><span data-stu-id="89492-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="89492-224">Этот класс содержит несколько пулов серверов Lync и не имеет самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-225">msRTCSIP-Пулсервице</span><span class="sxs-lookup"><span data-stu-id="89492-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="89492-226">Этот класс представляет контрольную точку элемента управления поинтсервице для пула.</span><span class="sxs-lookup"><span data-stu-id="89492-226">This class represents the service control pointservice control point of a pool.</span></span> <span data-ttu-id="89492-227">Пользователи, размещенные в пуле, имеют в качестве точки атрибута msRTCSIP-Примарихомесервер экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="89492-227">Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-228">msRTCSIP — присутствие</span><span class="sxs-lookup"><span data-stu-id="89492-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="89492-229">Контейнер, в котором хранятся глобальные параметры присутствия.</span><span class="sxs-lookup"><span data-stu-id="89492-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-230">msRTCSIP-регистратор</span><span class="sxs-lookup"><span data-stu-id="89492-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="89492-231">Этот вспомогательный класс для msRTCSIP-Глобалконтаинер содержит атрибуты, представляющие параметры пользователя, поддерживаемые серверами регистратора SIP.</span><span class="sxs-lookup"><span data-stu-id="89492-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-232">msRTCSIP-Раутеусаже (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-233">Этот класс является контейнером, представляющим экземпляр использования телефонной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="89492-233">This class is a container representing an instance of a phone route usage.</span></span> <span data-ttu-id="89492-234">Класс использования для телефонных маршрутов состоит из поля атрибута и поля Описание.</span><span class="sxs-lookup"><span data-stu-id="89492-234">A phone route usage class consists of an attribute field and a description field.</span></span> <span data-ttu-id="89492-235">Поле атрибута определяет тип использования.</span><span class="sxs-lookup"><span data-stu-id="89492-235">The attribute field defines a usage type.</span></span> <span data-ttu-id="89492-236">Поле «Описание» позволяет администраторам описать использование этого атрибута в телефонном маршруте.</span><span class="sxs-lookup"><span data-stu-id="89492-236">The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="89492-237">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-238">msRTCSIP-Раутеусажес (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-239">Этот класс содержит несколько экземпляров класса msRTCSIP-Раутеусаже и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-240">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-241">msRTCSIP-Поиск</span><span class="sxs-lookup"><span data-stu-id="89492-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="89492-242">Этот вспомогательный класс для msRTCSIP-Глобалконтаинер содержит атрибуты, которые ограничивают область результатов поиска и управляют ей.</span><span class="sxs-lookup"><span data-stu-id="89492-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-243">msRTCSIP-Server (сервер)</span><span class="sxs-lookup"><span data-stu-id="89492-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="89492-244">Этот класс представляет один сервер, на котором работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89492-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-245">msRTCSIP-Service</span><span class="sxs-lookup"><span data-stu-id="89492-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="89492-246">Этот класс содержит контейнер глобальных параметров и объект msRTCSIP-domain.</span><span class="sxs-lookup"><span data-stu-id="89492-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-247">msRTCSIP-Трустедмку</span><span class="sxs-lookup"><span data-stu-id="89492-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="89492-248">Этот класс содержит атрибуты, представляющие параметры для надежного сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="89492-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="89492-249">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-250">msRTCSIP-Трустедмкус</span><span class="sxs-lookup"><span data-stu-id="89492-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="89492-251">Этот класс содержит несколько экземпляров класса msRTCSIP-Трустедмку и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-252">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-253">msRTCSIP-Трустедпроксиес</span><span class="sxs-lookup"><span data-stu-id="89492-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="89492-254">Этот класс содержит несколько классов msRTCSIP-Трустедпрокси и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-255">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-256">msRTCSIP-Трустедпрокси</span><span class="sxs-lookup"><span data-stu-id="89492-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="89492-257">Этот класс является контейнером, представляющим сервер, на котором запущен прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="89492-257">This class is a container representing a server running Proxy Server.</span></span> <span data-ttu-id="89492-258">Экземпляр этого класса создается при активации нового прокси-сервера на компьютере, Соединенном с AD DS.</span><span class="sxs-lookup"><span data-stu-id="89492-258">An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="89492-259">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-260">msRTCSIP-Трустедсервер</span><span class="sxs-lookup"><span data-stu-id="89492-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="89492-261">Этот класс содержит атрибуты, представляющие параметры для доверенного сервера.</span><span class="sxs-lookup"><span data-stu-id="89492-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-262">msRTCSIP-Трустедсервице</span><span class="sxs-lookup"><span data-stu-id="89492-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="89492-263">Этот класс является контейнером, представляющим доверенную службу, которая поддерживает маршрутизацию с помощью глобально маршрутизируемой URL-адреса агента пользователя (ГРУУ).</span><span class="sxs-lookup"><span data-stu-id="89492-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="89492-264">Экземпляр этого класса создается, когда активируется новый сервер, являющийся надежным для сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89492-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="89492-265">Этот доверенный сервер должен быть присоединен к домену Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89492-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="89492-266">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-267">msRTCSIP-Трустедсервицес</span><span class="sxs-lookup"><span data-stu-id="89492-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="89492-268">Этот класс является контейнером для нескольких серверов ГРУУ и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-269">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-270">msRTCSIP-Трустедвебкомпонентссервер</span><span class="sxs-lookup"><span data-stu-id="89492-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="89492-271">Этот класс содержит атрибуты, представляющие параметры надежного веб-компонента.</span><span class="sxs-lookup"><span data-stu-id="89492-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="89492-272">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-273">msRTCSIP-Трустедвебкомпонентссерверс</span><span class="sxs-lookup"><span data-stu-id="89492-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="89492-274">Этот класс содержит несколько экземпляров класса msRTCSIP-Трустедвебкомпонентсервер и не содержит самих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="89492-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="89492-275">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-276">msRTCSIP-Унифиедкоммуникатионс (устарело)</span><span class="sxs-lookup"><span data-stu-id="89492-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="89492-277">Этот вспомогательный класс для msRTCSIP-Глобалконтаинер содержит атрибуты, связанные с единым обменом данными.</span><span class="sxs-lookup"><span data-stu-id="89492-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="89492-278">Устаревшие в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89492-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-279">msRTCSIP — компоненты</span><span class="sxs-lookup"><span data-stu-id="89492-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="89492-280">Этот класс содержит контрольную точку управления службой поинтсервице для сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="89492-280">This class holds the service control pointservice control point for Internet Information Server (IIS).</span></span> <span data-ttu-id="89492-281">Он определяет сервер как сервер веб-компонентов.</span><span class="sxs-lookup"><span data-stu-id="89492-281">It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="89492-282">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89492-283">msRTCSIP-Вебкомпонентссервице</span><span class="sxs-lookup"><span data-stu-id="89492-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="89492-284">Этот класс предоставляет ассоциацию из определенного пула к веб-компонентам, которые будут использоваться пулом.</span><span class="sxs-lookup"><span data-stu-id="89492-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="89492-285">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89492-286">msRTCSIP-Вебкомпонентсеттингс</span><span class="sxs-lookup"><span data-stu-id="89492-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="89492-287">Этот вспомогательный класс для msRTCSIP-компонентов содержит атрибуты, представляющие параметры для веб-компонентов.</span><span class="sxs-lookup"><span data-stu-id="89492-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="89492-288">Новые возможности коммуникационного сервера 2007.</span><span class="sxs-lookup"><span data-stu-id="89492-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


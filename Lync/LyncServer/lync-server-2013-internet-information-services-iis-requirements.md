---
title: 'Lync Server 2013: требования к службам IIS'
description: 'Lync Server 2013: требования к службам IIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543995"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="563f4-103">Требования к службам IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="563f4-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="563f4-104">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="563f4-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="563f4-105">Для некоторых компонентов Lync Server 2013 требуются информационные службы Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="563f4-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="563f4-106">В этом разделе описываются конкретные компоненты IIS, необходимые для поддержки Lync Server.</span><span class="sxs-lookup"><span data-stu-id="563f4-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="563f4-107">В подразделах данного раздела рассматриваются требования отдельных компонентов к службам IIS.</span><span class="sxs-lookup"><span data-stu-id="563f4-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="563f4-p102">Когда на Windows Server 2008 включена роль «Веб-сервер (IIS)», по умолчанию устанавливаются различные службы роли. В следующей таблице описываются дополнительные службы роли, которые следует установить при включении роли «Веб-сервер (IIS)» в Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="563f4-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="563f4-110">Служба роли</span><span class="sxs-lookup"><span data-stu-id="563f4-110">Role service</span></span></th>
<th><span data-ttu-id="563f4-111">Компонент</span><span class="sxs-lookup"><span data-stu-id="563f4-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="563f4-112">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="563f4-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="563f4-113">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="563f4-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f4-114">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="563f4-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="563f4-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="563f4-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f4-116">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="563f4-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="563f4-117">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="563f4-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f4-118">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="563f4-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="563f4-119">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="563f4-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f4-120">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="563f4-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="563f4-121">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="563f4-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f4-122">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="563f4-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="563f4-123">Средства ведения журнала</span><span class="sxs-lookup"><span data-stu-id="563f4-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f4-124">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="563f4-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="563f4-125">Образца</span><span class="sxs-lookup"><span data-stu-id="563f4-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f4-126">Безопасность</span><span class="sxs-lookup"><span data-stu-id="563f4-126">Security</span></span></p></td>
<td><p><span data-ttu-id="563f4-127">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="563f4-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f4-128">Безопасность</span><span class="sxs-lookup"><span data-stu-id="563f4-128">Security</span></span></p></td>
<td><p><span data-ttu-id="563f4-129">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="563f4-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f4-130">Средства управления</span><span class="sxs-lookup"><span data-stu-id="563f4-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="563f4-131">Сценарии и средства управления IIS</span><span class="sxs-lookup"><span data-stu-id="563f4-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f4-132">Средства управления</span><span class="sxs-lookup"><span data-stu-id="563f4-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="563f4-133">Совместимость управления IIS 6</span><span class="sxs-lookup"><span data-stu-id="563f4-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="563f4-135">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="563f4-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="563f4-136">Если вы используете IIS 7,0 в операционной системе Windows Server 2008, программа установки Lync Server отключает проверку подлинности в режиме ядра в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="563f4-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="563f4-137">Содержание</span><span class="sxs-lookup"><span data-stu-id="563f4-137">In This Section</span></span>

  - [<span data-ttu-id="563f4-138">Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="563f4-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


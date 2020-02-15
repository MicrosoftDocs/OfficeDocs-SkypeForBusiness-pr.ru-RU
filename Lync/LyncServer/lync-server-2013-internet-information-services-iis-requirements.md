---
title: 'Lync Server 2013: требования к службам IIS'
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
ms.openlocfilehash: 9a086713c4c4c1ea5752c7e1b46ce46e48a0ea42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="5c2db-102">Требования к службам IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c2db-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c2db-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="5c2db-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="5c2db-104">Для некоторых компонентов Lync Server 2013 требуются информационные службы Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="5c2db-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="5c2db-105">В этом разделе описываются конкретные компоненты IIS, необходимые для поддержки Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c2db-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="5c2db-106">В подразделах данного раздела рассматриваются требования отдельных компонентов к службам IIS.</span><span class="sxs-lookup"><span data-stu-id="5c2db-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="5c2db-p102">Когда на Windows Server 2008 включена роль «Веб-сервер (IIS)», по умолчанию устанавливаются различные службы роли. В следующей таблице описываются дополнительные службы роли, которые следует установить при включении роли «Веб-сервер (IIS)» в Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="5c2db-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c2db-109">Служба роли</span><span class="sxs-lookup"><span data-stu-id="5c2db-109">Role service</span></span></th>
<th><span data-ttu-id="5c2db-110">Функция</span><span class="sxs-lookup"><span data-stu-id="5c2db-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c2db-111">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="5c2db-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="5c2db-112">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="5c2db-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2db-113">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="5c2db-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5c2db-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c2db-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2db-115">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="5c2db-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5c2db-116">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="5c2db-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2db-117">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="5c2db-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5c2db-118">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="5c2db-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2db-119">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="5c2db-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="5c2db-120">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="5c2db-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2db-121">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="5c2db-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5c2db-122">Средства ведения журнала</span><span class="sxs-lookup"><span data-stu-id="5c2db-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2db-123">Проверка работоспособности и диагностика</span><span class="sxs-lookup"><span data-stu-id="5c2db-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="5c2db-124">Образца</span><span class="sxs-lookup"><span data-stu-id="5c2db-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2db-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5c2db-125">Security</span></span></p></td>
<td><p><span data-ttu-id="5c2db-126">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="5c2db-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2db-127">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5c2db-127">Security</span></span></p></td>
<td><p><span data-ttu-id="5c2db-128">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="5c2db-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2db-129">Средства управления</span><span class="sxs-lookup"><span data-stu-id="5c2db-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5c2db-130">Сценарии и средства управления IIS</span><span class="sxs-lookup"><span data-stu-id="5c2db-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2db-131">Средства управления</span><span class="sxs-lookup"><span data-stu-id="5c2db-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="5c2db-132">Совместимость управления IIS 6</span><span class="sxs-lookup"><span data-stu-id="5c2db-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="5c2db-134">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="5c2db-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5c2db-135">Если вы используете IIS 7,0 в операционной системе Windows Server 2008, программа установки Lync Server отключает проверку подлинности в режиме ядра в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5c2db-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c2db-136">Содержание</span><span class="sxs-lookup"><span data-stu-id="5c2db-136">In This Section</span></span>

  - [<span data-ttu-id="5c2db-137">Требования к службам IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c2db-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


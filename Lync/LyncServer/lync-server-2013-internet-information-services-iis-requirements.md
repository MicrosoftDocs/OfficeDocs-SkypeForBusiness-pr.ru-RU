---
title: 'Lync Server 2013: требования служб IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="c67c1-102">Требования служб IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c67c1-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c67c1-103">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="c67c1-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="c67c1-104">Для некоторых компонентов Lync Server 2013 требуются информационные службы Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="c67c1-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="c67c1-105">В этой статье описаны особые возможности IIS, необходимые для поддержки сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c67c1-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="c67c1-106">В подразделах этого раздела описаны требования конкретных компонентов IIS.</span><span class="sxs-lookup"><span data-stu-id="c67c1-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="c67c1-107">Если роль веб-сервера (IIS) включена в Windows Server 2008, по умолчанию устанавливаются различные службы ролей.</span><span class="sxs-lookup"><span data-stu-id="c67c1-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="c67c1-108">В приведенной ниже таблице описаны дополнительные службы ролей, которые необходимо установить, если в Windows Server 2008 включена роль веб-сервера (IIS).</span><span class="sxs-lookup"><span data-stu-id="c67c1-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c67c1-109">Служба ролей</span><span class="sxs-lookup"><span data-stu-id="c67c1-109">Role service</span></span></th>
<th><span data-ttu-id="c67c1-110">Функция</span><span class="sxs-lookup"><span data-stu-id="c67c1-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c67c1-111">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="c67c1-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c67c1-112">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="c67c1-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c67c1-113">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="c67c1-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c67c1-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c67c1-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c67c1-115">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="c67c1-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c67c1-116">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="c67c1-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c67c1-117">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="c67c1-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c67c1-118">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="c67c1-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c67c1-119">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="c67c1-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c67c1-120">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="c67c1-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c67c1-121">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="c67c1-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c67c1-122">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="c67c1-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c67c1-123">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="c67c1-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c67c1-124">Трассировка</span><span class="sxs-lookup"><span data-stu-id="c67c1-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c67c1-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c67c1-125">Security</span></span></p></td>
<td><p><span data-ttu-id="c67c1-126">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="c67c1-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c67c1-127">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c67c1-127">Security</span></span></p></td>
<td><p><span data-ttu-id="c67c1-128">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="c67c1-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c67c1-129">Средства управления</span><span class="sxs-lookup"><span data-stu-id="c67c1-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c67c1-130">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="c67c1-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c67c1-131">Средства управления</span><span class="sxs-lookup"><span data-stu-id="c67c1-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c67c1-132">Совместимость управления IIS 6</span><span class="sxs-lookup"><span data-stu-id="c67c1-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" /><span data-ttu-id="c67c1-134">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="c67c1-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c67c1-135">Если вы используете сервер IIS 7,0 в операционной системе Windows Server 2008, Настройка сервера Lync Server отключает проверку подлинности в режиме ядра в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="c67c1-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c67c1-136">Содержание</span><span class="sxs-lookup"><span data-stu-id="c67c1-136">In This Section</span></span>

  - [<span data-ttu-id="c67c1-137">Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c67c1-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


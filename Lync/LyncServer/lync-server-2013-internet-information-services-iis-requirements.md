---
title: 'Lync Server 2013: требования служб IIS'
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
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="ff328-102">Требования служб IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff328-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff328-103">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ff328-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ff328-104">Для некоторых компонентов Lync Server 2013 требуются информационные службы Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="ff328-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="ff328-105">В этой статье описаны особые возможности IIS, необходимые для поддержки сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff328-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="ff328-106">В подразделах этого раздела описаны требования конкретных компонентов IIS.</span><span class="sxs-lookup"><span data-stu-id="ff328-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="ff328-107">Если роль веб-сервера (IIS) включена в Windows Server 2008, по умолчанию устанавливаются различные службы ролей.</span><span class="sxs-lookup"><span data-stu-id="ff328-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="ff328-108">В приведенной ниже таблице описаны дополнительные службы ролей, которые необходимо установить, если в Windows Server 2008 включена роль веб-сервера (IIS).</span><span class="sxs-lookup"><span data-stu-id="ff328-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff328-109">Служба ролей</span><span class="sxs-lookup"><span data-stu-id="ff328-109">Role service</span></span></th>
<th><span data-ttu-id="ff328-110">Функция</span><span class="sxs-lookup"><span data-stu-id="ff328-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff328-111">Основные возможности HTTP</span><span class="sxs-lookup"><span data-stu-id="ff328-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="ff328-112">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="ff328-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff328-113">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="ff328-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff328-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ff328-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff328-115">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="ff328-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff328-116">Расширяемость .NET</span><span class="sxs-lookup"><span data-stu-id="ff328-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff328-117">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="ff328-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff328-118">Расширения ISAPI</span><span class="sxs-lookup"><span data-stu-id="ff328-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff328-119">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="ff328-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff328-120">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="ff328-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff328-121">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="ff328-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="ff328-122">Средства ведения журналов</span><span class="sxs-lookup"><span data-stu-id="ff328-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff328-123">Работоспособность и диагностика</span><span class="sxs-lookup"><span data-stu-id="ff328-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="ff328-124">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ff328-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff328-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ff328-125">Security</span></span></p></td>
<td><p><span data-ttu-id="ff328-126">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ff328-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff328-127">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ff328-127">Security</span></span></p></td>
<td><p><span data-ttu-id="ff328-128">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="ff328-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff328-129">Средства управления</span><span class="sxs-lookup"><span data-stu-id="ff328-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="ff328-130">Сценарии и средства управления для служб IIS</span><span class="sxs-lookup"><span data-stu-id="ff328-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff328-131">Средства управления</span><span class="sxs-lookup"><span data-stu-id="ff328-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="ff328-132">Совместимость управления IIS 6</span><span class="sxs-lookup"><span data-stu-id="ff328-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" /><span data-ttu-id="ff328-134">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="ff328-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ff328-135">Если вы используете сервер IIS 7,0 в операционной системе Windows Server 2008, Настройка сервера Lync Server отключает проверку подлинности в режиме ядра в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="ff328-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff328-136">Содержание</span><span class="sxs-lookup"><span data-stu-id="ff328-136">In This Section</span></span>

  - [<span data-ttu-id="ff328-137">Требования IIS для пулов переднего плана и серверов Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff328-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


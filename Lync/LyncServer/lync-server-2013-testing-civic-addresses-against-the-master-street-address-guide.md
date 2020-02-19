---
title: Проверка административного адреса для основного почтового руководства по адресу
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f9115e6bc0c65f589effc08ecd5f7b681208a54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="e03c9-102">Тестирование административных адресов для главного почтового руководства по адресу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e03c9-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e03c9-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e03c9-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e03c9-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e03c9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e03c9-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="e03c9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e03c9-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e03c9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e03c9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e03c9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e03c9-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="e03c9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e03c9-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e03c9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e03c9-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="e03c9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="e03c9-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e03c9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e03c9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e03c9-112">Description</span></span>

<span data-ttu-id="e03c9-113">Командлет Test-КслисЦивикаддресс используется для проверки расположений, добавленных в базу данных службы сведений о местоположении (LIS).</span><span class="sxs-lookup"><span data-stu-id="e03c9-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="e03c9-114">Командлет выполняет сравнение расположений с местоположениями в главном руководстве по адресам (MSAG), которые относятся к поставщику маршрутизации сети E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e03c9-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="e03c9-115">Если у вас нет поставщика сетевой маршрутизации или если поставщик недоступен, то тесты завершатся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="e03c9-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="e03c9-116">Если вы добавите необязательный параметр переключателя Упдатевалидатионстатус к команде, то для соответствующего свойства базы данных Мсагвалид будет задано значение true для каждого адреса, пройденного тест.</span><span class="sxs-lookup"><span data-stu-id="e03c9-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e03c9-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e03c9-117">Running the test</span></span>

<span data-ttu-id="e03c9-118">Командлет Test-КслисЦивикаддресс можно использовать для проверки отдельных адресов или для проверки нескольких адресов.</span><span class="sxs-lookup"><span data-stu-id="e03c9-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="e03c9-119">Например, эта команда проверяет один адрес, расположенный в Редмонде, WA:</span><span class="sxs-lookup"><span data-stu-id="e03c9-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="e03c9-120">При сравнении эта команда тестирует все адреса, которые в настоящее время находятся в базе данных LIS:</span><span class="sxs-lookup"><span data-stu-id="e03c9-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="e03c9-121">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="e03c9-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e03c9-122">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="e03c9-122">Determining success or failure</span></span>

<span data-ttu-id="e03c9-123">Test-КслисЦивикаддресс будет сообщать об успешном выполнении или сбое для указанных адресов.</span><span class="sxs-lookup"><span data-stu-id="e03c9-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="e03c9-124">Если не удается найти адрес или не удается связаться с поставщиком услуг, тест адреса завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e03c9-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e03c9-125">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e03c9-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="e03c9-126">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-КслисЦивикаддресс:</span><span class="sxs-lookup"><span data-stu-id="e03c9-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="e03c9-127">Поставщик услуг LIS может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="e03c9-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="e03c9-128">Вы можете получить URL-адрес поставщика службы LIS, выполнив командлет Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="e03c9-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="e03c9-129">После этого вы можете проверить связь с этим URL-адресом, чтобы проверить, доступен ли поставщик услуг.</span><span class="sxs-lookup"><span data-stu-id="e03c9-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


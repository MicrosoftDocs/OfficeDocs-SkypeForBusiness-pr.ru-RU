---
title: Тестирование многоадресных адресов в главном руководстве почтового адреса
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
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="888bc-102">Проверка многоадресных адресов в главном руководстве почтового адреса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="888bc-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="888bc-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="888bc-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="888bc-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="888bc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="888bc-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="888bc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="888bc-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="888bc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="888bc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="888bc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="888bc-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="888bc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="888bc-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="888bc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="888bc-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксрегистратион.</span><span class="sxs-lookup"><span data-stu-id="888bc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="888bc-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="888bc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="888bc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="888bc-112">Description</span></span>

<span data-ttu-id="888bc-113">Командлет Test-КслисЦивикаддресс используется для проверки местоположений, добавленных в базу данных службы сведений о расположении (LIS).</span><span class="sxs-lookup"><span data-stu-id="888bc-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="888bc-114">Командлет выполняет сравнение расположений с расположениями в главном руководстве по адресу (МСАГ), которые относятся к поставщику сетевой маршрутизации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="888bc-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="888bc-115">Если у вас нет провайдера сетевой маршрутизации или если поставщик недоступен, тесты завершатся сбоем.</span><span class="sxs-lookup"><span data-stu-id="888bc-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="888bc-116">Если вы добавите в команду необязательный параметр ключа Упдатевалидатионстатус, для соответствующего свойства базы данных Мсагвалид будет задано значение "true" для каждого адреса, продающего проверку.</span><span class="sxs-lookup"><span data-stu-id="888bc-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="888bc-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="888bc-117">Running the test</span></span>

<span data-ttu-id="888bc-118">Командлет Test-КслисЦивикаддресс можно использовать для проверки отдельных адресов или проверки нескольких адресов.</span><span class="sxs-lookup"><span data-stu-id="888bc-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="888bc-119">Например, эта команда проверяет один адрес, указанный в Редмонде, WA:</span><span class="sxs-lookup"><span data-stu-id="888bc-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="888bc-120">По сравнению с этой командой проверяются все адреса, находящиеся в базе данных LIS.</span><span class="sxs-lookup"><span data-stu-id="888bc-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="888bc-121">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксрегистратион](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="888bc-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="888bc-122">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="888bc-122">Determining success or failure</span></span>

<span data-ttu-id="888bc-123">Тест-КслисЦивикаддресс сообщит об успешном завершении или сбое для указанных адресов.</span><span class="sxs-lookup"><span data-stu-id="888bc-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="888bc-124">Если адрес не удается найти или не удается связаться с поставщиком услуг, проверка адреса завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="888bc-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="888bc-125">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="888bc-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="888bc-126">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-КслисЦивикаддресс:</span><span class="sxs-lookup"><span data-stu-id="888bc-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="888bc-127">Поставщик услуг LIS может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="888bc-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="888bc-128">Вы можете получить URL-адрес поставщика услуг LIS, выполнив командлет Get-Кслисконфигуратион:</span><span class="sxs-lookup"><span data-stu-id="888bc-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="888bc-129">Затем вы можете проверить связь с этим URL-адресом, чтобы убедиться, что поставщик услуг доступен.</span><span class="sxs-lookup"><span data-stu-id="888bc-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


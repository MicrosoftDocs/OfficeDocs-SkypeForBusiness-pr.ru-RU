---
title: 'Lync Server 2013: тестирование возможности подключения к федеративного домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a565c09e09e10eeb160b1d0514c89499427d1283
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532926"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="9676f-102">Тестирование возможности подключения к федеративного домена из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9676f-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9676f-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9676f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9676f-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="9676f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9676f-105">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="9676f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9676f-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="9676f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9676f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9676f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9676f-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="9676f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9676f-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9676f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9676f-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="9676f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="9676f-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9676f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9676f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9676f-112">Description</span></span>

<span data-ttu-id="9676f-113">Test-CsFederatedPartner проверяет возможность подключения к домену федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="9676f-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="9676f-114">Чтобы проверить подключение к домену, этот домен должен быть указан в коллекции разрешенных (Федеративных) доменов.</span><span class="sxs-lookup"><span data-stu-id="9676f-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="9676f-115">С помощью этой команды можно получить список доменов из списка разрешенных доменов:</span><span class="sxs-lookup"><span data-stu-id="9676f-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="9676f-116">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="9676f-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9676f-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="9676f-117">Running the test</span></span>

<span data-ttu-id="9676f-118">Командлету Test-FederatedPartner требуются два фрагмента информации: полное доменное имя пограничного сервера и полное доменное имя федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="9676f-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="9676f-119">Например, эта команда проверяет возможность подключения к домену contoso.com:</span><span class="sxs-lookup"><span data-stu-id="9676f-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="9676f-120">Эта команда позволяет проверить подключения ко всем доменам, которые в настоящее время находятся в списке разрешенных доменов:</span><span class="sxs-lookup"><span data-stu-id="9676f-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="9676f-121">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="9676f-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9676f-122">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="9676f-122">Determining success or failure</span></span>

<span data-ttu-id="9676f-123">Если к указанному домену можно обратиться, вы получите выходные данные, аналогичные приведенным ниже, с свойством Result, помеченным как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="9676f-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9676f-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9676f-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9676f-125">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="9676f-125">Result : Success</span></span>

<span data-ttu-id="9676f-126">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9676f-126">Latency : 00:00:00</span></span>

<span data-ttu-id="9676f-127">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="9676f-127">Error :</span></span>

<span data-ttu-id="9676f-128">Диагност</span><span class="sxs-lookup"><span data-stu-id="9676f-128">Diagnosis :</span></span>

<span data-ttu-id="9676f-129">Если не удается связаться с указанным доменом, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="9676f-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9676f-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9676f-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9676f-131">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="9676f-131">Result : Failure</span></span>

<span data-ttu-id="9676f-132">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9676f-132">Latency : 00:00:00</span></span>

<span data-ttu-id="9676f-133">Ошибка: 504, время ожидания сервера</span><span class="sxs-lookup"><span data-stu-id="9676f-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="9676f-134">Диагностика: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = видите</span><span class="sxs-lookup"><span data-stu-id="9676f-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="9676f-135">код отклика и фраза причины.</span><span class="sxs-lookup"><span data-stu-id="9676f-135">response code and reason phrase.</span></span>

<span data-ttu-id="9676f-136">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="9676f-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="9676f-137">Например, предыдущие выходные данные погрешностей о том, что тест завершился сбоем из-за ошибки времени ожидания сервера.</span><span class="sxs-lookup"><span data-stu-id="9676f-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="9676f-138">Как правило, это свидетельствует о проблемах с подключением к сети или проблемах связи с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="9676f-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="9676f-139">Если Test-CsFederatedPartner завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="9676f-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9676f-140">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="9676f-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="9676f-141">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsFederatedPartner:</span><span class="sxs-lookup"><span data-stu-id="9676f-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="9676f-142">Пограничный сервер может быть недоступен.</span><span class="sxs-lookup"><span data-stu-id="9676f-142">The Edge Server might not be available.</span></span> <span data-ttu-id="9676f-143">Полные доменные имена пограничных серверов можно выполнить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9676f-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="9676f-144">После этого можно выполнить обмен пакетами с каждым пограничным сервером, чтобы убедиться, что к ним возможен доступ через сеть.</span><span class="sxs-lookup"><span data-stu-id="9676f-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="9676f-145">Например:</span><span class="sxs-lookup"><span data-stu-id="9676f-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="9676f-146">Указанный домен может не отображаться в списке разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="9676f-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="9676f-147">Чтобы проверить домены, добавленные в список разрешенных доменов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9676f-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="9676f-148">Если вы хотите просмотреть список доменов, с которыми пользователи блокировали связь с, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9676f-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>


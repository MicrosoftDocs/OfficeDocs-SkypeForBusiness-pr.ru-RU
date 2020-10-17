---
title: 'Lync Server 2013: тестирование конфигурации сервера LIS'
description: 'Lync Server 2013: тестирование конфигурации сервера LIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560615"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="152f4-103">Тестирование конфигурации сервера LIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="152f4-103">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="152f4-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="152f4-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="152f4-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="152f4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="152f4-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="152f4-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="152f4-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="152f4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="152f4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="152f4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="152f4-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="152f4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="152f4-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="152f4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="152f4-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="152f4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="152f4-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="152f4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="152f4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="152f4-113">Description</span></span>

<span data-ttu-id="152f4-114">Командлет Test-CsLisConfiguration проверяет возможность связи с веб-службой LIS.</span><span class="sxs-lookup"><span data-stu-id="152f4-114">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="152f4-115">Если вы можете связаться с веб-службой, тест будет считаться успешным, независимо от того, можно ли найти какие-либо конкретные расположения.</span><span class="sxs-lookup"><span data-stu-id="152f4-115">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="152f4-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="152f4-116">Running the test</span></span>

<span data-ttu-id="152f4-117">Командлет Test-CsLisConfguration можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="152f4-117">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="152f4-118">Чтобы выполнить эту проверку с помощью тестовой учетной записи, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="152f4-118">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="152f4-119">Например:</span><span class="sxs-lookup"><span data-stu-id="152f4-119">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="152f4-120">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="152f4-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="152f4-121">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="152f4-121">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="152f4-122">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="152f4-122">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="152f4-123">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="152f4-123">Determining success or failure</span></span>

<span data-ttu-id="152f4-124">Если LIS настроен правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="152f4-124">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="152f4-125">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="152f4-125">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="152f4-126">лисервице. svc</span><span class="sxs-lookup"><span data-stu-id="152f4-126">liservice.svc</span></span>

<span data-ttu-id="152f4-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="152f4-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="152f4-128">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="152f4-128">Result : Success</span></span>

<span data-ttu-id="152f4-129">Задержка: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="152f4-129">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="152f4-130">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="152f4-130">Error :</span></span>

<span data-ttu-id="152f4-131">Диагност</span><span class="sxs-lookup"><span data-stu-id="152f4-131">Diagnosis :</span></span>

<span data-ttu-id="152f4-132">Если указанный пользователь не может войти в систему или выйти из нее, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="152f4-132">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="152f4-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="152f4-133">TargetUri :</span></span>

<span data-ttu-id="152f4-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="152f4-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="152f4-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="152f4-135">Result : Failure</span></span>

<span data-ttu-id="152f4-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="152f4-136">Latency : 00:00:00</span></span>

<span data-ttu-id="152f4-137">Ошибка: 11004, запрошенное имя является допустимым, но данные запрошенного</span><span class="sxs-lookup"><span data-stu-id="152f4-137">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="152f4-138">обнаружен тип</span><span class="sxs-lookup"><span data-stu-id="152f4-138">type was found</span></span>

<span data-ttu-id="152f4-139">Диагност</span><span class="sxs-lookup"><span data-stu-id="152f4-139">Diagnosis :</span></span>

<span data-ttu-id="152f4-140">Test-CsLisConfiguration: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="152f4-140">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="152f4-141">Например, в предыдущем выходе включается заметка "в топологии не обнаружены подходящие кластеры".</span><span class="sxs-lookup"><span data-stu-id="152f4-141">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="152f4-142">Как правило, это свидетельствует о проблеме с пограничным сервером: LIS, использующий пограничный сервер, для подключения к поставщику услуг и проверки адресов.</span><span class="sxs-lookup"><span data-stu-id="152f4-142">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="152f4-143">В случае сбоя Test-CsLisConfiguration вы можете повторно выполнить тест, на этот раз включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="152f4-143">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="152f4-144">Если включен параметр Verbose, Test-CsLisConfiguration будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="152f4-144">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="152f4-145">Например:</span><span class="sxs-lookup"><span data-stu-id="152f4-145">For example:</span></span>

<span data-ttu-id="152f4-146">Служба сведений о расположении звонков.</span><span class="sxs-lookup"><span data-stu-id="152f4-146">Calling Location Information Service.</span></span>

<span data-ttu-id="152f4-147">Путь к службе = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="152f4-147">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="152f4-148">Subnet =</span><span class="sxs-lookup"><span data-stu-id="152f4-148">Subnet =</span></span>

<span data-ttu-id="152f4-149">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="152f4-149">BssId = 5</span></span>

<span data-ttu-id="152f4-150">Чассисид =</span><span class="sxs-lookup"><span data-stu-id="152f4-150">ChassisId =</span></span>

<span data-ttu-id="152f4-151">Портид =</span><span class="sxs-lookup"><span data-stu-id="152f4-151">PortId =</span></span>

<span data-ttu-id="152f4-152">Портидсубтипе = неопределенный тип</span><span class="sxs-lookup"><span data-stu-id="152f4-152">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="152f4-153">Mac</span><span class="sxs-lookup"><span data-stu-id="152f4-153">Mac</span></span>

<span data-ttu-id="152f4-154">Ошибка запроса веб-службы сведений о расположении с кодом отклика Item400.</span><span class="sxs-lookup"><span data-stu-id="152f4-154">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="152f4-155">возникла во время выполнения рабочего процесса Microsoft. RTC. Синсетиктрснактионс. Workflows. Стлисконфигуратионворкфлов.</span><span class="sxs-lookup"><span data-stu-id="152f4-155">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="152f4-156">Если вы изучите предыдущие выходные данные, вы увидите, что командлет завершился с ошибкой после попытки вызова службы сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="152f4-156">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="152f4-157">Один из параметров, которые использовались в этом вызове:</span><span class="sxs-lookup"><span data-stu-id="152f4-157">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="152f4-158">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="152f4-158">BssId = 5</span></span>

<span data-ttu-id="152f4-159">Это значение не является допустимым для базового идентификатора набора служб (BssID).</span><span class="sxs-lookup"><span data-stu-id="152f4-159">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="152f4-160">Вместо этого BssID должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="152f4-160">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="152f4-161">12-34-56-78-90 – AB</span><span class="sxs-lookup"><span data-stu-id="152f4-161">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="152f4-162">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="152f4-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="152f4-163">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="152f4-163">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="152f4-164">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="152f4-164">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="152f4-165">Как показано в предыдущем примере, необязательные параметры должны быть настроены правильно, иначе тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="152f4-165">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="152f4-166">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="152f4-166">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


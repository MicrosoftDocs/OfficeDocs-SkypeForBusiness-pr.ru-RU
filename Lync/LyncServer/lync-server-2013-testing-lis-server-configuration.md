---
title: 'Lync Server 2013: тестирование конфигурации сервера LIS'
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
ms.openlocfilehash: 8893964ce1982c67dc97ed93bca9ba19ec2f24e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536022"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="450db-102">Тестирование конфигурации сервера LIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="450db-102">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="450db-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="450db-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="450db-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="450db-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="450db-105">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="450db-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="450db-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="450db-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="450db-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="450db-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="450db-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="450db-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="450db-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="450db-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="450db-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsLisConfiguration.</span><span class="sxs-lookup"><span data-stu-id="450db-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="450db-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="450db-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="450db-112">Описание</span><span class="sxs-lookup"><span data-stu-id="450db-112">Description</span></span>

<span data-ttu-id="450db-113">Командлет Test-CsLisConfiguration проверяет возможность связи с веб-службой LIS.</span><span class="sxs-lookup"><span data-stu-id="450db-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="450db-114">Если вы можете связаться с веб-службой, тест будет считаться успешным, независимо от того, можно ли найти какие-либо конкретные расположения.</span><span class="sxs-lookup"><span data-stu-id="450db-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="450db-115">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="450db-115">Running the test</span></span>

<span data-ttu-id="450db-116">Командлет Test-CsLisConfguration можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="450db-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="450db-117">Чтобы выполнить эту проверку с помощью тестовой учетной записи, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="450db-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="450db-118">Например:</span><span class="sxs-lookup"><span data-stu-id="450db-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="450db-119">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="450db-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="450db-120">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, при вызове Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="450db-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="450db-121">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="450db-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="450db-122">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="450db-122">Determining success or failure</span></span>

<span data-ttu-id="450db-123">Если LIS настроен правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="450db-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="450db-124">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="450db-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="450db-125">лисервице. svc</span><span class="sxs-lookup"><span data-stu-id="450db-125">liservice.svc</span></span>

<span data-ttu-id="450db-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="450db-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="450db-127">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="450db-127">Result : Success</span></span>

<span data-ttu-id="450db-128">Задержка: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="450db-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="450db-129">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="450db-129">Error :</span></span>

<span data-ttu-id="450db-130">Диагност</span><span class="sxs-lookup"><span data-stu-id="450db-130">Diagnosis :</span></span>

<span data-ttu-id="450db-131">Если указанный пользователь не может войти в систему или выйти из нее, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="450db-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="450db-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="450db-132">TargetUri :</span></span>

<span data-ttu-id="450db-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="450db-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="450db-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="450db-134">Result : Failure</span></span>

<span data-ttu-id="450db-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="450db-135">Latency : 00:00:00</span></span>

<span data-ttu-id="450db-136">Ошибка: 11004, запрошенное имя является допустимым, но данные запрошенного</span><span class="sxs-lookup"><span data-stu-id="450db-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="450db-137">обнаружен тип</span><span class="sxs-lookup"><span data-stu-id="450db-137">type was found</span></span>

<span data-ttu-id="450db-138">Диагност</span><span class="sxs-lookup"><span data-stu-id="450db-138">Diagnosis :</span></span>

<span data-ttu-id="450db-139">Test-CsLisConfiguration: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="450db-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="450db-140">Например, в предыдущем выходе включается заметка "в топологии не обнаружены подходящие кластеры".</span><span class="sxs-lookup"><span data-stu-id="450db-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="450db-141">Как правило, это свидетельствует о проблеме с пограничным сервером: LIS, использующий пограничный сервер, для подключения к поставщику услуг и проверки адресов.</span><span class="sxs-lookup"><span data-stu-id="450db-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="450db-142">В случае сбоя Test-CsLisConfiguration вы можете повторно выполнить тест, на этот раз включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="450db-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="450db-143">Если включен параметр Verbose, Test-CsLisConfiguration будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="450db-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="450db-144">Например:</span><span class="sxs-lookup"><span data-stu-id="450db-144">For example:</span></span>

<span data-ttu-id="450db-145">Служба сведений о расположении звонков.</span><span class="sxs-lookup"><span data-stu-id="450db-145">Calling Location Information Service.</span></span>

<span data-ttu-id="450db-146">Путь к службе = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="450db-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="450db-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="450db-147">Subnet =</span></span>

<span data-ttu-id="450db-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="450db-148">BssId = 5</span></span>

<span data-ttu-id="450db-149">Чассисид =</span><span class="sxs-lookup"><span data-stu-id="450db-149">ChassisId =</span></span>

<span data-ttu-id="450db-150">Портид =</span><span class="sxs-lookup"><span data-stu-id="450db-150">PortId =</span></span>

<span data-ttu-id="450db-151">Портидсубтипе = неопределенный тип</span><span class="sxs-lookup"><span data-stu-id="450db-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="450db-152">Mac</span><span class="sxs-lookup"><span data-stu-id="450db-152">Mac</span></span>

<span data-ttu-id="450db-153">Ошибка запроса веб-службы сведений о расположении с кодом отклика Item400.</span><span class="sxs-lookup"><span data-stu-id="450db-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="450db-154">возникла во время выполнения рабочего процесса Microsoft. RTC. Синсетиктрснактионс. Workflows. Стлисконфигуратионворкфлов.</span><span class="sxs-lookup"><span data-stu-id="450db-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="450db-155">Если вы изучите предыдущие выходные данные, вы увидите, что командлет завершился с ошибкой после попытки вызова службы сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="450db-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="450db-156">Один из параметров, которые использовались в этом вызове:</span><span class="sxs-lookup"><span data-stu-id="450db-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="450db-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="450db-157">BssId = 5</span></span>

<span data-ttu-id="450db-158">Это значение не является допустимым для базового идентификатора набора служб (BssID).</span><span class="sxs-lookup"><span data-stu-id="450db-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="450db-159">Вместо этого BssID должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="450db-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="450db-160">12-34-56-78-90 – AB</span><span class="sxs-lookup"><span data-stu-id="450db-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="450db-161">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="450db-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="450db-162">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="450db-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="450db-163">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="450db-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="450db-164">Как показано в предыдущем примере, необязательные параметры должны быть настроены правильно, иначе тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="450db-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="450db-165">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="450db-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


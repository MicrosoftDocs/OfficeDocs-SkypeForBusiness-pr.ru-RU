---
title: 'Lync Server 2013: тестирование возможности использования расширения групп'
description: 'Lync Server 2013: тестирование возможности использования расширения групп.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560795"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="22f0e-103">Тестирование возможности использования расширения групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22f0e-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f0e-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="22f0e-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f0e-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="22f0e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="22f0e-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="22f0e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f0e-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="22f0e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="22f0e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22f0e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f0e-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="22f0e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="22f0e-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="22f0e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="22f0e-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsGroupExpansion.</span><span class="sxs-lookup"><span data-stu-id="22f0e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="22f0e-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="22f0e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="22f0e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="22f0e-113">Description</span></span>

<span data-ttu-id="22f0e-114">Командлет Test-CsGroupExpansion позволяет определить, работает ли расширение группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="22f0e-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="22f0e-115">Если включено расширение группы, пользователи настраивают группы рассылки как контакты.</span><span class="sxs-lookup"><span data-stu-id="22f0e-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="22f0e-116">Это означает, что эти пользователи могут отправить одно и то же мгновенное сообщение всем участникам группы, отправляя сообщение в группу, а не отдельные участники этой группы.</span><span class="sxs-lookup"><span data-stu-id="22f0e-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="22f0e-117">Углубление в группы позволяет быстро и просто увидеть всех членов группы и их текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="22f0e-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="22f0e-118">С помощью командлета Test-CsGroupExpansion вы указываете группу рассылки Active Directory с помощью электронного адреса группы.</span><span class="sxs-lookup"><span data-stu-id="22f0e-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="22f0e-119">В Test-CsGroupExpansion затем используется расширение группы для получения сведений о членстве в группах и сравнения полученного списка с членством в указанном адресе электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="22f0e-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="22f0e-120">Если эти два списка совпадают, то значит углубление в группы работает правильно.</span><span class="sxs-lookup"><span data-stu-id="22f0e-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="22f0e-121">Обратите внимание, что вы можете протестировать расширение группы двумя способами: Протестируйте саму службу или протестируйте связанную веб-службу.</span><span class="sxs-lookup"><span data-stu-id="22f0e-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="22f0e-122">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="22f0e-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="22f0e-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="22f0e-123">Running the test</span></span>

<span data-ttu-id="22f0e-124">Командлет Test-CsGroupExpansion можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, который был включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f0e-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="22f0e-125">Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула Lync Server и адрес электронной почты для действительной группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="22f0e-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="22f0e-126">Например:</span><span class="sxs-lookup"><span data-stu-id="22f0e-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="22f0e-127">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Lync Server, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="22f0e-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="22f0e-128">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда система вызывает Test-Ксграупекспансион:</span><span class="sxs-lookup"><span data-stu-id="22f0e-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="22f0e-129">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="22f0e-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="22f0e-130">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="22f0e-130">Determining success or failure</span></span>

<span data-ttu-id="22f0e-131">Если указанный пользователь может использовать расширение группы, будет выведен результат, подобный следующему, с свойством Result, помеченным как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="22f0e-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="22f0e-132">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="22f0e-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="22f0e-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="22f0e-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="22f0e-134">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="22f0e-134">Result : Success</span></span>

<span data-ttu-id="22f0e-135">Задержка: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="22f0e-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="22f0e-136">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="22f0e-136">Error :</span></span>

<span data-ttu-id="22f0e-137">Диагност</span><span class="sxs-lookup"><span data-stu-id="22f0e-137">Diagnosis :</span></span>

<span data-ttu-id="22f0e-138">Если указанный пользователь не может использовать расширение группы, то результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="22f0e-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="22f0e-139">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="22f0e-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="22f0e-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="22f0e-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="22f0e-141">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="22f0e-141">Result : Failure</span></span>

<span data-ttu-id="22f0e-142">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="22f0e-142">Latency : 00:00:00</span></span>

<span data-ttu-id="22f0e-143">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="22f0e-143">Error :</span></span>

<span data-ttu-id="22f0e-144">Диагност</span><span class="sxs-lookup"><span data-stu-id="22f0e-144">Diagnosis :</span></span>

<span data-ttu-id="22f0e-145">Test-CsGroupExpansion: не удалось зарегистрировать конечную точку.</span><span class="sxs-lookup"><span data-stu-id="22f0e-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="22f0e-146">Обратитесь к разделу ErrorCode по определенному причине.</span><span class="sxs-lookup"><span data-stu-id="22f0e-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="22f0e-147">Предыдущие выходные данные появлялись, что не удалось выполнить проверку, так как указанный пользователь не смог зарегистрироваться в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f0e-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="22f0e-148">Обычно это происходит, если тестовая учетная запись не существует или не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f0e-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="22f0e-149">Вы можете убедиться, что учетная запись существует, и определить, включена ли учетная запись для NM-OCS-14-3, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="22f0e-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="22f0e-150">Если Test-CsGroupExpansion завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="22f0e-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="22f0e-151">Если включен параметр Verbose, Test-CsGroupExpansion будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f0e-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="22f0e-152">Например, эти выходные данные указывают на то, что не удалось найти указанную группу рассылки:</span><span class="sxs-lookup"><span data-stu-id="22f0e-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="22f0e-153">Попытка получить веб-билет.</span><span class="sxs-lookup"><span data-stu-id="22f0e-153">Trying to get web ticket.</span></span>

<span data-ttu-id="22f0e-154">URL-адрес веб-службы: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="22f0e-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="22f0e-155">Использование проверки подлинности NTLM/Kerbtray.</span><span class="sxs-lookup"><span data-stu-id="22f0e-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="22f0e-156">Жетвебтиккетактивити завершен.</span><span class="sxs-lookup"><span data-stu-id="22f0e-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="22f0e-157">Начато действие "Верифидистрибутионлист".</span><span class="sxs-lookup"><span data-stu-id="22f0e-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="22f0e-158">Состояние ответа веб-службы ДЛКС: Нотфаунд.</span><span class="sxs-lookup"><span data-stu-id="22f0e-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="22f0e-159">Действие ' Верифидистрибутионлист ' завершено в ' 0,2597923 ' сек.</span><span class="sxs-lookup"><span data-stu-id="22f0e-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="22f0e-160">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="22f0e-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="22f0e-161">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsGroupExpansion:</span><span class="sxs-lookup"><span data-stu-id="22f0e-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="22f0e-162">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="22f0e-162">You specified an invalid user account.</span></span> <span data-ttu-id="22f0e-163">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="22f0e-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="22f0e-164">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f0e-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="22f0e-165">Чтобы убедиться, что учетная запись пользователя была включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="22f0e-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="22f0e-166">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22f0e-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="22f0e-167">Расширение группы может быть отключено.</span><span class="sxs-lookup"><span data-stu-id="22f0e-167">Group expansion might be disabled.</span></span> <span data-ttu-id="22f0e-168">Можно отключить расширение группы.</span><span class="sxs-lookup"><span data-stu-id="22f0e-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="22f0e-169">Если расширение группы было отключено, командлет Test-CsGroupExpansion завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="22f0e-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="22f0e-170">Чтобы определить, включено ли расширение группы, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="22f0e-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>


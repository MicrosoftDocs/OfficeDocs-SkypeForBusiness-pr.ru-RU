---
title: 'Lync Server 2013: тестирование возможности использования расширения групп'
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
ms.openlocfilehash: ca5964a31682172bafb0c7d5604aab7f70ad8fbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="f3cd0-102">Тестирование возможности использования расширения групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3cd0-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3cd0-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f3cd0-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3cd0-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f3cd0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f3cd0-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="f3cd0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3cd0-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f3cd0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f3cd0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3cd0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3cd0-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="f3cd0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f3cd0-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f3cd0-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксграупекспансион.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="f3cd0-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f3cd0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f3cd0-112">Description</span></span>

<span data-ttu-id="f3cd0-113">Командлет Test-Ксграупекспансион позволяет определить, работает ли расширение группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="f3cd0-114">Если включено расширение группы, пользователи настраивают группы рассылки как контакты.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="f3cd0-115">Это означает, что эти пользователи могут отправить одно и то же мгновенное сообщение всем участникам группы, отправляя сообщение в группу, а не отдельные участники этой группы.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="f3cd0-116">Углубление в группы позволяет быстро и просто увидеть всех членов группы и их текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="f3cd0-117">С помощью командлета Test-Ксграупекспансион вы указываете группу рассылки Active Directory, используя адрес электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="f3cd0-118">После этого Test-Ксграупекспансион использует расширение группы для получения сведений о членстве в группах и сравнения полученного списка с членством в указанном адресе электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="f3cd0-119">Если эти два списка совпадают, то значит углубление в группы работает правильно.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="f3cd0-120">Обратите внимание, что вы можете протестировать расширение группы двумя способами: Протестируйте саму службу или протестируйте связанную веб-службу.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="f3cd0-121">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="f3cd0-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f3cd0-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f3cd0-122">Running the test</span></span>

<span data-ttu-id="f3cd0-123">Командлет Test-Ксграупекспансион можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, который был включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="f3cd0-124">Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя тестируемого пула Lync Server и адрес электронной почты для действительной группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="f3cd0-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="f3cd0-126">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Lync Server, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="f3cd0-127">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда система вызывает Test-Ксграупекспансион:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f3cd0-128">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="f3cd0-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f3cd0-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="f3cd0-129">Determining success or failure</span></span>

<span data-ttu-id="f3cd0-130">Если указанный пользователь может использовать расширение группы, будет выведен результат, подобный следующему, с свойством Result, помеченным как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="f3cd0-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f3cd0-131">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="f3cd0-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="f3cd0-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3cd0-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3cd0-133">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f3cd0-133">Result : Success</span></span>

<span data-ttu-id="f3cd0-134">Задержка: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="f3cd0-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="f3cd0-135">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="f3cd0-135">Error :</span></span>

<span data-ttu-id="f3cd0-136">Диагност</span><span class="sxs-lookup"><span data-stu-id="f3cd0-136">Diagnosis :</span></span>

<span data-ttu-id="f3cd0-137">Если указанный пользователь не может использовать расширение группы, то результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f3cd0-138">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="f3cd0-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="f3cd0-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f3cd0-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f3cd0-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f3cd0-140">Result : Failure</span></span>

<span data-ttu-id="f3cd0-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f3cd0-141">Latency : 00:00:00</span></span>

<span data-ttu-id="f3cd0-142">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="f3cd0-142">Error :</span></span>

<span data-ttu-id="f3cd0-143">Диагност</span><span class="sxs-lookup"><span data-stu-id="f3cd0-143">Diagnosis :</span></span>

<span data-ttu-id="f3cd0-144">Test-Ксграупекспансион: не удалось зарегистрировать конечную точку.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="f3cd0-145">Обратитесь к разделу ErrorCode по определенному причине.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="f3cd0-146">Предыдущие выходные данные появлялись, что не удалось выполнить проверку, так как указанный пользователь не смог зарегистрироваться в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="f3cd0-147">Обычно это происходит, если тестовая учетная запись не существует или не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="f3cd0-148">Вы можете убедиться, что учетная запись существует, и определить, включена ли учетная запись для NM-OCS-14-3, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="f3cd0-149">Если Test-Ксграупекспансион завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="f3cd0-150">Если параметр verbose включен, Test-Ксграупекспансион будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f3cd0-151">Например, эти выходные данные указывают на то, что не удалось найти указанную группу рассылки:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="f3cd0-152">Попытка получить веб-билет.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-152">Trying to get web ticket.</span></span>

<span data-ttu-id="f3cd0-153">URL-адрес веб-службы:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="f3cd0-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="f3cd0-154">Использование проверки подлинности NTLM/Kerbtray.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="f3cd0-155">Жетвебтиккетактивити завершен.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="f3cd0-156">Начато действие "Верифидистрибутионлист".</span><span class="sxs-lookup"><span data-stu-id="f3cd0-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="f3cd0-157">Состояние ответа веб-службы ДЛКС: Нотфаунд.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="f3cd0-158">Действие ' Верифидистрибутионлист ' завершено в ' 0,2597923 ' сек.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f3cd0-159">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f3cd0-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="f3cd0-160">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-Ксграупекспансион:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="f3cd0-161">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-161">You specified an invalid user account.</span></span> <span data-ttu-id="f3cd0-162">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f3cd0-163">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f3cd0-164">Чтобы убедиться, что учетная запись пользователя была включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f3cd0-165">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f3cd0-166">Расширение группы может быть отключено.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-166">Group expansion might be disabled.</span></span> <span data-ttu-id="f3cd0-167">Можно отключить расширение группы.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="f3cd0-168">Если расширение группы было отключено, командлет Test-Ксграупекспансион завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f3cd0-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="f3cd0-169">Чтобы определить, включено ли расширение группы, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f3cd0-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>


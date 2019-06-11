---
title: 'Lync Server 2013: Проверка возможности развертывания групп'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="e085d-102">Тестирование возможности развертывания групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e085d-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e085d-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e085d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e085d-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e085d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e085d-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="e085d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e085d-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e085d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e085d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e085d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e085d-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="e085d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e085d-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="e085d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e085d-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксграупекспансион.</span><span class="sxs-lookup"><span data-stu-id="e085d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="e085d-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e085d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e085d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e085d-112">Description</span></span>

<span data-ttu-id="e085d-113">Командлет Test-Ксграупекспансион позволяет определить, работает ли расширение групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="e085d-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="e085d-114">Если включено расширение группы, пользователи настраивают группы рассылки как контакты.</span><span class="sxs-lookup"><span data-stu-id="e085d-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="e085d-115">Это означает, что пользователи смогут отправить одно и то же мгновенное сообщение всем участникам группы, направив сообщение группе, а не отдельным участникам этой группы.</span><span class="sxs-lookup"><span data-stu-id="e085d-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="e085d-116">Расширение групп позволяет быстро и легко просмотреть всех участников группы и их текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="e085d-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="e085d-117">С помощью командлета Test-Ксграупекспансион вы указываете группу рассылки Active Directory, используя адрес электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="e085d-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="e085d-118">После этого в Ксграупекспансион используется расширение группы, чтобы получить сведения о членстве в группах и сравнить полученный список с членством в указанном адресе электронной почты группы.</span><span class="sxs-lookup"><span data-stu-id="e085d-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="e085d-119">Если два списка соответствуют друг другу, то расширение группы работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e085d-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="e085d-120">Обратите внимание, что вы можете протестировать расширение группы двумя способами: Протестируйте саму службу или проверяя связанную веб-службу.</span><span class="sxs-lookup"><span data-stu-id="e085d-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="e085d-121">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="e085d-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e085d-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e085d-122">Running the test</span></span>

<span data-ttu-id="e085d-123">Командлет Test-Ксграупекспансион можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который был включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e085d-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="e085d-124">Для выполнения этой проверки с помощью тестовой учетной записи необходимо указать полное доменное имя тестируемого пула сервера Lync и адрес электронной почты для действительной группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="e085d-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="e085d-125">Например:</span><span class="sxs-lookup"><span data-stu-id="e085d-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="e085d-126">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Lync Server, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="e085d-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="e085d-127">Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда система вызывает Test-Ксграупекспансион:</span><span class="sxs-lookup"><span data-stu-id="e085d-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e085d-128">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксграупекспансион](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .</span><span class="sxs-lookup"><span data-stu-id="e085d-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e085d-129">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="e085d-129">Determining success or failure</span></span>

<span data-ttu-id="e085d-130">Если указанный пользователь может использовать расширение группы, вы будете получать выходные данные, аналогичные этим, с помощью свойства Result, помеченного как **успешно.**</span><span class="sxs-lookup"><span data-stu-id="e085d-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e085d-131">Таржетури:https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e085d-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="e085d-132">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e085d-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e085d-133">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="e085d-133">Result : Success</span></span>

<span data-ttu-id="e085d-134">Задержка: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="e085d-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="e085d-135">Ошибки</span><span class="sxs-lookup"><span data-stu-id="e085d-135">Error :</span></span>

<span data-ttu-id="e085d-136">Диагностик</span><span class="sxs-lookup"><span data-stu-id="e085d-136">Diagnosis :</span></span>

<span data-ttu-id="e085d-137">Если указанный пользователь не может использовать расширение группы, результат будет показан как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="e085d-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e085d-138">Таржетури:https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e085d-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="e085d-139">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e085d-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e085d-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="e085d-140">Result : Failure</span></span>

<span data-ttu-id="e085d-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e085d-141">Latency : 00:00:00</span></span>

<span data-ttu-id="e085d-142">Ошибки</span><span class="sxs-lookup"><span data-stu-id="e085d-142">Error :</span></span>

<span data-ttu-id="e085d-143">Диагностик</span><span class="sxs-lookup"><span data-stu-id="e085d-143">Diagnosis :</span></span>

<span data-ttu-id="e085d-144">Test-Ксграупекспансион: не удалось зарегистрировать конечную точку.</span><span class="sxs-lookup"><span data-stu-id="e085d-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="e085d-145">Ознакомьтесь с ErrorCode по конкретной причине.</span><span class="sxs-lookup"><span data-stu-id="e085d-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="e085d-146">В предыдущем выводе говорится, что тест завершился сбоем, так как указанный пользователь не смог зарегистрироваться в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e085d-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="e085d-147">Обычно это происходит, если учетная запись пользователя не существует или не включена в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e085d-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="e085d-148">Вы можете проверить существование учетной записи и определить, включена ли учетная запись для NM-OCS-14-3, выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="e085d-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="e085d-149">Если при выполнении теста-Ксграупекспансион происходит сбой, может потребоваться повторный запуск теста, в том числе параметр подробно:</span><span class="sxs-lookup"><span data-stu-id="e085d-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="e085d-150">При включенном параметре "подробный" — Ксграупекспансион возвращает пошаговые учетные записи всех действий, которые он пытался войти на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e085d-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e085d-151">Например, эти выходные данные указывают на то, что не удалось найти указанную группу рассылки:</span><span class="sxs-lookup"><span data-stu-id="e085d-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="e085d-152">Попытка получить веб-билет.</span><span class="sxs-lookup"><span data-stu-id="e085d-152">Trying to get web ticket.</span></span>

<span data-ttu-id="e085d-153">URL веб-службы:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="e085d-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="e085d-154">Использование проверки подлинности NTLM/керб.</span><span class="sxs-lookup"><span data-stu-id="e085d-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="e085d-155">Жетвебтиккетактивити завершен.</span><span class="sxs-lookup"><span data-stu-id="e085d-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="e085d-156">Начато действие "Верифидистрибутионлист".</span><span class="sxs-lookup"><span data-stu-id="e085d-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="e085d-157">Состояние ответа веб-службы ДЛКС: Нотфаунд.</span><span class="sxs-lookup"><span data-stu-id="e085d-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="e085d-158">Действие "Верифидистрибутионлист" завершено в течение "0,2597923" сек.</span><span class="sxs-lookup"><span data-stu-id="e085d-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e085d-159">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e085d-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="e085d-160">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Ксграупекспансион:</span><span class="sxs-lookup"><span data-stu-id="e085d-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="e085d-161">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="e085d-161">You specified an invalid user account.</span></span> <span data-ttu-id="e085d-162">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e085d-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e085d-163">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e085d-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e085d-164">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="e085d-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e085d-165">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e085d-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="e085d-166">Возможно, отключено расширение групп.</span><span class="sxs-lookup"><span data-stu-id="e085d-166">Group expansion might be disabled.</span></span> <span data-ttu-id="e085d-167">Можно отключить развертывание групп.</span><span class="sxs-lookup"><span data-stu-id="e085d-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="e085d-168">Если расширение группы было отключено, командлет Test-Ксграупекспансион завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="e085d-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="e085d-169">Чтобы определить, включено ли расширение группы, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e085d-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>


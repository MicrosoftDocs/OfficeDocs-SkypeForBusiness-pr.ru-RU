---
title: 'Lync Server 2013: тестирование веб-планировщика'
description: 'Lync Server 2013: тестирование веб-планировщика.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6512bf074078005eac66d1e4f5cd3d8ba2dc4bc7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556155"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="f5064-103">Тестирование веб-планировщика в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5064-103">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5064-104">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="f5064-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5064-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f5064-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f5064-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="f5064-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5064-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f5064-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f5064-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5064-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5064-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="f5064-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f5064-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5064-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f5064-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsWebScheduler</strong> .</span><span class="sxs-lookup"><span data-stu-id="f5064-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="f5064-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f5064-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f5064-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f5064-113">Description</span></span>

<span data-ttu-id="f5064-114">Командлет **Test-CsWebScheduler** позволяет определить, может ли определенный пользователь запланировать собрание с помощью веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="f5064-114">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="f5064-115">Веб-планировщик позволяет пользователям, не работающим в Outlook, планировать собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="f5064-115">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="f5064-116">Помимо прочего, эта новая функция (включающая в себя функциональные возможности средства веб-планировщика, включенного в пакет ресурсов Microsoft Lync Server 2010) позволяет пользователям выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f5064-116">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="f5064-117">Планирование нового собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="f5064-117">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="f5064-118">Отображение списка всех собраний, запланированных данным пользователем.</span><span class="sxs-lookup"><span data-stu-id="f5064-118">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="f5064-119">Просмотр и изменение существующего собрания.</span><span class="sxs-lookup"><span data-stu-id="f5064-119">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="f5064-120">Удаление существующего собрания.</span><span class="sxs-lookup"><span data-stu-id="f5064-120">Delete an existing meeting.</span></span>

  - <span data-ttu-id="f5064-121">Отправка приглашения участникам собрания по электронной почте с использованием предварительно настроенного почтового SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="f5064-121">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="f5064-122">Присоединение к существующей конференции.</span><span class="sxs-lookup"><span data-stu-id="f5064-122">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f5064-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f5064-123">Running the test</span></span>

<span data-ttu-id="f5064-124">В следующем примере проверяется веб-планировщик для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5064-124">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f5064-125">Эта команда будет работать только в том случае, если тестовые пользователи определены для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5064-125">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f5064-126">В этом случае команда определит, может ли первый тестовый пользователь планировать собрание по сети с помощью веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="f5064-126">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="f5064-127">Если тестовые пользователи не определены, команда завершится с ошибками, так как не будет определять, какой пользователь должен войти в систему.</span><span class="sxs-lookup"><span data-stu-id="f5064-127">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="f5064-128">Если тестовые пользователи не определены для пула, необходимо включить параметр UserSipAddress и учетные данные пользователя, который должна использовать команда при попытке входа в систему.</span><span class="sxs-lookup"><span data-stu-id="f5064-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f5064-129">Команды, показанные в следующем примере, проверяют возможность определенного пользователя (litwareinc \\ кенмэйер) для планирования собраний по сети с помощью веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="f5064-129">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="f5064-130">Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Ken Крюкова.</span><span class="sxs-lookup"><span data-stu-id="f5064-130">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="f5064-131">(Так как имя для входа litwareinc \\ кенмэйер включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Ken Крюкова.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="f5064-131">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="f5064-132">Вторая команда проверяет, может ли этот пользователь войти в пул atl-cs-001.litwareinc.com и запланировать собрание по сети.</span><span class="sxs-lookup"><span data-stu-id="f5064-132">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="f5064-133">Для запуска этой задачи вызывается командлет **Test-CsWebScheduler** вместе с тремя параметрами: TargetFqdn (полное доменное имя пула регистратора); UserCredential (объект Windows PowerShell, содержащий учетные данные пользователя Pilar Ackerman); и UserSipAddress (SIP-адрес, соответствующий предоставленным учетным данным пользователя).</span><span class="sxs-lookup"><span data-stu-id="f5064-133">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f5064-134">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="f5064-134">Determining success or failure</span></span>

<span data-ttu-id="f5064-135">Если веб-планировщик настроен правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.</span><span class="sxs-lookup"><span data-stu-id="f5064-135">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="f5064-136">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5064-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f5064-137">Целевой URI: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f5064-137">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="f5064-138">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="f5064-138">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="f5064-139">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f5064-139">Result : Success</span></span>

<span data-ttu-id="f5064-140">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f5064-140">Latency : 00:00:00</span></span>

<span data-ttu-id="f5064-141">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="f5064-141">Error Message :</span></span>

<span data-ttu-id="f5064-142">Диагност</span><span class="sxs-lookup"><span data-stu-id="f5064-142">Diagnosis :</span></span>

<span data-ttu-id="f5064-143">Если веб-планировщик настроен неправильно, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="f5064-143">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f5064-144">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="f5064-144">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="f5064-145">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f5064-145">domain name (FQDN).</span></span> <span data-ttu-id="f5064-146">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5064-146">Using default Registrar port number.</span></span> <span data-ttu-id="f5064-147">Возникновения</span><span class="sxs-lookup"><span data-stu-id="f5064-147">Exception:</span></span>

<span data-ttu-id="f5064-148">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="f5064-148">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="f5064-149">в</span><span class="sxs-lookup"><span data-stu-id="f5064-149">at</span></span>

<span data-ttu-id="f5064-150">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="f5064-150">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="f5064-151">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="f5064-151">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="f5064-152">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f5064-152">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f5064-153">Целевой URI:</span><span class="sxs-lookup"><span data-stu-id="f5064-153">Target Uri :</span></span>

<span data-ttu-id="f5064-154">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f5064-154">Result : Failure</span></span>

<span data-ttu-id="f5064-155">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f5064-155">Latency : 00:00:00</span></span>

<span data-ttu-id="f5064-156">Сообщение об ошибке: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="f5064-156">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="f5064-157">Диагност</span><span class="sxs-lookup"><span data-stu-id="f5064-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f5064-158">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f5064-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="f5064-159">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsWebScheduler** :</span><span class="sxs-lookup"><span data-stu-id="f5064-159">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="f5064-160">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f5064-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f5064-161">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f5064-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f5064-162">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="f5064-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f5064-163">Эта команда завершится с ошибками, если веб-планировщик неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="f5064-163">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5064-164">См. также</span><span class="sxs-lookup"><span data-stu-id="f5064-164">See Also</span></span>


[<span data-ttu-id="f5064-165">Set — Ксвебсервер</span><span class="sxs-lookup"><span data-stu-id="f5064-165">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


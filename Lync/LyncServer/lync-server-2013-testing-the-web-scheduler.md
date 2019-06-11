---
title: 'Lync Server 2013: Проверка веб-планировщика'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="a352a-102">Проверка веб-планировщика в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a352a-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a352a-103">_**Тема последнего изменения:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a352a-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a352a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="a352a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a352a-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="a352a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a352a-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="a352a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a352a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a352a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a352a-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="a352a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a352a-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="a352a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a352a-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксвебсчедулер</strong> .</span><span class="sxs-lookup"><span data-stu-id="a352a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="a352a-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a352a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a352a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a352a-112">Description</span></span>

<span data-ttu-id="a352a-113">Командлет **Test-ксвебсчедулер** позволяет определить, может ли определенный пользователь запланировать собрание с помощью веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="a352a-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="a352a-114">Веб-планировщик позволяет пользователям, которые не запущены в Outlook, планировать собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="a352a-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="a352a-115">Помимо прочего, эта новая функция (которая включает в себя функцию, обнаруженную в средстве веб-планировщика, которая входит в состав набора Microsoft Lync Server 2010 Resource Kit), позволяет пользователям:</span><span class="sxs-lookup"><span data-stu-id="a352a-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="a352a-116">Планирование нового собрания по сети.</span><span class="sxs-lookup"><span data-stu-id="a352a-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="a352a-117">Список всех собраний, для которых он запланирован.</span><span class="sxs-lookup"><span data-stu-id="a352a-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="a352a-118">Просмотр и изменение существующего собрания.</span><span class="sxs-lookup"><span data-stu-id="a352a-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="a352a-119">Удаление существующего собрания.</span><span class="sxs-lookup"><span data-stu-id="a352a-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="a352a-120">Отправьте приглашение по электронной почте участникам собрания с помощью предварительно настроенного почтового сервера SMTP.</span><span class="sxs-lookup"><span data-stu-id="a352a-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="a352a-121">Присоединиться к существующей конференции.</span><span class="sxs-lookup"><span data-stu-id="a352a-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a352a-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="a352a-122">Running the test</span></span>

<span data-ttu-id="a352a-123">В следующем примере показана проверка веб-планировщика для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a352a-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a352a-124">Эта команда будет работать только в том случае, если тестовые пользователи определены для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a352a-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a352a-125">Если это так, команда определит, может ли первый тестовый пользователь запланировать собрание по сети с помощью веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="a352a-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="a352a-126">Если тестовые пользователи не заданы, команда завершится сбоем, так как не будет определять, какой пользователь должен войти в систему.</span><span class="sxs-lookup"><span data-stu-id="a352a-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="a352a-127">Если вы не определили тестовых пользователей для пула, необходимо включить параметр Усерсипаддресс и учетные данные пользователя, который должна использовать команда при попытке входа в систему.</span><span class="sxs-lookup"><span data-stu-id="a352a-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="a352a-128">Команды, показанные в следующем примере, проверяют возможность определенного пользователя (плана litwareinc\\кенмэйер), чтобы запланировать собрание по сети с помощью веб-планировщика.</span><span class="sxs-lookup"><span data-stu-id="a352a-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="a352a-129">Для этого в первой команде примера используется командлет **Get-Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, который содержит имя и пароль пользователя Кен Мэйер.</span><span class="sxs-lookup"><span data-stu-id="a352a-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="a352a-130">(Поскольку имя для входа плана litwareinc\\кенмэйер входит в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи Кен Мэйер.) Полученный объект учетных данных затем сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="a352a-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="a352a-131">Вторая команда проверяет, может ли пользователь войти в пул atl-cs-001.litwareinc.com и запланировать собрание по сети.</span><span class="sxs-lookup"><span data-stu-id="a352a-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="a352a-132">Для выполнения этой задачи вызывается командлет **Test-ксвебсчедулер** , вместе с тремя параметрами: таржетфкдн (полное доменное имя пула регистраторов). Усеркредентиал (объект Windows PowerShell, который включает в себя учетные данные пользователя для почтового Вронский); и Усерсипаддресс (SIP-адрес, соответствующий предоставленным учетным данным пользователя).</span><span class="sxs-lookup"><span data-stu-id="a352a-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a352a-133">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="a352a-133">Determining success or failure</span></span>

<span data-ttu-id="a352a-134">Если веб-планировщик настроен правильно, вы получите вывод, аналогичный приведенному ниже, и свойство Result помечается как **успешно**.</span><span class="sxs-lookup"><span data-stu-id="a352a-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="a352a-135">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a352a-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a352a-136">Конечный URI: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a352a-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="a352a-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="a352a-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="a352a-138">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="a352a-138">Result : Success</span></span>

<span data-ttu-id="a352a-139">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a352a-139">Latency : 00:00:00</span></span>

<span data-ttu-id="a352a-140">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="a352a-140">Error Message :</span></span>

<span data-ttu-id="a352a-141">Диагностик</span><span class="sxs-lookup"><span data-stu-id="a352a-141">Diagnosis :</span></span>

<span data-ttu-id="a352a-142">Если веб-планировщик настроен неправильно, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="a352a-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a352a-143">Предупреждение: не удалось прочитать номер порта регистратора для заданного полного имени</span><span class="sxs-lookup"><span data-stu-id="a352a-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a352a-144">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a352a-144">domain name (FQDN).</span></span> <span data-ttu-id="a352a-145">С помощью номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a352a-145">Using default Registrar port number.</span></span> <span data-ttu-id="a352a-146">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a352a-146">Exception:</span></span>

<span data-ttu-id="a352a-147">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="a352a-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a352a-148">скорость</span><span class="sxs-lookup"><span data-stu-id="a352a-148">at</span></span>

<span data-ttu-id="a352a-149">Microsoft. RTC. Management. Синсетиктрансактионс. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="a352a-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a352a-150">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="a352a-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a352a-151">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a352a-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a352a-152">Конечный URI:</span><span class="sxs-lookup"><span data-stu-id="a352a-152">Target Uri :</span></span>

<span data-ttu-id="a352a-153">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="a352a-153">Result : Failure</span></span>

<span data-ttu-id="a352a-154">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a352a-154">Latency : 00:00:00</span></span>

<span data-ttu-id="a352a-155">Сообщение об ошибке: подходящие кластеры не найдены в топологии.</span><span class="sxs-lookup"><span data-stu-id="a352a-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="a352a-156">Диагностик</span><span class="sxs-lookup"><span data-stu-id="a352a-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a352a-157">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="a352a-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="a352a-158">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксвебсчедулер** :</span><span class="sxs-lookup"><span data-stu-id="a352a-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="a352a-159">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="a352a-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a352a-160">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="a352a-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a352a-161">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="a352a-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a352a-162">Эта команда завершится сбоем, если веб-планировщик неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="a352a-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a352a-163">См. также</span><span class="sxs-lookup"><span data-stu-id="a352a-163">See Also</span></span>


[<span data-ttu-id="a352a-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="a352a-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


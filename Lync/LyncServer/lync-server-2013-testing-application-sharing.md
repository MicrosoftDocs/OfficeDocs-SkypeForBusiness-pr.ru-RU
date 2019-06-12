---
title: 'Lync Server 2013: тестирование общего доступ к приложениям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="9138e-102">Тестирование общего обмена приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9138e-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9138e-103">_**Тема последнего изменения:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="9138e-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9138e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="9138e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9138e-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="9138e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9138e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="9138e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9138e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9138e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9138e-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="9138e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9138e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="9138e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9138e-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксасконференце.</span><span class="sxs-lookup"><span data-stu-id="9138e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="9138e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9138e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9138e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9138e-112">Description</span></span>

<span data-ttu-id="9138e-113">Командлет **Test-ксасконференце** удостоверяется в том, что пользователь может принимать участие в собрании по сети, включающего общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="9138e-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="9138e-114">Для этого командлет регистрирует двух пользователей с помощью Lync Server 2013, а затем использует одну из учетных записей пользователей для создания новой конференции, которая включает общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="9138e-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="9138e-115">Затем командлет проверяет, что второй пользователь может присоединиться к этой Конференции.</span><span class="sxs-lookup"><span data-stu-id="9138e-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9138e-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="9138e-116">Running the test</span></span>

<span data-ttu-id="9138e-117">Команда, показанная в примере 1, подтверждает, что Конференция для совместного использования приложений может быть проведена в пуле atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9138e-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9138e-118">В этой команде предполагается, что вы настроили пару тестовых пользователей для указанного пула.</span><span class="sxs-lookup"><span data-stu-id="9138e-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="9138e-119">Если таких тестовых пользователей не существует, команда завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="9138e-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9138e-120">В примере 2 проверяются возможности службы запуска присоединения присоединиться к Конференции для совместного использования приложений в пуле atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9138e-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9138e-121">Обратите внимание, что эта команда проверяет только саму службу. для выполнения команды не требуются мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="9138e-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="9138e-122">Команды, показанные в примере 2, проверяют возможности пары пользователей (плана litwareinc\\почтового и плана litwareinc\\кенмер) для входа на сервер Lync Server 2013 и проведения конференции для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="9138e-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="9138e-123">Для этого в первой команде примера используется командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя почтового Вронский.</span><span class="sxs-lookup"><span data-stu-id="9138e-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="9138e-124">(Так как имя для входа,\\плана litwareinc почтового, включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи почтового Вронский.) Полученный объект учетных данных затем сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="9138e-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="9138e-125">Вторая команда — это то же самое, что возвращает объект учетной записи Кен мер.</span><span class="sxs-lookup"><span data-stu-id="9138e-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="9138e-126">Если у вас есть объекты учетных данных в руки, третья команда определяет, могут ли эти пользователи войти в Lync Server 2013 и провести Конференц-связь приложения.</span><span class="sxs-lookup"><span data-stu-id="9138e-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="9138e-127">Для выполнения этой задачи вызывается командлет **Test-ксасконференце** , а также следующие параметры: таржетфкдн (полное доменное имя пула регистраторов). Сендерсипаддресс (адрес SIP для первого тестового пользователя); Сендеркредентиал (объект Windows PowerShell с учетными данными для этого пользователя); Рецеиверсипаддресс (SIP-адрес для другого тестового пользователя); и Рецеиверкредентиал (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).</span><span class="sxs-lookup"><span data-stu-id="9138e-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9138e-128">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="9138e-128">Determining success or failure</span></span>

<span data-ttu-id="9138e-129">Если вы правильно настроили общий доступ к приложениям, вы получите вывод примерно так, чтобы свойство Result пометило **"успешно".**</span><span class="sxs-lookup"><span data-stu-id="9138e-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9138e-130">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9138e-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9138e-131">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="9138e-131">Result : Success</span></span>

<span data-ttu-id="9138e-132">Задержка: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="9138e-132">Latency : 00:00:01</span></span>

<span data-ttu-id="9138e-133">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="9138e-133">Error Message :</span></span>

<span data-ttu-id="9138e-134">Диагностик</span><span class="sxs-lookup"><span data-stu-id="9138e-134">Diagnosis :</span></span>

<span data-ttu-id="9138e-135">Если указанные пользователи не могут предоставлять общий доступ к приложениям, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="9138e-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9138e-136">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9138e-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9138e-137">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="9138e-137">Result : Failure</span></span>

<span data-ttu-id="9138e-138">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9138e-138">Latency : 00:00:00</span></span>

<span data-ttu-id="9138e-139">Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="9138e-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="9138e-140">не отвечает на запросы в течение определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="9138e-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="9138e-141">не удалось установить соединение, так как подключенный узел имеет</span><span class="sxs-lookup"><span data-stu-id="9138e-141">established connection failed because connected host has</span></span>

<span data-ttu-id="9138e-142">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="9138e-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9138e-143">Внутреннее исключение: сбой при попытке подключения из-за того, что</span><span class="sxs-lookup"><span data-stu-id="9138e-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="9138e-144">связь с абонентом завершилась неправильно после определенного периода</span><span class="sxs-lookup"><span data-stu-id="9138e-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="9138e-145">время или соединение не удалось установить, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="9138e-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="9138e-146">не удалось ответить 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="9138e-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9138e-147">Диагностик</span><span class="sxs-lookup"><span data-stu-id="9138e-147">Diagnosis :</span></span>

<span data-ttu-id="9138e-148">Например, в предыдущем выводе есть Примечание "подключенная сторона не ответила должным образом", которая обычно указывает на проблему с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="9138e-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9138e-149">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="9138e-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="9138e-150">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксасконференце** :</span><span class="sxs-lookup"><span data-stu-id="9138e-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="9138e-151">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="9138e-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9138e-152">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="9138e-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9138e-153">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="9138e-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9138e-154">Эта команда завершится сбоем, если пользователям теста была назначена политика конференц-связи, не позволяющая использовать общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="9138e-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="9138e-155">Эта команда завершается сбоем, если граничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="9138e-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9138e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="9138e-156">See Also</span></span>


[<span data-ttu-id="9138e-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="9138e-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="9138e-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="9138e-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


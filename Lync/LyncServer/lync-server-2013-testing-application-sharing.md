---
title: 'Lync Server 2013: тестирование общего доступа к приложениям'
description: 'Lync Server 2013: тестирование общего доступа к приложениям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560725"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="ae829-103">Тестирование общего доступа к приложениям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae829-103">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae829-104">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ae829-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae829-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="ae829-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ae829-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="ae829-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae829-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="ae829-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ae829-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae829-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae829-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="ae829-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ae829-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ae829-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ae829-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsASConference.</span><span class="sxs-lookup"><span data-stu-id="ae829-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="ae829-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae829-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ae829-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ae829-113">Description</span></span>

<span data-ttu-id="ae829-114">Командлет **Test-CsASConference** проверяет, может ли пользователь, который является членом тестовой конференции, участвовать в интерактивной конференции, включающей общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="ae829-114">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="ae829-115">Для этого командлет регистрирует двух пользователей с помощью Lync Server 2013, а затем использует одну из учетных записей пользователей для создания новой конференции, включающей общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="ae829-115">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="ae829-116">Затем командлет проверяет, может ли второй пользователь присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="ae829-116">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ae829-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="ae829-117">Running the test</span></span>

<span data-ttu-id="ae829-p103">Команда, показанная в примере 1, проверяет, может ли конференция с общим доступом к приложениям проводиться в пуле atl-cs-001.litwareinc.com. Перед выполнением команды необходимо предварительно настроить пару тестовых пользователей для указанного пула. Если эти тестовые пользователи не существуют, команда завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="ae829-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ae829-p104">В примере 2 проверяется, может ли компонент обеспечения процесса присоединения подключиться к конференции с общим доступом к приложениям в пуле atl-cs-001.litwareinc.com. Обратите внимание на то, что эта команда проверяет только сам компонент. Для ее выполнения мобильные устройства не требуются.</span><span class="sxs-lookup"><span data-stu-id="ae829-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="ae829-123">Команды, показанные в примере 2, проверяют возможность использования пользователями (litwareinc \\ Pilar и litwareinc \\ kenmyer) для входа в Lync Server 2013, а затем выполняют Конференц-связь с приложением.</span><span class="sxs-lookup"><span data-stu-id="ae829-123">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="ae829-124">Для этого первая команда в примере использует командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="ae829-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="ae829-125">(Так как имя для входа, litwareinc \\ Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="ae829-125">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="ae829-126">Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="ae829-126">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="ae829-127">Если у вас есть объекты учетных данных в наличии, третья команда определяет, могут ли эти два пользователя войти в Lync Server 2013 и провести конференц-совместный доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="ae829-127">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="ae829-128">Для выполнения этой задачи вызывается командлет **Test-CsASConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); SenderSipAddress (SIP-адрес для первого тестового пользователя); SenderCredential (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ReceiverSipAddress (SIP-адрес для другого тестового пользователя); и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).</span><span class="sxs-lookup"><span data-stu-id="ae829-128">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ae829-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="ae829-129">Determining success or failure</span></span>

<span data-ttu-id="ae829-130">Если общий доступ к приложениям настроен правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="ae829-130">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ae829-131">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ae829-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ae829-132">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="ae829-132">Result : Success</span></span>

<span data-ttu-id="ae829-133">Задержка: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="ae829-133">Latency : 00:00:01</span></span>

<span data-ttu-id="ae829-134">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="ae829-134">Error Message :</span></span>

<span data-ttu-id="ae829-135">Диагност</span><span class="sxs-lookup"><span data-stu-id="ae829-135">Diagnosis :</span></span>

<span data-ttu-id="ae829-136">Если указанные пользователи не могут совместно использовать приложения, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="ae829-136">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ae829-137">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ae829-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ae829-138">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="ae829-138">Result : Failure</span></span>

<span data-ttu-id="ae829-139">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ae829-139">Latency : 00:00:00</span></span>

<span data-ttu-id="ae829-140">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="ae829-140">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ae829-141">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="ae829-141">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ae829-142">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="ae829-142">established connection failed because connected host has</span></span>

<span data-ttu-id="ae829-143">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="ae829-143">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ae829-144">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="ae829-144">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ae829-145">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="ae829-145">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ae829-146">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="ae829-146">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ae829-147">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="ae829-147">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ae829-148">Диагност</span><span class="sxs-lookup"><span data-stu-id="ae829-148">Diagnosis :</span></span>

<span data-ttu-id="ae829-149">Например, в примере выше приведена заметка "подключенная сторона не ответила", которая обычно указывает на проблему с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="ae829-149">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ae829-150">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="ae829-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="ae829-151">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsASConference** :</span><span class="sxs-lookup"><span data-stu-id="ae829-151">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="ae829-152">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="ae829-152">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ae829-153">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="ae829-153">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ae829-154">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="ae829-154">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ae829-155">Эта команда завершится с ошибками, если тестовым пользователям была назначена политика конференц-связи, которая не позволяет использовать общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="ae829-155">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="ae829-156">Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="ae829-156">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae829-157">См. также</span><span class="sxs-lookup"><span data-stu-id="ae829-157">See Also</span></span>


[<span data-ttu-id="ae829-158">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="ae829-158">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="ae829-159">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="ae829-159">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Проверка общего доступа в конференциях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a98312c04b943d485e1c6668b1c9347c9714e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="f05e5-102">Тестирование общего доступа в конференциях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f05e5-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f05e5-103">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="f05e5-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f05e5-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f05e5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f05e5-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="f05e5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f05e5-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f05e5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f05e5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f05e5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f05e5-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="f05e5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f05e5-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f05e5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f05e5-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsDataConference</strong> .</span><span class="sxs-lookup"><span data-stu-id="f05e5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="f05e5-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f05e5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f05e5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f05e5-112">Description</span></span>

<span data-ttu-id="f05e5-113">В Lync Server 2013 конференц-связи с данными — это любая конференция, в которой используются операции сотрудничества, такие как доска или заметки.</span><span class="sxs-lookup"><span data-stu-id="f05e5-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="f05e5-114">Командлет **Test-CsDataConference** позволяет проверить, могут ли две пользователи принять участие в конференции с данными.</span><span class="sxs-lookup"><span data-stu-id="f05e5-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f05e5-115">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f05e5-115">Running the test</span></span>

<span data-ttu-id="f05e5-p103">Команда, показанная в примере 1, проверяет, может ли конференция для совместной работы с данными проводиться в пуле atl-cs-001.litwareinc.com. Перед выполнением команды необходимо предварительно настроить пару тестовых пользователей для указанного пула. Если эти тестовые пользователи не существуют, команда завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="f05e5-p103">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="f05e5-119">Команды, показанные в примере 2, проверяют возможность использования пользователями двух пользователей (\\litwareinc Pilar и\\litwareinc kenmyer) для входа в Lync Server 2013 и проведения Конференции с данными.</span><span class="sxs-lookup"><span data-stu-id="f05e5-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="f05e5-120">Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="f05e5-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="f05e5-121">(Так как имя для входа,\\litwareinc Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="f05e5-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="f05e5-122">Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f05e5-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="f05e5-123">Если у вас есть объекты учетных данных в наличии, третья команда определяет, могут ли эти два пользователя войти в Lync Server 2013 и провести конференц-передачу данных.</span><span class="sxs-lookup"><span data-stu-id="f05e5-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="f05e5-124">Для выполнения этой задачи вызывается командлет **Test-CsDataConference** , а также следующие параметры: TargetFqdn (полное доменное имя пула регистратора); SenderSipAddress (SIP-адрес для первого тестового пользователя); SenderCredential (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ReceiverSipAddress (SIP-адрес для другого тестового пользователя); и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).</span><span class="sxs-lookup"><span data-stu-id="f05e5-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f05e5-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="f05e5-125">Determining success or failure</span></span>

<span data-ttu-id="f05e5-126">Если Конференц-связь с данными настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="f05e5-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f05e5-127">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f05e5-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f05e5-128">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f05e5-128">Result : Success</span></span>

<span data-ttu-id="f05e5-129">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f05e5-129">Latency : 00:00:00</span></span>

<span data-ttu-id="f05e5-130">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="f05e5-130">Error Message :</span></span>

<span data-ttu-id="f05e5-131">Диагност</span><span class="sxs-lookup"><span data-stu-id="f05e5-131">Diagnosis :</span></span>

<span data-ttu-id="f05e5-132">Если указанные пользователи не могут использовать общий доступ к данным, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="f05e5-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f05e5-133">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f05e5-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f05e5-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f05e5-134">Result : Failure</span></span>

<span data-ttu-id="f05e5-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f05e5-135">Latency : 00:00:00</span></span>

<span data-ttu-id="f05e5-136">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="f05e5-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="f05e5-137">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="f05e5-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="f05e5-138">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="f05e5-138">established connection failed because connected host has</span></span>

<span data-ttu-id="f05e5-139">не удалось ответить \[на 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="f05e5-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="f05e5-140">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="f05e5-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="f05e5-141">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="f05e5-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="f05e5-142">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="f05e5-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="f05e5-143">не отвечает</span><span class="sxs-lookup"><span data-stu-id="f05e5-143">has failed to respond</span></span>

<span data-ttu-id="f05e5-144">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="f05e5-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="f05e5-145">Диагност</span><span class="sxs-lookup"><span data-stu-id="f05e5-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f05e5-146">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f05e5-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="f05e5-147">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsDataConference** :</span><span class="sxs-lookup"><span data-stu-id="f05e5-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="f05e5-148">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f05e5-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f05e5-149">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f05e5-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f05e5-150">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="f05e5-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f05e5-151">Возможность проведения Конференции с данными зависит от политики конференц-связи, назначенной пользователю, который организует конференцию (в случае командлета **Test-CsDataConference** , который является "отправителем").</span><span class="sxs-lookup"><span data-stu-id="f05e5-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="f05e5-152">Если организатор не может включать в свое собрание действия для совместной работы (например, если для свойства Енабледатаколлаборатион в политике конференц-связи задано значение false), командлет **Test-CsDataConference** завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f05e5-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="f05e5-153">Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="f05e5-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


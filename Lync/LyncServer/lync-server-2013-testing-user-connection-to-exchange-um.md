---
title: 'Lync Server 2013: тестирование подключения пользователя к единой системе обмена сообщениями Exchange'
description: 'Lync Server 2013: тестирование подключения пользователя к единой системе обмена сообщениями Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556071"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="d65ff-103">Тестирование подключения пользователя к единой системе обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d65ff-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d65ff-104">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="d65ff-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d65ff-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="d65ff-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d65ff-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="d65ff-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d65ff-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="d65ff-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d65ff-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d65ff-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d65ff-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="d65ff-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d65ff-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d65ff-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d65ff-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExUMConnectivity</strong> .</span><span class="sxs-lookup"><span data-stu-id="d65ff-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="d65ff-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d65ff-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d65ff-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d65ff-113">Description</span></span>

<span data-ttu-id="d65ff-114">Командлет **Test-CsExUMConnectivity** проверяет, может ли указанный пользователь подключаться к службе единой системы обмена сообщениями Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d65ff-114">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="d65ff-115">Обратите внимание, что этот командлет проверяет только то, что для службы можно установить подключение.</span><span class="sxs-lookup"><span data-stu-id="d65ff-115">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="d65ff-116">Он не проверяет саму службу.</span><span class="sxs-lookup"><span data-stu-id="d65ff-116">It does not test the service itself.</span></span> <span data-ttu-id="d65ff-117">Чтобы протестировать службу единой системы обмена сообщениями (запустив командлет искусственной транзакции, который оставляет сообщение голосовой почты в почтовом ящике пользователя), используйте командлет Test-CsExUMVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="d65ff-117">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d65ff-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="d65ff-118">Running the test</span></span>

<span data-ttu-id="d65ff-119">В следующем примере показано, как проверить подключение единой системы обмена сообщениями Exchange для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d65ff-119">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="d65ff-120">Эта команда будет работать только в том случае, если тестовые пользователи были определены для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d65ff-120">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="d65ff-121">В этом случае команда определит, может ли первый тестовый пользователь подключаться к единой системе обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d65ff-121">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="d65ff-122">Если тестовые пользователи не были настроены для пула, команда завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="d65ff-122">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="d65ff-123">Команды, показанные в следующем примере, проверяют подключение единой системы обмена сообщениями Exchange для пользователя litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="d65ff-123">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="d65ff-124">Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell для пользователя litwareinc \\ kenmyer.</span><span class="sxs-lookup"><span data-stu-id="d65ff-124">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="d65ff-125">Обратите внимание, что для этой учетной записи необходимо указать пароль, чтобы создать допустимый объект учетных данных и убедиться, что командлет **Test-CsExUMConnectivity** может выполнить его проверку.</span><span class="sxs-lookup"><span data-stu-id="d65ff-125">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="d65ff-126">Вторая команда в примере использует предоставленный объект учетных данных ($x) и SIP-адрес пользователя litwareinc kenmyer, \\ чтобы определить, может ли этот пользователь подключиться к единой системе обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="d65ff-126">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d65ff-127">Команда, показанная в следующем примере, является вариантом только что показанной команды.</span><span class="sxs-lookup"><span data-stu-id="d65ff-127">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="d65ff-128">В этом случае параметр OutLoggerVariable включается для создания подробного журнала каждого шага, выполняемого с помощью **Test-CsExUMConnectivity** , кмдлетанд успешное или неуспешное выполнение каждого из этих действий.</span><span class="sxs-lookup"><span data-stu-id="d65ff-128">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="d65ff-129">Для этого параметр OutLoggerVariable добавляется вместе со значением параметра Ексумтекст; Это приводит к тому, что подробные сведения о ведении журнала хранятся в переменной с именем $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="d65ff-129">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="d65ff-130">В завершающей команде в примере метод ToXML () используется для преобразования данных журнала в формат XML.</span><span class="sxs-lookup"><span data-stu-id="d65ff-130">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="d65ff-131">После этого XML-данные записываются в файл с именем C: \\ Logs \\ExumTest.xml с помощью командлета Out-File.</span><span class="sxs-lookup"><span data-stu-id="d65ff-131">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d65ff-132">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="d65ff-132">Determining success or failure</span></span>

<span data-ttu-id="d65ff-133">Если интеграция Exchange настроена правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.</span><span class="sxs-lookup"><span data-stu-id="d65ff-133">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="d65ff-134">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d65ff-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d65ff-135">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="d65ff-135">Result : Success</span></span>

<span data-ttu-id="d65ff-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d65ff-136">Latency : 00:00:00</span></span>

<span data-ttu-id="d65ff-137">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="d65ff-137">Error Message :</span></span>

<span data-ttu-id="d65ff-138">Диагност</span><span class="sxs-lookup"><span data-stu-id="d65ff-138">Diagnosis :</span></span>

<span data-ttu-id="d65ff-139">Если указанный пользователь не может получать уведомления, результат будет отображаться как **сбой**, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="d65ff-139">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d65ff-140">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d65ff-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d65ff-141">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="d65ff-141">Result : Failure</span></span>

<span data-ttu-id="d65ff-142">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d65ff-142">Latency : 00:00:00</span></span>

<span data-ttu-id="d65ff-143">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="d65ff-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="d65ff-144">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="d65ff-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="d65ff-145">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="d65ff-145">established connection failed because connected host has</span></span>

<span data-ttu-id="d65ff-146">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="d65ff-146">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="d65ff-147">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="d65ff-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="d65ff-148">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="d65ff-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="d65ff-149">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="d65ff-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="d65ff-150">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="d65ff-150">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="d65ff-151">Диагност</span><span class="sxs-lookup"><span data-stu-id="d65ff-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d65ff-152">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="d65ff-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="d65ff-153">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExUMConnectivity** :</span><span class="sxs-lookup"><span data-stu-id="d65ff-153">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="d65ff-154">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="d65ff-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="d65ff-155">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="d65ff-155">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="d65ff-156">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="d65ff-156">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="d65ff-157">Эта команда завершится с ошибками, если сервер Exchange неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="d65ff-157">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="d65ff-158">Если сервер Exchange недостижим по сети, эта команда завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="d65ff-158">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d65ff-159">См. также</span><span class="sxs-lookup"><span data-stu-id="d65ff-159">See Also</span></span>


[<span data-ttu-id="d65ff-160">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="d65ff-160">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


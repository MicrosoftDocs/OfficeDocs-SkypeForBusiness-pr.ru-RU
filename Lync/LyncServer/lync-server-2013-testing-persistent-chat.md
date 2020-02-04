---
title: 'Lync Server 2013: Проверка сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="8d5c3-102">Проверка сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d5c3-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d5c3-103">_**Тема последнего изменения:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="8d5c3-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d5c3-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="8d5c3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8d5c3-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="8d5c3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d5c3-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="8d5c3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8d5c3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d5c3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d5c3-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="8d5c3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8d5c3-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8d5c3-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксперсистентчатмессаже</strong> .</span><span class="sxs-lookup"><span data-stu-id="8d5c3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="8d5c3-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d5c3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8d5c3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8d5c3-112">Description</span></span>

<span data-ttu-id="8d5c3-113">Командлет **Test-ксперсистентчатмессаже** удостоверяется в том, что с помощью службы сохраняемого чата пользователи могут обмениваться сообщениями с другими тестами.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="8d5c3-114">Для этого командлет заносит двух пользователей на Lync Server 2013, подключает пользователей к сохраняемой комнате чата, обменивается сообщениями, а затем выходит из комнаты чата и завершает работу двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="8d5c3-115">Обратите внимание на то, что если вы не создали комнаты чата или если у двух тестовых учетных записей не назначена политика сохраняемого чата, которая предоставляет им доступ к службе сохраняемого чата, следует отметить, что вызов этого командлета завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8d5c3-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="8d5c3-116">Running the test</span></span>

<span data-ttu-id="8d5c3-117">Команды, показанные в приведенном ниже примере, проверяют возможность подключения к серверу Lync\\Server 2013 (\\плана litwareinc почтового и плана litwareinc кенмер), а затем обмен сообщениями с помощью службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="8d5c3-118">Для этого в первой команде примера используется командлет **Get-Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя почтового Вронский.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="8d5c3-119">(Поскольку имя для входа, плана litwareinc\\почтового, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи почтового Вронский.) Результирующий объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="8d5c3-120">Вторая команда — это то же самое, что возвращает объект учетной записи Кен мер.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="8d5c3-121">Если у вас есть объекты учетных данных, третья команда определяет, могут ли эти два пользователя входить на сервер Lync Server 2013 и обмениваться сообщениями с помощью сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="8d5c3-122">Для выполнения этой задачи командлет **Test-ксперсистентчатмессаже** вызывается с помощью следующих параметров: таржетфкдн (полное доменное имя пула регистраторов). Сендерсипаддресс (адрес SIP для первого тестового пользователя); Сендеркредентиал (объект Windows PowerShell, который включает в себя учетные данные для этого пользователя); Рецеиверсипаддресс (SIP-адрес для другого тестового пользователя); и Рецеиверкредентиал (объект Windows PowerShell, который включает в себя учетные данные для другого тестового пользователя).</span><span class="sxs-lookup"><span data-stu-id="8d5c3-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8d5c3-123">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="8d5c3-123">Determining success or failure</span></span>

<span data-ttu-id="8d5c3-124">Если указанный пользователь имеет действующую политику расположения, вы получите вывод, как показано ниже, и свойство Result, помеченное как **успешно**.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="8d5c3-125">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8d5c3-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8d5c3-126">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="8d5c3-126">Result : Success</span></span>

<span data-ttu-id="8d5c3-127">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8d5c3-127">Latency : 00:00:00</span></span>

<span data-ttu-id="8d5c3-128">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="8d5c3-128">Error Message :</span></span>

<span data-ttu-id="8d5c3-129">Диагностик</span><span class="sxs-lookup"><span data-stu-id="8d5c3-129">Diagnosis :</span></span>

<span data-ttu-id="8d5c3-130">Если указанные пользователи не могут обмениваться сообщениями с помощью службы "сохраняемый чат", результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8d5c3-131">Предупреждение: не удалось прочитать номер порта регистратора для заданного полного имени</span><span class="sxs-lookup"><span data-stu-id="8d5c3-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="8d5c3-132">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="8d5c3-132">domain name (FQDN).</span></span> <span data-ttu-id="8d5c3-133">С помощью номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-133">Using default Registrar port number.</span></span> <span data-ttu-id="8d5c3-134">Ошибка</span><span class="sxs-lookup"><span data-stu-id="8d5c3-134">Exception:</span></span>

<span data-ttu-id="8d5c3-135">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="8d5c3-136">скорость</span><span class="sxs-lookup"><span data-stu-id="8d5c3-136">at</span></span>

<span data-ttu-id="8d5c3-137">Microsoft. RTC. Management. Синсетиктрансактионс. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="8d5c3-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="8d5c3-138">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="8d5c3-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="8d5c3-139">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8d5c3-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8d5c3-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="8d5c3-140">Result : Failure</span></span>

<span data-ttu-id="8d5c3-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8d5c3-141">Latency : 00:00:00</span></span>

<span data-ttu-id="8d5c3-142">Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="8d5c3-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="8d5c3-143">не отвечает на запросы в течение определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="8d5c3-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="8d5c3-144">не удалось установить соединение, так как подключенный узел имеет</span><span class="sxs-lookup"><span data-stu-id="8d5c3-144">established connection failed because connected host has</span></span>

<span data-ttu-id="8d5c3-145">не удалось ответить \[на 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="8d5c3-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="8d5c3-146">Внутреннее исключение: сбой при попытке подключения из-за того, что</span><span class="sxs-lookup"><span data-stu-id="8d5c3-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="8d5c3-147">связь с абонентом завершилась неправильно после определенного периода</span><span class="sxs-lookup"><span data-stu-id="8d5c3-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="8d5c3-148">время или соединение не удалось установить, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="8d5c3-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="8d5c3-149">не отвечает</span><span class="sxs-lookup"><span data-stu-id="8d5c3-149">has failed to respond</span></span>

<span data-ttu-id="8d5c3-150">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="8d5c3-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="8d5c3-151">Диагностик</span><span class="sxs-lookup"><span data-stu-id="8d5c3-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8d5c3-152">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="8d5c3-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="8d5c3-153">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксперсистентчатмессаже** :</span><span class="sxs-lookup"><span data-stu-id="8d5c3-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="8d5c3-154">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="8d5c3-155">Возможно, необходимые проверочные учетные записи не существуют или созданы неправильно.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="8d5c3-156">Возможно, возникла проблема с сетью, вызывающая непредвиденную задержку, из-за которой истекло время выполнения теста.</span><span class="sxs-lookup"><span data-stu-id="8d5c3-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d5c3-157">См. также</span><span class="sxs-lookup"><span data-stu-id="8d5c3-157">See Also</span></span>


[<span data-ttu-id="8d5c3-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="8d5c3-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="8d5c3-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="8d5c3-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="8d5c3-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="8d5c3-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


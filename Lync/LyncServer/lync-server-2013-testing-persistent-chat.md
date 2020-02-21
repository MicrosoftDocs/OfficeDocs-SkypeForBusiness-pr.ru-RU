---
title: 'Lync Server 2013: тестирование сохраняемого чата'
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
ms.openlocfilehash: 2177e4fce4d32bb2dc6c82e1f3fecae367eb2543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="4d752-102">Тестирование сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d752-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d752-103">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="4d752-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d752-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="4d752-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4d752-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="4d752-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d752-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="4d752-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4d752-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d752-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d752-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="4d752-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4d752-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4d752-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4d752-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsPersistentChatMessage</strong> .</span><span class="sxs-lookup"><span data-stu-id="4d752-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="4d752-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4d752-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4d752-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4d752-112">Description</span></span>

<span data-ttu-id="4d752-113">Командлет **Test-CsPersistentChatMessage** проверяет, может ли пользователь, выполняющий проверку, обмениваться сообщениями с помощью службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d752-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="4d752-114">Для этого командлет записывает два пользователя в Lync Server 2013, подключает пользователей к комнате сохраняемого чата, обменивается с другими сообщениями, а затем выходит из комнаты чата и выходит из системы двух пользователей.</span><span class="sxs-lookup"><span data-stu-id="4d752-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="4d752-115">Обратите внимание на то, что вызовы этого командлета завершатся неуспешно, если вы не создали комнаты чата или две тестовых учетных записей пользователей не назначены политике сохраняемого чата, которая предоставляет им доступ к службе сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d752-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4d752-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="4d752-116">Running the test</span></span>

<span data-ttu-id="4d752-117">Команды, показанные в следующем примере, проверяют способность пользователей (litwareinc\\Pilar и litwareinc\\kenmyer) войти в Lync Server 2013, а затем обмениваться сообщениями с помощью службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d752-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="4d752-118">Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="4d752-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="4d752-119">(Так как имя для входа,\\litwareinc Pilar, было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Pilar Ackerman.) Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="4d752-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="4d752-120">Вторая команда производит аналогичную операцию, возвращая объект учетных данных для учетной записи Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4d752-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="4d752-121">Если у вас есть объекты учетных данных в наличии, третья команда определяет, могут ли эти два пользователя входить в Lync Server 2013 и обмениваться сообщениями с помощью сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="4d752-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="4d752-122">Для выполнения этой задачи командлет **Test-CsPersistentChatMessage** вызывается с использованием следующих параметров: TargetFqdn (полное доменное имя пула регистратора); SenderSipAddress (SIP-адрес для первого тестового пользователя); SenderCredential (объект Windows PowerShell, содержащий учетные данные для этого пользователя); ReceiverSipAddress (SIP-адрес для другого тестового пользователя); и ReceiverCredential (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).</span><span class="sxs-lookup"><span data-stu-id="4d752-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4d752-123">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="4d752-123">Determining success or failure</span></span>

<span data-ttu-id="4d752-124">Если указанный пользователь имеет действительную политику расположения, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.</span><span class="sxs-lookup"><span data-stu-id="4d752-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="4d752-125">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d752-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4d752-126">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="4d752-126">Result : Success</span></span>

<span data-ttu-id="4d752-127">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4d752-127">Latency : 00:00:00</span></span>

<span data-ttu-id="4d752-128">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="4d752-128">Error Message :</span></span>

<span data-ttu-id="4d752-129">Диагност</span><span class="sxs-lookup"><span data-stu-id="4d752-129">Diagnosis :</span></span>

<span data-ttu-id="4d752-130">Если указанные пользователи не могут обмениваться сообщениями с помощью службы сохраняемого чата, результат будет отображаться как **сбой**, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="4d752-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4d752-131">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="4d752-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="4d752-132">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="4d752-132">domain name (FQDN).</span></span> <span data-ttu-id="4d752-133">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d752-133">Using default Registrar port number.</span></span> <span data-ttu-id="4d752-134">Возникновения</span><span class="sxs-lookup"><span data-stu-id="4d752-134">Exception:</span></span>

<span data-ttu-id="4d752-135">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="4d752-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="4d752-136">в</span><span class="sxs-lookup"><span data-stu-id="4d752-136">at</span></span>

<span data-ttu-id="4d752-137">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="4d752-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="4d752-138">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="4d752-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="4d752-139">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d752-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4d752-140">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="4d752-140">Result : Failure</span></span>

<span data-ttu-id="4d752-141">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4d752-141">Latency : 00:00:00</span></span>

<span data-ttu-id="4d752-142">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="4d752-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="4d752-143">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="4d752-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="4d752-144">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="4d752-144">established connection failed because connected host has</span></span>

<span data-ttu-id="4d752-145">не удалось ответить \[на 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="4d752-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="4d752-146">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="4d752-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="4d752-147">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="4d752-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="4d752-148">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="4d752-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="4d752-149">не отвечает</span><span class="sxs-lookup"><span data-stu-id="4d752-149">has failed to respond</span></span>

<span data-ttu-id="4d752-150">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="4d752-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="4d752-151">Диагност</span><span class="sxs-lookup"><span data-stu-id="4d752-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4d752-152">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="4d752-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="4d752-153">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsPersistentChatMessage** :</span><span class="sxs-lookup"><span data-stu-id="4d752-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="4d752-154">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="4d752-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="4d752-155">Возможно, необходимые тестовые учетные записи не существуют или созданы неправильно.</span><span class="sxs-lookup"><span data-stu-id="4d752-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="4d752-156">Возможно, возникла проблема с сетью, которая привела к непредвиденной задержке, при которой истекло время ожидания проверки.</span><span class="sxs-lookup"><span data-stu-id="4d752-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d752-157">См. также</span><span class="sxs-lookup"><span data-stu-id="4d752-157">See Also</span></span>


[<span data-ttu-id="4d752-158">Granting — CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="4d752-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="4d752-159">New — CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="4d752-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="4d752-160">Set — CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="4d752-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


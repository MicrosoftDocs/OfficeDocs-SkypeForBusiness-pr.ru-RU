---
title: 'Lync Server 2013: Проверка сеанса конференц-связи с телефонным подключением'
description: 'Lync Server 2013: Проверка сеанса конференц-связи с телефонным подключением.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d0c51b16df674dbf8bf7f0a2c6c4c93c2606d95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560635"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="be800-103">Проверка сеанса конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be800-103">Testing dial-in conferencing session in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be800-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="be800-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be800-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="be800-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="be800-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="be800-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be800-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="be800-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="be800-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be800-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be800-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="be800-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="be800-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="be800-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="be800-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsDialInConferencing.</span><span class="sxs-lookup"><span data-stu-id="be800-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="be800-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be800-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="be800-113">Описание</span><span class="sxs-lookup"><span data-stu-id="be800-113">Description</span></span>

<span data-ttu-id="be800-114">Командлет Test-CsDialInConferencing проверяет, может ли пользователь участвовать в конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="be800-114">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="be800-115">Test-CsDialInConferencing работает, пытаясь записать тестового пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="be800-115">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="be800-116">Если вход выполнен успешно, командлет затем использует учетные данные пользователя и разрешения, чтобы попробовать все доступные номера доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="be800-116">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="be800-117">Успешное или неудачное завершение каждой попытки проверки подлинности. После этого тестовый пользователь будет выполнен выход из Lync Server. Test-CsDialInConferencing только проверяет, могут ли быть выполнены соответствующие подключения.</span><span class="sxs-lookup"><span data-stu-id="be800-117">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="be800-118">В действительности он не выполняет никакие телефонные звонки и не создает никаких конференций с телефонным подключением, к которым могли бы присоединиться другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="be800-118">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="be800-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="be800-119">Running the test</span></span>

<span data-ttu-id="be800-120">Командлет Test-CsDialInConferencing можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be800-120">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="be800-121">Чтобы выполнить эту проверку с помощью тестовой учетной записи, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be800-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="be800-122">Например:</span><span class="sxs-lookup"><span data-stu-id="be800-122">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="be800-123">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="be800-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="be800-124">Затем необходимо добавить этот объект учетных данных и SIP-адрес учетной записи, вызывающей Test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="be800-124">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="be800-125">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="be800-125">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="be800-126">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="be800-126">Determining success or failure</span></span>

<span data-ttu-id="be800-127">Если указанный пользователь может войти в систему Lync Server и установить подключение, используя один из доступных номеров доступа к конференц-связи с телефонным подключением, будет получен результат, подобный следующему, при этом свойство Result помечается как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="be800-127">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="be800-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be800-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="be800-129">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="be800-129">Result : Success</span></span>

<span data-ttu-id="be800-130">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="be800-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="be800-131">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="be800-131">Error :</span></span>

<span data-ttu-id="be800-132">Диагност</span><span class="sxs-lookup"><span data-stu-id="be800-132">Diagnosis :</span></span>

<span data-ttu-id="be800-133">Если указанный пользователь не может сделать это подключение, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="be800-133">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="be800-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be800-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="be800-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="be800-135">Result : Failure</span></span>

<span data-ttu-id="be800-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="be800-136">Latency : 00:00:00</span></span>

<span data-ttu-id="be800-137">Ошибка: при входе в систему было отказано.</span><span class="sxs-lookup"><span data-stu-id="be800-137">Error : The log on was denied.</span></span> <span data-ttu-id="be800-138">Убедитесь, что правильные учетные данные</span><span class="sxs-lookup"><span data-stu-id="be800-138">Check that the proper credentials are</span></span>

<span data-ttu-id="be800-139">используется, и учетная запись активна.</span><span class="sxs-lookup"><span data-stu-id="be800-139">being used and the account is active.</span></span>

<span data-ttu-id="be800-140">Внутреннее исключение: сбой НеготиатесекуритяссоЦиатион, ошибка: —</span><span class="sxs-lookup"><span data-stu-id="be800-140">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="be800-141">2146893044</span><span class="sxs-lookup"><span data-stu-id="be800-141">2146893044</span></span>

<span data-ttu-id="be800-142">Диагност</span><span class="sxs-lookup"><span data-stu-id="be800-142">Diagnosis :</span></span>

<span data-ttu-id="be800-143">Приведенные выше выходные данные показывают, что тестовый пользователь отклонил доступ к серверу Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be800-143">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="be800-144">Обычно это означает, что учетные данные пользователя, переданные Test-CsDialInConferencing, являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="be800-144">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="be800-145">В свою очередь, необходимо повторно создать объект учетных данных Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be800-145">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="be800-146">Несмотря на то, что вы можете получить пароль для учетной записи пользователя, вы можете проверить SIP адрес, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be800-146">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="be800-147">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="be800-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="be800-148">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsDialInConferencing:</span><span class="sxs-lookup"><span data-stu-id="be800-148">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="be800-149">Указана недопустимая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="be800-149">You specified a user account that is not valid.</span></span> <span data-ttu-id="be800-150">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="be800-150">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="be800-151">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be800-151">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="be800-152">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="be800-152">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="be800-153">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be800-153">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="be800-154">Возможно, у вас неверный номер доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="be800-154">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="be800-155">С помощью этой команды можно возвратить список номеров доступа для конференц-связи с телефонным подключением, настроенный в текущий момент:</span><span class="sxs-lookup"><span data-stu-id="be800-155">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>


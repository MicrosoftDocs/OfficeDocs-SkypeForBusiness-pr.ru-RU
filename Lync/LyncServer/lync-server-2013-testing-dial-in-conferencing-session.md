---
title: 'Lync Server 2013: Проверка сеанса конференц-связи с телефонным подключением'
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
ms.openlocfilehash: 1afb4ee2e1a500b08c3481f71994f585298bc8c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="99b35-102">Проверка сеанса конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b35-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b35-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="99b35-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99b35-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="99b35-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="99b35-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="99b35-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99b35-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="99b35-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="99b35-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99b35-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99b35-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="99b35-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="99b35-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="99b35-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="99b35-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-КсдиалинконференЦинг.</span><span class="sxs-lookup"><span data-stu-id="99b35-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="99b35-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="99b35-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="99b35-112">Описание</span><span class="sxs-lookup"><span data-stu-id="99b35-112">Description</span></span>

<span data-ttu-id="99b35-113">Командлет Test-КсдиалинконференЦинг проверяет, может ли пользователь принимать участие в конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="99b35-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="99b35-114">Тест-КсдиалинконференЦинг работает, пытаясь записать тестового пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="99b35-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="99b35-115">Если вход завершается успешно, командлет будет использовать учетные данные пользователя и разрешения, чтобы попробовать все доступные номера доступа для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="99b35-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="99b35-116">При попытке входа в систему с помощью функции "Пошаговое подключение" может быть выдано сообщение об успешном завершении работы, а также о том, что тестовый пользователь будет выполнен из Lync Server. Test-КсдиалинконференЦинг только проверяет, правильно ли выполняются соответствующие подключения.</span><span class="sxs-lookup"><span data-stu-id="99b35-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="99b35-117">Этот командлет на самом деле не позволяет звонить или создавать конференции с телефонным подключением, которые могут присоединить другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="99b35-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="99b35-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="99b35-118">Running the test</span></span>

<span data-ttu-id="99b35-119">Командлет Test-КсдиалинконференЦинг можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. раздел Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи пользователя, который включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99b35-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="99b35-120">Для выполнения этой проверки с помощью тестовой учетной записи нужно просто указать полное доменное имя для тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99b35-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="99b35-121">Например:</span><span class="sxs-lookup"><span data-stu-id="99b35-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="99b35-122">Для выполнения этой проверки с использованием реальной учетной записи пользователя необходимо создать объект учетных данных Windows PowerShell, содержащий имя учетной записи и пароль.</span><span class="sxs-lookup"><span data-stu-id="99b35-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="99b35-123">Затем необходимо добавить этот объект учетных данных и адрес SIP учетной записи, чтобы позвонить тесту-КсдиалинконференЦинг:</span><span class="sxs-lookup"><span data-stu-id="99b35-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="99b35-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксдиалинконференЦинг](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .</span><span class="sxs-lookup"><span data-stu-id="99b35-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="99b35-125">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="99b35-125">Determining success or failure</span></span>

<span data-ttu-id="99b35-126">Если указанный пользователь может войти на сервер Lync Server, а затем установить соединение с помощью одного из доступных номеров доступа для конференц-связи с телефонным подключением, то вы получите вывод примерно так, чтобы свойство Result помечаed " **успешно".**</span><span class="sxs-lookup"><span data-stu-id="99b35-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="99b35-127">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="99b35-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="99b35-128">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="99b35-128">Result : Success</span></span>

<span data-ttu-id="99b35-129">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="99b35-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="99b35-130">Ошибки</span><span class="sxs-lookup"><span data-stu-id="99b35-130">Error :</span></span>

<span data-ttu-id="99b35-131">Диагностик</span><span class="sxs-lookup"><span data-stu-id="99b35-131">Diagnosis :</span></span>

<span data-ttu-id="99b35-132">Если указанный пользователь не может сделать это подключение, результат будет показан как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="99b35-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="99b35-133">Таржетфкдн: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="99b35-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="99b35-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="99b35-134">Result : Failure</span></span>

<span data-ttu-id="99b35-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="99b35-135">Latency : 00:00:00</span></span>

<span data-ttu-id="99b35-136">Ошибка: отказано в входе.</span><span class="sxs-lookup"><span data-stu-id="99b35-136">Error : The log on was denied.</span></span> <span data-ttu-id="99b35-137">Убедитесь, что указаны правильные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="99b35-137">Check that the proper credentials are</span></span>

<span data-ttu-id="99b35-138">используется, и учетная запись активна.</span><span class="sxs-lookup"><span data-stu-id="99b35-138">being used and the account is active.</span></span>

<span data-ttu-id="99b35-139">Внутреннее исключение: НеготиатесекуритяссоЦиатион не удалось, ошибка:-</span><span class="sxs-lookup"><span data-stu-id="99b35-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="99b35-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="99b35-140">2146893044</span></span>

<span data-ttu-id="99b35-141">Диагностик</span><span class="sxs-lookup"><span data-stu-id="99b35-141">Diagnosis :</span></span>

<span data-ttu-id="99b35-142">Предыдущий вывод указывает на то, что пользователю в тесте отказано в доступе к серверу Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99b35-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="99b35-143">Обычно это означает, что учетные данные пользователя, переданные в Test-КсдиалинконференЦинг, недопустимы.</span><span class="sxs-lookup"><span data-stu-id="99b35-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="99b35-144">В свою очередь, необходимо повторно создать объект учетных данных Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99b35-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="99b35-145">Несмотря на то, что вы можете получить пароль для учетной записи пользователя, вы можете проверить адрес SIP с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="99b35-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="99b35-146">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="99b35-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="99b35-147">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-КсдиалинконференЦинг:</span><span class="sxs-lookup"><span data-stu-id="99b35-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="99b35-148">Указана недействительная учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="99b35-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="99b35-149">Для проверки существования учетной записи пользователя можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="99b35-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="99b35-150">Учетная запись пользователя верна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99b35-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="99b35-151">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="99b35-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="99b35-152">Если для свойства Enabled задано значение false, это означает, что пользователь в настоящее время не поддерживает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99b35-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="99b35-153">Возможно, у вас неправильный номер доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="99b35-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="99b35-154">Вы можете вернуться к текущему списку номеров доступа конференц-связи с телефонным подключением с помощью этой команды:</span><span class="sxs-lookup"><span data-stu-id="99b35-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>


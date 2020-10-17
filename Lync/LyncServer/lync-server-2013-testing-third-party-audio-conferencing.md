---
title: 'Lync Server 2013: тестирование сторонней голосовой конференции'
description: 'Lync Server 2013: тестирование сторонних конференций с аудио-и видеоконференциями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f009d95834768d8a4e6619a79ff1f3be0a2b92bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556105"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="b2587-103">Тестирование аудио конференц-связи сторонних производителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2587-103">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2587-104">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b2587-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2587-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b2587-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b2587-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="b2587-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2587-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="b2587-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b2587-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2587-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2587-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="b2587-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b2587-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b2587-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b2587-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAudioConferencingProvider.</span><span class="sxs-lookup"><span data-stu-id="b2587-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="b2587-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b2587-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b2587-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b2587-113">Description</span></span>

<span data-ttu-id="b2587-p102">Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций. Помимо прочего подобный поставщик позволяет пользователям, находящимся вне пределов сайта или не подключенным к сети предприятия или Интернету, принимать участие в конференции или собрании с помощью аудиосвязи. Подобные поставщики часто предоставляют и высококачественные услуги, например, синхронный перевод, запись и обслуживание оговоренных конференций оператором.</span><span class="sxs-lookup"><span data-stu-id="b2587-p102">An audio conferencing provider is a third-party company that provides organizations with conferencing services. Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting. Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="b2587-117">Командлет **Test-CsAudioConferencingProvider** используется для проверки того, что пользователь может подключиться к своему поставщику конференц-связи с аудио-и видеоконференциями.</span><span class="sxs-lookup"><span data-stu-id="b2587-117">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="b2587-118">Этот командлет может выполняться одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="b2587-118">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="b2587-119">Многие администраторы используют командлеты CsHealthMonitoringConfiguration, чтобы настроить тестовых пользователей для каждого из своих пулов регистратора.</span><span class="sxs-lookup"><span data-stu-id="b2587-119">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="b2587-120">Тестовые пользователи представляют собой пару учетных записей пользователей, предварительно настроенных для применения с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="b2587-120">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="b2587-121">(Как правило, это тестовые учетные записи, а не учетные записи, принадлежащие реальным пользователям.) Если тестовые пользователи настроены для пула, администраторы могут запустить командлет **Test-CsAudioConferencingProvider** для этого пула без необходимости указания удостоверения (и предоставления учетных данных) учетной записи пользователя, используемой в тесте.</span><span class="sxs-lookup"><span data-stu-id="b2587-121">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="b2587-122">Кроме того, администраторы могут выполнять командлет **Test-CsAudioConferencingProvider** с использованием реальной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b2587-122">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="b2587-123">Если вы решили проверить реальную учетную запись пользователя, необходимо указать имя пользователя и пароль для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b2587-123">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b2587-124">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="b2587-124">Running the test</span></span>

<span data-ttu-id="b2587-125">В примере 1 проверяется, может ли тестовый пользователь, определенный для пула atl-cs-001.litwareinc.com, подключиться к своему поставщику услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b2587-125">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="b2587-126">Для этой команды необходимо, чтобы для пула был определен хотя бы один тестовый пользователь.</span><span class="sxs-lookup"><span data-stu-id="b2587-126">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="b2587-127">Если тестовых пользователей не было определено для atl-cs-001.litwareinc.com, команда завершится с ошибками; Это вызвано тем, что командлет **Test-CsAudioConferencingProvider** не будет знать, какой пользователь должен использовать в тесте.</span><span class="sxs-lookup"><span data-stu-id="b2587-127">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="b2587-128">Если вы не определили тестовых пользователей для пула, необходимо включить в команду параметр UserSipAddress и учетные данные учетной записи пользователя, которые команда будет использовать при проверке подключения к поставщику услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b2587-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="b2587-129">Команды, показанные в примере 2, проверяют возможность определенного пользователя (litwareinc \\ kenmyer) для подключения к своему поставщику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b2587-129">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="b2587-130">Для этого первая команда в примере использует командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b2587-130">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="b2587-131">(Так как имя для входа litwareinc \\ kenmyer было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо, чтобы администратор вводил пароль для учетной записи Ken Myer.) Полученный объект учетных данных хранится в переменной с именем $credential.</span><span class="sxs-lookup"><span data-stu-id="b2587-131">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="b2587-132">Вторая команда проверяет, может ли пользователь подключиться к своему поставщику услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b2587-132">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="b2587-133">Для выполнения этой задачи вызывается командлет Test-CsAudioConferencingProvider, а также три параметра: TargetFqdn (полное доменное имя пула регистратора); UserCredential (объект Windows PowerShell, содержащий учетные данные пользователя Ken Myer); и UserSipAddress (SIP-адрес, соответствующий предоставленным учетным данным пользователя).</span><span class="sxs-lookup"><span data-stu-id="b2587-133">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b2587-134">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="b2587-134">Determining success or failure</span></span>

<span data-ttu-id="b2587-135">Если поставщик службы аудио-и видеоконференций настроен правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="b2587-135">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b2587-136">Целевое полное доменное имя: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b2587-136">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b2587-137">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="b2587-137">Result : Success</span></span>

<span data-ttu-id="b2587-138">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b2587-138">Latency : 00:00:00</span></span>

<span data-ttu-id="b2587-139">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="b2587-139">Error Message :</span></span>

<span data-ttu-id="b2587-140">Диагност</span><span class="sxs-lookup"><span data-stu-id="b2587-140">Diagnosis :</span></span>

<span data-ttu-id="b2587-141">Если указанный пользователь не может войти в систему или выйти из нее, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="b2587-141">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b2587-142">Целевое полное доменное имя: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b2587-142">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="b2587-143">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="b2587-143">Result : Failure</span></span>

<span data-ttu-id="b2587-144">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b2587-144">Latency : 00:00:00</span></span>

<span data-ttu-id="b2587-145">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="b2587-145">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b2587-146">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="b2587-146">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b2587-147">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="b2587-147">established connection failed because connected host has</span></span>

<span data-ttu-id="b2587-148">не удалось ответить на \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944: \] 5061</span><span class="sxs-lookup"><span data-stu-id="b2587-148">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="b2587-149">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="b2587-149">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b2587-150">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="b2587-150">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b2587-151">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="b2587-151">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b2587-152">не отвечает</span><span class="sxs-lookup"><span data-stu-id="b2587-152">has failed to respond</span></span>

<span data-ttu-id="b2587-153">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="b2587-153">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="b2587-154">Диагност</span><span class="sxs-lookup"><span data-stu-id="b2587-154">Diagnosis :</span></span>

<span data-ttu-id="b2587-155">Например, в примере выше приведена заметка "подключенная сторона не ответила", которая обычно указывает на проблему с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="b2587-155">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b2587-156">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="b2587-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="b2587-157">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsAudioConferencingProvider** :</span><span class="sxs-lookup"><span data-stu-id="b2587-157">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="b2587-158">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="b2587-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b2587-159">Как показано в предыдущем примере, необязательные параметры должны быть настроены правильно, иначе тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="b2587-159">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b2587-160">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="b2587-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b2587-161">Обратите внимание, что тест завершится ошибкой, если пользователю, используемому командлетом **Test-CsAudioConferencingProvider** , не назначен поставщик конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b2587-161">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="b2587-162">Эта команда завершится с ошибками, если пограничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="b2587-162">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


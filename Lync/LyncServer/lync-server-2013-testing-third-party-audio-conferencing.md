---
title: 'Lync Server 2013: Проверка голосовой конференции третьих лиц'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="f281e-102">Тестирование голосовой конференции третьих лиц в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f281e-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f281e-103">_**Тема последнего изменения:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="f281e-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f281e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f281e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f281e-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="f281e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f281e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f281e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f281e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f281e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f281e-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="f281e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f281e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="f281e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f281e-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-КсаудиоконференЦингпровидер.</span><span class="sxs-lookup"><span data-stu-id="f281e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="f281e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f281e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f281e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f281e-112">Description</span></span>

<span data-ttu-id="f281e-113">Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="f281e-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="f281e-114">Помимо всего прочего поставщики услуг аудиоконференций позволяют пользователям, расположенным за пределами организации и не подключенным к корпоративной сети или Интернету, участвовать в конференции или собрании с помощью аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="f281e-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="f281e-115">Поставщики видеоконференций часто предоставляют высококачественные службы, такие как трансляция, транскрипция и Динамическая поддержка операторов на Конференции.</span><span class="sxs-lookup"><span data-stu-id="f281e-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="f281e-116">Командлет **Test-ксаудиоконференЦингпровидер** используется для подтверждения того, что пользователь может подключиться к своему поставщику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f281e-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="f281e-117">Обратите внимание, что этот командлет можно выполнить одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="f281e-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="f281e-118">Многие администраторы будут использовать командлеты Кшеалсмониторингконфигуратион для настройки тестовых пользователей для каждого из своих пулов регистраторов.</span><span class="sxs-lookup"><span data-stu-id="f281e-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="f281e-119">Эти тестовые пользователи представляют собой пару учетных записей пользователей, которые были предварительно настроены для использования с искусственными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="f281e-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="f281e-120">(Как правило, они являются тестовыми учетными записями, а не учетными записями, принадлежащими реальным пользователям.) Если тестовые пользователи настроены для пула, администраторы могут выполнять командлет **Test-ксаудиоконференЦингпровидер** для этого пула без необходимости указывать учетные данные для учетной записи пользователя, участвующей в тесте.</span><span class="sxs-lookup"><span data-stu-id="f281e-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="f281e-121">Кроме того, администраторы могут выполнять командлет **Test-ксаудиоконференЦингпровидер** с использованием реальной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f281e-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="f281e-122">Если вы решите провести тестирование с использованием реальной учетной записи пользователя, вам потребуется указать имя для входа и пароль для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f281e-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f281e-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f281e-123">Running the test</span></span>

<span data-ttu-id="f281e-124">В примере 1 Проверка того, определен ли тестовый пользователь для пула atl-cs-001.litwareinc.com, может подключаться к своему поставщику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="f281e-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="f281e-125">Для этой команды требуется, чтобы для пула было определено по крайней мере один тестовый пользователь.</span><span class="sxs-lookup"><span data-stu-id="f281e-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="f281e-126">Если тестовых пользователей для atl-cs-001.litwareinc.com не заданы, команда завершится сбоем. Это обусловлено тем, что командлет **Test-ксаудиоконференЦингпровидер** не будет знать, какой пользователь должен использовать в тесте.</span><span class="sxs-lookup"><span data-stu-id="f281e-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="f281e-127">Если вы не определили тестовых пользователей для пула, необходимо включить параметр Усерсипаддресс и учетные данные учетной записи пользователя, которую должна использовать команда, при проверке подключения с помощью поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="f281e-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="f281e-128">Команды, показанные в примере 2, проверяют возможность определенного пользователя (плана litwareinc\\кенмер) для подключения к своему поставщику видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="f281e-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="f281e-129">Для этого в первой команде примера используется командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Кен мер.</span><span class="sxs-lookup"><span data-stu-id="f281e-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="f281e-130">(Поскольку имя для входа плана litwareinc\\кенмер в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи Кен мер.) Результирующий объект учетных данных хранится в переменной с именем $credential.</span><span class="sxs-lookup"><span data-stu-id="f281e-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="f281e-131">Вторая команда проверяет, может ли пользователь подключиться к своему поставщику видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="f281e-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="f281e-132">Для выполнения этой задачи вызывается командлет Test-КсаудиоконференЦингпровидер, а также три параметра: Таржетфкдн (полное доменное имя пула регистраторов). Усеркредентиал (объект Windows PowerShell, содержащий учетные данные пользователя Кен мер); и Усерсипаддресс (адрес SIP, соответствующий предоставленным учетным данным пользователя).</span><span class="sxs-lookup"><span data-stu-id="f281e-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f281e-133">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="f281e-133">Determining success or failure</span></span>

<span data-ttu-id="f281e-134">Если вы правильно настроили поставщик видеоконференций, вы получите вывод примерно так, чтобы свойство Result пометило **"успешно".**</span><span class="sxs-lookup"><span data-stu-id="f281e-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f281e-135">Целевое полное доменное имя: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f281e-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="f281e-136">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="f281e-136">Result : Success</span></span>

<span data-ttu-id="f281e-137">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f281e-137">Latency : 00:00:00</span></span>

<span data-ttu-id="f281e-138">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="f281e-138">Error Message :</span></span>

<span data-ttu-id="f281e-139">Диагностик</span><span class="sxs-lookup"><span data-stu-id="f281e-139">Diagnosis :</span></span>

<span data-ttu-id="f281e-140">Если указанному пользователю не удается войти в систему или выйти из нее, результат будет показан в виде **ошибки**, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="f281e-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f281e-141">Целевое полное доменное имя: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f281e-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="f281e-142">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f281e-142">Result : Failure</span></span>

<span data-ttu-id="f281e-143">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f281e-143">Latency : 00:00:00</span></span>

<span data-ttu-id="f281e-144">Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="f281e-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="f281e-145">не отвечает на запросы в течение определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="f281e-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="f281e-146">не удалось установить соединение, так как подключенный узел имеет</span><span class="sxs-lookup"><span data-stu-id="f281e-146">established connection failed because connected host has</span></span>

<span data-ttu-id="f281e-147">не удалось ответить \[на 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="f281e-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="f281e-148">Внутреннее исключение: сбой при попытке подключения из-за того, что</span><span class="sxs-lookup"><span data-stu-id="f281e-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="f281e-149">связь с абонентом завершилась неправильно после определенного периода</span><span class="sxs-lookup"><span data-stu-id="f281e-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="f281e-150">время или соединение не удалось установить, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="f281e-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="f281e-151">не отвечает</span><span class="sxs-lookup"><span data-stu-id="f281e-151">has failed to respond</span></span>

<span data-ttu-id="f281e-152">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="f281e-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="f281e-153">Диагностик</span><span class="sxs-lookup"><span data-stu-id="f281e-153">Diagnosis :</span></span>

<span data-ttu-id="f281e-154">Например, в предыдущем выводе есть Примечание "подключенная сторона не ответила должным образом", которая обычно указывает на проблему с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="f281e-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f281e-155">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f281e-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="f281e-156">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксаудиоконференЦингпровидер** :</span><span class="sxs-lookup"><span data-stu-id="f281e-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="f281e-157">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="f281e-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="f281e-158">Как показано в предыдущем примере, необязательные параметры должны быть настроены правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="f281e-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="f281e-159">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="f281e-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="f281e-160">Обратите внимание, что тест завершается сбоем, если пользователь, который использует командлет **Test-ксаудиоконференЦингпровидер** , не назначил поставщика видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="f281e-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="f281e-161">Эта команда завершается сбоем, если граничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="f281e-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


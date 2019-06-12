---
title: 'Lync Server 2013: Проверка общего доступа в конференциях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="83d8e-102">Проверка общего использования в конференциях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83d8e-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83d8e-103">_**Тема последнего изменения:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="83d8e-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83d8e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="83d8e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="83d8e-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="83d8e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83d8e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="83d8e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="83d8e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83d8e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83d8e-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="83d8e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="83d8e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="83d8e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="83d8e-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксдатаконференце</strong> .</span><span class="sxs-lookup"><span data-stu-id="83d8e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="83d8e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="83d8e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="83d8e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="83d8e-112">Description</span></span>

<span data-ttu-id="83d8e-113">В Lync Server 2013 конференция данных — это любая конференция, в которой используются операции совместной работы, такие как доска или заметки.</span><span class="sxs-lookup"><span data-stu-id="83d8e-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="83d8e-114">Командлет **Test-ксдатаконференце** позволяет удостовериться, что пара пользователей сможет принимать участие в конференц-связи с данными.</span><span class="sxs-lookup"><span data-stu-id="83d8e-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="83d8e-115">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="83d8e-115">Running the test</span></span>

<span data-ttu-id="83d8e-116">Команда, показанная в примере 1, проверяет, можно ли проводить Конференц-связь с данными в atl-cs-001.litwareinc.com пула.</span><span class="sxs-lookup"><span data-stu-id="83d8e-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="83d8e-117">В этой команде предполагается, что вы настроили пару тестовых пользователей для указанного пула.</span><span class="sxs-lookup"><span data-stu-id="83d8e-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="83d8e-118">Если таких тестовых пользователей не существует, команда завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="83d8e-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="83d8e-119">Команды, показанные в примере 2, проверяют возможности пары пользователей (плана litwareinc\\почтового и плана litwareinc\\кенмер) для входа на сервер Lync Server 2013 и проведения Конференции с данными.</span><span class="sxs-lookup"><span data-stu-id="83d8e-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="83d8e-120">Для этого в первой команде примера используется командлет **Get-Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя почтового Вронский.</span><span class="sxs-lookup"><span data-stu-id="83d8e-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="83d8e-121">(Так как имя для входа,\\плана litwareinc почтового, включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи почтового Вронский.) Полученный объект учетных данных затем сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="83d8e-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="83d8e-122">Вторая команда — это то же самое, что возвращает объект учетной записи Кен мер.</span><span class="sxs-lookup"><span data-stu-id="83d8e-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="83d8e-123">Если у вас есть объекты учетных данных в ладони, третья команда определяет, могут ли эти пользователи войти в Lync Server 2013 и провести Конференц-связь с данными.</span><span class="sxs-lookup"><span data-stu-id="83d8e-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="83d8e-124">Для выполнения этой задачи вызывается командлет **Test-ксдатаконференце** , а также следующие параметры: таржетфкдн (полное доменное имя пула регистраторов). Сендерсипаддресс (адрес SIP для первого тестового пользователя); Сендеркредентиал (объект Windows PowerShell с учетными данными для этого пользователя); Рецеиверсипаддресс (SIP-адрес для другого тестового пользователя); и Рецеиверкредентиал (объект Windows PowerShell, содержащий учетные данные для другого тестового пользователя).</span><span class="sxs-lookup"><span data-stu-id="83d8e-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="83d8e-125">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="83d8e-125">Determining success or failure</span></span>

<span data-ttu-id="83d8e-126">Если вы правильно настраиваете Конференц-связь с данными, вы получаете такие данные, как и свойство Result, помеченное как **успешно.**</span><span class="sxs-lookup"><span data-stu-id="83d8e-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="83d8e-127">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="83d8e-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="83d8e-128">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="83d8e-128">Result : Success</span></span>

<span data-ttu-id="83d8e-129">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="83d8e-129">Latency : 00:00:00</span></span>

<span data-ttu-id="83d8e-130">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="83d8e-130">Error Message :</span></span>

<span data-ttu-id="83d8e-131">Диагностик</span><span class="sxs-lookup"><span data-stu-id="83d8e-131">Diagnosis :</span></span>

<span data-ttu-id="83d8e-132">Если указанные пользователи не могут использовать общий доступ к данным, результат будет показан как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="83d8e-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="83d8e-133">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="83d8e-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="83d8e-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="83d8e-134">Result : Failure</span></span>

<span data-ttu-id="83d8e-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="83d8e-135">Latency : 00:00:00</span></span>

<span data-ttu-id="83d8e-136">Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="83d8e-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="83d8e-137">не отвечает на запросы в течение определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="83d8e-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="83d8e-138">не удалось установить соединение, так как подключенный узел имеет</span><span class="sxs-lookup"><span data-stu-id="83d8e-138">established connection failed because connected host has</span></span>

<span data-ttu-id="83d8e-139">не удалось ответить \[на 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061</span><span class="sxs-lookup"><span data-stu-id="83d8e-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="83d8e-140">Внутреннее исключение: сбой при попытке подключения из-за того, что</span><span class="sxs-lookup"><span data-stu-id="83d8e-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="83d8e-141">связь с абонентом завершилась неправильно после определенного периода</span><span class="sxs-lookup"><span data-stu-id="83d8e-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="83d8e-142">время или соединение не удалось установить, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="83d8e-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="83d8e-143">не отвечает</span><span class="sxs-lookup"><span data-stu-id="83d8e-143">has failed to respond</span></span>

<span data-ttu-id="83d8e-144">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="83d8e-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="83d8e-145">Диагностик</span><span class="sxs-lookup"><span data-stu-id="83d8e-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="83d8e-146">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="83d8e-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="83d8e-147">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксдатаконференце** :</span><span class="sxs-lookup"><span data-stu-id="83d8e-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="83d8e-148">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="83d8e-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="83d8e-149">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="83d8e-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="83d8e-150">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="83d8e-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="83d8e-151">Возможность проведения конференции для данных зависит от политики конференц-связи, назначенной пользователю, который организовал конференцию (в случае командлета **Test — ксдатаконференце** , который является отправителем).</span><span class="sxs-lookup"><span data-stu-id="83d8e-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="83d8e-152">Если организатор не может включать мероприятия для совместной работы на своем собрании (например, если у его политики Конференции задано значение false), командлет **Test-ксдатаконференце** завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="83d8e-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="83d8e-153">Эта команда завершается сбоем, если граничный сервер неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="83d8e-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


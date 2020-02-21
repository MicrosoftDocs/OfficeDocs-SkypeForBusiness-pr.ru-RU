---
title: 'Lync Server 2013: тестирование доступа к единому хранилищу контактов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34dbf6ede9f58b39df1722e742511ee0844c41f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="909c4-102">Тестирование доступа к единому хранилищу контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="909c4-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="909c4-103">_**Последнее изменение темы:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="909c4-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="909c4-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="909c4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="909c4-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="909c4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="909c4-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="909c4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="909c4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="909c4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="909c4-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="909c4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="909c4-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="909c4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="909c4-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="909c4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="909c4-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="909c4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="909c4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="909c4-112">Description</span></span>

<span data-ttu-id="909c4-113">Единое хранилище контактов, представленное в Lync Server 2013, дает администраторам возможность хранить контакты пользователя в Microsoft Exchange Server 2013, а не в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="909c4-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="909c4-114">Это позволяет пользователю получить доступ к тому же набору контактов в Outlook Web Access в дополнение к Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="909c4-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="909c4-115">(Или вы можете продолжить хранение контактов в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="909c4-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="909c4-116">В этом случае пользователям потребуется поддерживать два отдельных набора контактов: один для использования с Outlook и Outlook Web Access и один для использования с Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="909c4-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="909c4-117">Чтобы определить, были ли контакты пользователя перемещены в единое хранилище контактов, запустите командлет **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="909c4-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="909c4-118">Командлет **Test-CsUnifiedContactStore** принимает указанную учетную запись пользователя, подключается к единому хранилищу контактов и пытается получить контакт для пользователя.</span><span class="sxs-lookup"><span data-stu-id="909c4-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="909c4-119">Если не удается получить контакты, команда завершится с сообщением "нет контактов, полученных для пользователя".</span><span class="sxs-lookup"><span data-stu-id="909c4-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="909c4-120">Убедитесь, что контакты существуют для пользователя. "</span><span class="sxs-lookup"><span data-stu-id="909c4-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="909c4-121">Обратите внимание на то, что командлет **Test-CsUnifiedContactStore** завершится с ошибками, если пользователь успешно выполнил миграцию в единое хранилище контактов, но не имеет контактов в своем списке контактов.</span><span class="sxs-lookup"><span data-stu-id="909c4-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="909c4-122">Указанный пользователь должен иметь по крайней мере один контакт для успешного выполнения командлета **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="909c4-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="909c4-123">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="909c4-123">Running the test</span></span>

<span data-ttu-id="909c4-124">Команды, показанные в следующем примере, определяют, можно ли найти контакты\\для пользователя litwareinc kenmyer в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="909c4-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="909c4-125">Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell для пользователя litwareinc\\kenmyer.</span><span class="sxs-lookup"><span data-stu-id="909c4-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="909c4-126">Обратите внимание, что для этой учетной записи необходимо указать пароль, чтобы создать допустимый объект учетных данных, а затем убедиться, что командлет **Test-CsUnifiedContactStore** может выполнить его проверку.</span><span class="sxs-lookup"><span data-stu-id="909c4-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="909c4-127">Вторая команда в примере использует предоставленный объект учетных данных ($x) и SIP-адрес пользователя litwareinc\\kenmyer, чтобы определить, можно ли найти его контакты в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="909c4-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="909c4-128">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="909c4-128">Determining success or failure</span></span>

<span data-ttu-id="909c4-129">Если доступ к хранилищу контактов настроен правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**</span><span class="sxs-lookup"><span data-stu-id="909c4-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="909c4-130">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="909c4-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="909c4-131">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="909c4-131">Result : Success</span></span>

<span data-ttu-id="909c4-132">Задержка: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="909c4-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="909c4-133">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="909c4-133">Error Message :</span></span>

<span data-ttu-id="909c4-134">Диагност</span><span class="sxs-lookup"><span data-stu-id="909c4-134">Diagnosis :</span></span>

<span data-ttu-id="909c4-135">Если доступ к хранилищу контактов настроен неправильно, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="909c4-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="909c4-136">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="909c4-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="909c4-137">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="909c4-137">domain name (FQDN).</span></span> <span data-ttu-id="909c4-138">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="909c4-138">Using default Registrar port number.</span></span> <span data-ttu-id="909c4-139">Возникновения</span><span class="sxs-lookup"><span data-stu-id="909c4-139">Exception:</span></span>

<span data-ttu-id="909c4-140">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="909c4-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="909c4-141">в</span><span class="sxs-lookup"><span data-stu-id="909c4-141">at</span></span>

<span data-ttu-id="909c4-142">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="909c4-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="909c4-143">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="909c4-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="909c4-144">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="909c4-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="909c4-145">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="909c4-145">Result : Failure</span></span>

<span data-ttu-id="909c4-146">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="909c4-146">Latency : 00:00:00</span></span>

<span data-ttu-id="909c4-147">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="909c4-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="909c4-148">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="909c4-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="909c4-149">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="909c4-149">established connection failed because connected host has</span></span>

<span data-ttu-id="909c4-150">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="909c4-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="909c4-151">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="909c4-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="909c4-152">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="909c4-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="909c4-153">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="909c4-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="909c4-154">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="909c4-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="909c4-155">Диагност</span><span class="sxs-lookup"><span data-stu-id="909c4-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="909c4-156">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="909c4-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="909c4-157">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsUnifiedContactStore** :</span><span class="sxs-lookup"><span data-stu-id="909c4-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="909c4-158">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="909c4-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="909c4-159">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="909c4-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="909c4-160">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="909c4-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="909c4-161">Не удалось подключиться к единому хранилищу контактов, и попытка получить контакт для пользователя была невозможна.</span><span class="sxs-lookup"><span data-stu-id="909c4-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="909c4-162">Возможны проблемы с сетевым подключением.</span><span class="sxs-lookup"><span data-stu-id="909c4-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="909c4-163">См. также</span><span class="sxs-lookup"><span data-stu-id="909c4-163">See Also</span></span>


[<span data-ttu-id="909c4-164">New — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="909c4-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="909c4-165">Set — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="909c4-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


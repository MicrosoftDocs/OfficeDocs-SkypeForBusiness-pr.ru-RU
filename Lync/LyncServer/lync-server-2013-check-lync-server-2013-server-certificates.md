---
title: 'Lync Server 2013: Проверка серверных сертификатов Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebdbfdc4ed0f88d78fc78037a3522c73bd220270
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="b1795-102">Проверка серверных сертификатов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1795-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1795-103">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="b1795-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1795-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b1795-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b1795-105">Monthly Channel</span><span class="sxs-lookup"><span data-stu-id="b1795-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1795-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="b1795-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b1795-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1795-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1795-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="b1795-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b1795-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b1795-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b1795-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Get – CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="b1795-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="b1795-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b1795-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b1795-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b1795-112">Description</span></span>

<span data-ttu-id="b1795-113">Командлет Get – CsCertificate позволяет получить сведения о каждом из сертификатов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1795-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="b1795-114">Это особенно важно, так как сертификаты имеют встроенную дату истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="b1795-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="b1795-115">Например, срок действия сертификатов, выданных частными, обычно истечет через 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="b1795-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="b1795-116">Если какой-либо из ваших сертификатов Lync Server истечет, все функции будут потеряны до тех пор, пока сертификат не будет обновлен или заменен.</span><span class="sxs-lookup"><span data-stu-id="b1795-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b1795-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="b1795-117">Running the test</span></span>

<span data-ttu-id="b1795-118">Чтобы получить сведения о каждом из ваших сертификатов Lync Server, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b1795-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="b1795-119">Вы также можете отфильтровать сведения о сертификате возврата на основе даты истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="b1795-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="b1795-120">Например, эта команда позволяет ограничить возвращаемые данные сертификатами, срок действия которых истечет (нельзя использовать после 1 июня 2014 г.).</span><span class="sxs-lookup"><span data-stu-id="b1795-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="b1795-121">Для получения дополнительных сведений обратитесь к справочной документации по командлету Get – CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="b1795-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="b1795-122">Обратите внимание, что несмотря на то, что командлет Test-Ксцертификатеконфигуратион существует, он не очень полезен администраторам.</span><span class="sxs-lookup"><span data-stu-id="b1795-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="b1795-123">(Вместо этого этот командлет используется в основном мастером сертификатов.) Несмотря на то, что командлет работает, возвращаемые им данные имеют минимальное значение, как показано в следующем примере вывода:</span><span class="sxs-lookup"><span data-stu-id="b1795-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="b1795-124">Использование отпечатков</span><span class="sxs-lookup"><span data-stu-id="b1795-124">Thumbprint Use</span></span>

<span data-ttu-id="b1795-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="b1795-125">\---------- ---</span></span>

<span data-ttu-id="b1795-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b1795-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="b1795-127">Просмотр выходных данных</span><span class="sxs-lookup"><span data-stu-id="b1795-127">Reviewing the output</span></span>

<span data-ttu-id="b1795-128">Командлет Get – CsCertificate возвращает сведения, аналогичные приведенным ниже, для каждого сертификата сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1795-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="b1795-129">Издатель: CN = Фабрикамка</span><span class="sxs-lookup"><span data-stu-id="b1795-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="b1795-130">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="b1795-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="b1795-131">Свойстве NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="b1795-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="b1795-132">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="b1795-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="b1795-133">Subject: CN = LYNC — SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="b1795-134">Алтернативенамес: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="b1795-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="b1795-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="b1795-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="b1795-136">Отпечаток: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="b1795-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="b1795-137">Использовать: по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b1795-137">Use : Default</span></span>

<span data-ttu-id="b1795-138">Как правило, основные проблемы, связанные с сертификатами Lync Server, включают даты и время, например время, когда сертификаты вступают в силу (свойстве NotBefore) или когда истечет срок их действия (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="b1795-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="b1795-139">Так как эти значения дат и времени важны, вы можете ограничить возвращаемые данные сведениями, такими как использование сертификата, серийный номер сертификата и Дата окончания срока действия сертификата; После этого вы сможете быстро просмотреть все сертификаты и срок их действия.</span><span class="sxs-lookup"><span data-stu-id="b1795-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="b1795-140">Чтобы получить только эти сведения, используйте команду вместе с параметрами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b1795-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="b1795-141">Эта команда возвращает данные, аналогичные приведенным ниже, при этом сертификаты сортируются в порядке их истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="b1795-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="b1795-142">Использование NotAfter SerialNumber</span><span class="sxs-lookup"><span data-stu-id="b1795-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="b1795-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="b1795-143">\--- ------------ --------</span></span>

<span data-ttu-id="b1795-144">611BB01200000000000C по умолчанию 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="b1795-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="b1795-145">Вебсервицесинтерал 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="b1795-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="b1795-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="b1795-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="b1795-147">Если у вас возникнут проблемы с сертификатом, вам может потребоваться просмотреть Алтернативенамес, настроенный для сертификата.</span><span class="sxs-lookup"><span data-stu-id="b1795-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="b1795-148">На первый взгляд кажется, что проблема.</span><span class="sxs-lookup"><span data-stu-id="b1795-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="b1795-149">По умолчанию, в зависимости от размера окна консоли, Get – CsCertificate может не отображать все имена:</span><span class="sxs-lookup"><span data-stu-id="b1795-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="b1795-150">Алтернативенамес: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="b1795-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="b1795-151">meet.fabrikam.com, admin. фабрика...}</span><span class="sxs-lookup"><span data-stu-id="b1795-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="b1795-152">Чтобы просмотреть все альтернативные имена, назначенные для сертификата, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="b1795-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="b1795-153">Должны отображаться все альтернативные имена сертификата:</span><span class="sxs-lookup"><span data-stu-id="b1795-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="b1795-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-154">sip.fabrikam.com</span></span>

<span data-ttu-id="b1795-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="b1795-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-156">meet.fabrikam.com</span></span>

<span data-ttu-id="b1795-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-157">admin.fabrikam.com</span></span>

<span data-ttu-id="b1795-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="b1795-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b1795-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1795-160">См. также</span><span class="sxs-lookup"><span data-stu-id="b1795-160">See Also</span></span>


[<span data-ttu-id="b1795-161">Get — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="b1795-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


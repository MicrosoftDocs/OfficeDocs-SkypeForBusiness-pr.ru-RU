---
title: 'Lync Server 2013: Проверка серверных сертификатов Lync Server 2013'
description: 'Lync Server 2013: Проверка серверных сертификатов Lync Server 2013.'
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
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543595"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="3dc24-103">Проверка серверных сертификатов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dc24-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dc24-104">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3dc24-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dc24-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="3dc24-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3dc24-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="3dc24-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dc24-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="3dc24-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3dc24-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3dc24-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dc24-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="3dc24-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3dc24-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3dc24-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3dc24-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="3dc24-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="3dc24-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3dc24-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3dc24-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3dc24-113">Description</span></span>

<span data-ttu-id="3dc24-114">Командлет Get-CsCertificate позволяет получить сведения о каждом из сертификатов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dc24-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="3dc24-115">Это особенно важно, так как сертификаты имеют встроенную дату истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="3dc24-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="3dc24-116">Например, срок действия сертификатов, выданных частными, обычно истечет через 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="3dc24-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="3dc24-117">Если какой-либо из ваших сертификатов Lync Server истечет, все функции будут потеряны до тех пор, пока сертификат не будет обновлен или заменен.</span><span class="sxs-lookup"><span data-stu-id="3dc24-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3dc24-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="3dc24-118">Running the test</span></span>

<span data-ttu-id="3dc24-119">Чтобы получить сведения о каждом из ваших сертификатов Lync Server, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3dc24-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="3dc24-120">Вы также можете отфильтровать сведения о сертификате возврата на основе даты истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="3dc24-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="3dc24-121">Например, эта команда позволяет ограничить возвращаемые данные сертификатами, срок действия которых истечет (нельзя использовать после 1 июня 2014 г.).</span><span class="sxs-lookup"><span data-stu-id="3dc24-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="3dc24-122">Для получения дополнительных сведений обратитесь к справочной документации по командлету Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="3dc24-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="3dc24-123">Обратите внимание, что несмотря на то, что командлет Test-CsCertificateConfiguration существует, он не очень полезен администраторам.</span><span class="sxs-lookup"><span data-stu-id="3dc24-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="3dc24-124">(Вместо этого этот командлет используется в основном мастером сертификатов.) Несмотря на то, что командлет работает, возвращаемые им данные имеют минимальное значение, как показано в следующем примере вывода:</span><span class="sxs-lookup"><span data-stu-id="3dc24-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="3dc24-125">Использование отпечатков</span><span class="sxs-lookup"><span data-stu-id="3dc24-125">Thumbprint Use</span></span>

<span data-ttu-id="3dc24-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="3dc24-126">\---------- ---</span></span>

<span data-ttu-id="3dc24-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3dc24-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="3dc24-128">Просмотр выходных данных</span><span class="sxs-lookup"><span data-stu-id="3dc24-128">Reviewing the output</span></span>

<span data-ttu-id="3dc24-129">Командлет Get-CsCertificate возвращает сведения, аналогичные приведенным ниже, для каждого сертификата сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dc24-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="3dc24-130">Издатель: CN = Фабрикамка</span><span class="sxs-lookup"><span data-stu-id="3dc24-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="3dc24-131">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="3dc24-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="3dc24-132">Свойстве NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="3dc24-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="3dc24-133">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="3dc24-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="3dc24-134">Subject: CN = LYNC — SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="3dc24-135">Алтернативенамес: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="3dc24-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="3dc24-136">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="3dc24-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="3dc24-137">Отпечаток: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="3dc24-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="3dc24-138">Использовать: по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3dc24-138">Use : Default</span></span>

<span data-ttu-id="3dc24-139">Как правило, основные проблемы, связанные с сертификатами Lync Server, включают даты и время, например время, когда сертификаты вступают в силу (свойстве NotBefore) или когда истечет срок их действия (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="3dc24-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="3dc24-140">Так как эти значения дат и времени важны, вы можете ограничить возвращаемые данные сведениями, такими как использование сертификата, серийный номер сертификата и Дата окончания срока действия сертификата; После этого вы сможете быстро просмотреть все сертификаты и срок их действия.</span><span class="sxs-lookup"><span data-stu-id="3dc24-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="3dc24-141">Чтобы получить только эти сведения, используйте команду вместе с параметрами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3dc24-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="3dc24-142">Эта команда возвращает данные, аналогичные приведенным ниже, при этом сертификаты сортируются в порядке их истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="3dc24-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="3dc24-143">Использование NotAfter SerialNumber</span><span class="sxs-lookup"><span data-stu-id="3dc24-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="3dc24-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="3dc24-144">\--- ------------ --------</span></span>

<span data-ttu-id="3dc24-145">611BB01200000000000C по умолчанию 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="3dc24-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="3dc24-146">Вебсервицесинтерал 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="3dc24-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="3dc24-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="3dc24-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="3dc24-148">Если у вас возникнут проблемы с сертификатом, вам может потребоваться просмотреть Алтернативенамес, настроенный для сертификата.</span><span class="sxs-lookup"><span data-stu-id="3dc24-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="3dc24-149">На первый взгляд кажется, что проблема.</span><span class="sxs-lookup"><span data-stu-id="3dc24-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="3dc24-150">По умолчанию в зависимости от размера окна консоли Get-CsCertificate могут не отображать все имена:</span><span class="sxs-lookup"><span data-stu-id="3dc24-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="3dc24-151">Алтернативенамес: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="3dc24-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="3dc24-152">meet.fabrikam.com, admin. фабрика...}</span><span class="sxs-lookup"><span data-stu-id="3dc24-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="3dc24-153">Чтобы просмотреть все альтернативные имена, назначенные для сертификата, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="3dc24-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="3dc24-154">Должны отображаться все альтернативные имена сертификата:</span><span class="sxs-lookup"><span data-stu-id="3dc24-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="3dc24-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-155">sip.fabrikam.com</span></span>

<span data-ttu-id="3dc24-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="3dc24-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-157">meet.fabrikam.com</span></span>

<span data-ttu-id="3dc24-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-158">admin.fabrikam.com</span></span>

<span data-ttu-id="3dc24-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="3dc24-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3dc24-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3dc24-161">См. также</span><span class="sxs-lookup"><span data-stu-id="3dc24-161">See Also</span></span>


[<span data-ttu-id="3dc24-162">Get — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="3dc24-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


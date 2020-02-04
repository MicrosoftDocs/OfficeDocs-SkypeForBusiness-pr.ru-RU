---
title: Проверка и отчет о функциональной готовности для использования проверки подлинности Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="993a0-102">Проверка и отчет о функциональной готовности для использования проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="993a0-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="993a0-103">_**Тема последнего изменения:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="993a0-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="993a0-104">Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="993a0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="993a0-105">С помощью командлета Windows PowerShell **Test-кскерберосаккаунтассигнмент** можно протестировать и сообщить о готовности назначения сайта для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="993a0-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="993a0-106">Эта команда отправляет запрос на сайт, указанный в требуемом параметре удостоверения.</span><span class="sxs-lookup"><span data-stu-id="993a0-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="993a0-107">Необязательный параметр отчета заставляет командлет записать отчет в формате HTML в C:\\журналы на компьютере, на котором она выполняется.</span><span class="sxs-lookup"><span data-stu-id="993a0-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="993a0-108">Необязательный параметр подробной информации выводит сведения о действиях на экран.</span><span class="sxs-lookup"><span data-stu-id="993a0-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="993a0-109">Тестирование и создание отчетов о готовности проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="993a0-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="993a0-110">Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="993a0-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="993a0-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="993a0-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="993a0-112">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="993a0-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="993a0-113">Например:</span><span class="sxs-lookup"><span data-stu-id="993a0-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Тестирование и составление отчетов о готовности к проверке подлинности Kerberos
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
ms.openlocfilehash: c3c5a2c83d664182226decb88ab6bd1c34d6d3a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="3e580-102">Тестирование и составление отчетов о готовности к использованию проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e580-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e580-103">_**Последнее изменение темы:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="3e580-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="3e580-104">Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3e580-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="3e580-105">С помощью командлета Windows PowerShell **Test-CsKerberosAccountAssignment** вы можете протестировать и сообщить о готовности к работоспособности назначения сайта для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3e580-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="3e580-106">Эта команда запрашивает сайт, указанный обязательным параметром Identity.</span><span class="sxs-lookup"><span data-stu-id="3e580-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="3e580-107">Необязательный параметр Report создает командлет для записи HTML-отчета в журнал C\\: журналы на компьютере, на котором выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="3e580-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="3e580-108">Дополнительный параметр Verbose передает данные об активности на экран.</span><span class="sxs-lookup"><span data-stu-id="3e580-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="3e580-109">Тестирование и передача данных о функциональной готовности сайта для проверки подлинности Kerberos</span><span class="sxs-lookup"><span data-stu-id="3e580-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="3e580-110">В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="3e580-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="3e580-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3e580-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3e580-112">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e580-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="3e580-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="3e580-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>


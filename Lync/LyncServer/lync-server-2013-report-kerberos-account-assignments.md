---
title: 'Lync Server 2013: отчет о назначениях учетных записей Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f44f187b751ec9baa78df8890e64332070d8b33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="1f5a0-102">Отчет о назначениях учетных записей Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f5a0-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f5a0-103">_**Последнее изменение темы:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="1f5a0-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="1f5a0-104">Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1f5a0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="1f5a0-105">Можно использовать командлет **Get-CsKerberosAccountAssignment** для запроса информации о назначениях учетной записи проверки подлинности Kerberos и получения сведений о текущих назначениях в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="1f5a0-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="1f5a0-106">Запрос назначений учетной записи проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="1f5a0-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="1f5a0-107">В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="1f5a0-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="1f5a0-108">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1f5a0-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1f5a0-109">В командной строке выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="1f5a0-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="1f5a0-110">Чтобы запросить все назначения учетной записи проверки подлинности Kerberos в организации и возвратить сведения о каждом из них, запустите командлет без каких-либо параметров:</span><span class="sxs-lookup"><span data-stu-id="1f5a0-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="1f5a0-111">Чтобы запросить все назначения учетной записи проверки подлинности Kerberos в развертывании и возвратить сведения о каждом из них, запустите командлет с параметром Identity:</span><span class="sxs-lookup"><span data-stu-id="1f5a0-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="1f5a0-112">Например:</span><span class="sxs-lookup"><span data-stu-id="1f5a0-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="1f5a0-113">Чтобы запросить все назначения учетной записи проверки подлинности Kerberos на отдельном сайте и возвратить сведения о каждом из них, запустите командлет с параметром Filter:</span><span class="sxs-lookup"><span data-stu-id="1f5a0-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="1f5a0-114">Например:</span><span class="sxs-lookup"><span data-stu-id="1f5a0-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1f5a0-115">При указании значения \*имя_сайта для параметра Filter возвращает информацию обо всех сайтах, содержащих указанное имя в любой части идентификатора сайта (например, все сайты, содержащие слово Redmond в идентификаторе).</span><span class="sxs-lookup"><span data-stu-id="1f5a0-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


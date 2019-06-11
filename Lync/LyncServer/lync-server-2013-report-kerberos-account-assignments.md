---
title: 'Lync Server 2013: отчет о назначениях для учетной записи Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="ffe52-102">Отчет о назначениях для учетной записи Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffe52-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe52-103">_**Тема последнего изменения:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="ffe52-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="ffe52-104">Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="ffe52-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="ffe52-105">Вы можете использовать командлет **Get-кскерберосаккаунтассигнмент** , чтобы запросить сведения о назначениях учетных записей проверки подлинности Kerberos и сообщить о текущих заданиях в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ffe52-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="ffe52-106">Запрос назначений учетной записи для проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="ffe52-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="ffe52-107">Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="ffe52-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="ffe52-108">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ffe52-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ffe52-109">В командной строке выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="ffe52-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="ffe52-110">Чтобы запросить все назначения учетной записи для проверки подлинности Kerberos в Организации и вернуть сведения о назначениях для каждого из них, запустите командлет без параметров.</span><span class="sxs-lookup"><span data-stu-id="ffe52-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="ffe52-111">Чтобы запросить все назначения учетной записи для проверки подлинности Kerberos в развертывании и вернуть сведения о назначениях сайтов для каждого из них, выполните командлет с параметром Identity.</span><span class="sxs-lookup"><span data-stu-id="ffe52-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="ffe52-112">Например:</span><span class="sxs-lookup"><span data-stu-id="ffe52-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="ffe52-113">Чтобы запросить все назначения учетной записи проверки подлинности Kerberos на одном сайте и вернуть сведения о назначениях для каждого из них, запустите командлет с параметром Filter.</span><span class="sxs-lookup"><span data-stu-id="ffe52-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="ffe52-114">Например:</span><span class="sxs-lookup"><span data-stu-id="ffe52-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ffe52-115">Указание \* SiteName для параметра Filter возвращает сведения обо всех сайтах, которые содержат указанное имя сайта в любом месте идентификатора сайта (например, все сайты, содержащие строку Redmond в идентификаторе сайта).</span><span class="sxs-lookup"><span data-stu-id="ffe52-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: удаление проверки подлинности Kerberos для сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f030083bc49822f1d41e297388f6ca7dbf66d397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="c8fbf-102">В Lync Server 2013 удаление проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="c8fbf-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8fbf-103">_**Тема последнего изменения:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="c8fbf-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="c8fbf-104">Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="c8fbf-105">Если необходимо удалить проверку подлинности Kerberos с сайта или снять с учета сайта, необходимо удалить назначение учетной записи для проверки подлинности Kerberos с сайта с помощью командлета **Remove-кскерберосаккаунтассигнмент** .</span><span class="sxs-lookup"><span data-stu-id="c8fbf-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="c8fbf-106">Выполните описанные ниже действия, чтобы удалить назначение учетной записи проверки подлинности Kerberos, удаляя назначение со всех компьютеров сайта.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="c8fbf-107">Если вы безвозвратно удаляете учетную запись с поддержкой Kerberos, вы должны использовать оснастку "пользователи и компьютеры Active Directory", чтобы удалить ее из доменных служб Active Directory после удаления задания.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="c8fbf-108">Если вы планируете использовать объект в будущем, вам может понадобиться сохранить объект Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="c8fbf-109">Удаление проверки подлинности Kerberos с сайта</span><span class="sxs-lookup"><span data-stu-id="c8fbf-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="c8fbf-110">Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="c8fbf-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c8fbf-112">В командной строке выполните следующие две команды:</span><span class="sxs-lookup"><span data-stu-id="c8fbf-112">From the command line, run the following two commands:</span></span>
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <span data-ttu-id="c8fbf-113">Например:</span><span class="sxs-lookup"><span data-stu-id="c8fbf-113">For example:</span></span>
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c8fbf-114">После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8fbf-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


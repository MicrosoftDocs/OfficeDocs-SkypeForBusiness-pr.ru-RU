---
title: 'Lync Server 2013: Удаление проверки подлинности Kerberos для сайта'
description: 'Lync Server 2013: Удаление проверки подлинности Kerberos на сайте.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553535"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="82827-103">В Lync Server 2013 удаление проверки подлинности Kerberos для сайта</span><span class="sxs-lookup"><span data-stu-id="82827-103">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82827-104">_**Последнее изменение темы:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="82827-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="82827-105">Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="82827-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="82827-106">Если необходимо удалить проверку подлинности Kerberos с узла или прекратить использование узла, необходимо удалить назначение учетной записи проверки подлинности Kerberos с узла с помощью командлета **Remove-CsKerberosAccountAssignment**.</span><span class="sxs-lookup"><span data-stu-id="82827-106">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="82827-107">Используйте следующую процедуру для удаления назначения учетной записи проверки подлинности Kerberos, что приводит к удалению назначения со всех компьютеров узла.</span><span class="sxs-lookup"><span data-stu-id="82827-107">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="82827-108">Если вы безвозвратно удаляете учетную запись с включенной проверкой подлинности Kerberos, следует использовать оснастку "Active Directory — пользователи и компьютеры", чтобы удалить его из доменных служб Active Directory после удаления назначения.</span><span class="sxs-lookup"><span data-stu-id="82827-108">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="82827-109">Если вы планируете использовать данный объект в дальнейшем, возможно, потребуется сохранить объект Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82827-109">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="82827-110">Удаление проверки подлинности Kerberos с узла</span><span class="sxs-lookup"><span data-stu-id="82827-110">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="82827-111">В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="82827-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="82827-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="82827-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="82827-113">Выполните две следующие команды в командной строке:</span><span class="sxs-lookup"><span data-stu-id="82827-113">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="82827-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="82827-114">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="82827-115">После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82827-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: назначение учетной записи проверки подлинности Kerberos для сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb755f7e7b814d4ca643bd04ddfc0241b4d96d60
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="705c6-102">Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="705c6-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="705c6-103">_**Тема последнего изменения:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="705c6-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="705c6-104">Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="705c6-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="705c6-105">После создания учетной записи Kerberos ее необходимо назначить сайту.</span><span class="sxs-lookup"><span data-stu-id="705c6-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="705c6-106">Это сайт Lync Server 2013, а не сайт Active Directory.</span><span class="sxs-lookup"><span data-stu-id="705c6-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="705c6-107">Вы можете создать несколько учетных записей проверки подлинности Kerberos для каждого развертывания, но вы можете назначить сайту только одну учетную запись.</span><span class="sxs-lookup"><span data-stu-id="705c6-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="705c6-108">Чтобы назначить сайту ранее созданную учетную запись для проверки подлинности Kerberos, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="705c6-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="705c6-109">Подробнее о том, как создать учетную запись Kerberos, можно найти [в разделе Создание учетной записи проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="705c6-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="705c6-110">Назначение учетной записи проверки подлинности Kerberos сайту</span><span class="sxs-lookup"><span data-stu-id="705c6-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="705c6-111">Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="705c6-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="705c6-112">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="705c6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="705c6-113">В командной строке выполните следующие две команды:</span><span class="sxs-lookup"><span data-stu-id="705c6-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="705c6-114">Например:</span><span class="sxs-lookup"><span data-stu-id="705c6-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="705c6-115">Параметр UserAccount необходимо указать с помощью формата домен \ пользователь.</span><span class="sxs-lookup"><span data-stu-id="705c6-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="705c6-116">Формат User@Domain. расширение не поддерживается для ссылок на объекты компьютера, созданные для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="705c6-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="705c6-117">**Необязательно**: возможно, вы настроили для своих веб-служб полное доменное имя (FQDN), как и в случае [изменения URL — в Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="705c6-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="705c6-118">В этом случае вам потребуется также добавить SPN для этого полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="705c6-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="705c6-119">Например, если полное доменное имя — WebService. contoso. local, вы можете выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="705c6-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="705c6-120">После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="705c6-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


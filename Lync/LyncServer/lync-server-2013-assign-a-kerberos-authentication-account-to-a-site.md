---
title: 'Lync Server 2013: Назначение учетной записи проверки подлинности Kerberos сайту'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2d8d2a68914ee45d741d161ff6137015f3a13e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="cab2d-102">Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cab2d-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cab2d-103">_**Последнее изменение темы:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="cab2d-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="cab2d-104">Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cab2d-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="cab2d-105">После создания учетной записи Kerberos вам следует назначить ее сайту.</span><span class="sxs-lookup"><span data-stu-id="cab2d-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="cab2d-106">Это сайт Lync Server 2013, а не сайт Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cab2d-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="cab2d-107">Для одного развертывания вы можете создать несколько учетных записей для проверки подлинности Kerberos, однако сайту можно назначить всего одну из них.</span><span class="sxs-lookup"><span data-stu-id="cab2d-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="cab2d-108">Используйте описанную ниже процедуру, чтобы назначить сайту ранее созданную учетную запись для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="cab2d-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="cab2d-109">Более подробную информацию о создании учетной записи Kerberos можно узнать [в статье Создание учетной записи проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="cab2d-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="cab2d-110">Назначение учетной записи для проверки подлинности Kerberos сайту</span><span class="sxs-lookup"><span data-stu-id="cab2d-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="cab2d-111">В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="cab2d-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="cab2d-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cab2d-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cab2d-113">Выполните две следующие команды в командной строке:</span><span class="sxs-lookup"><span data-stu-id="cab2d-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="cab2d-114">Например:</span><span class="sxs-lookup"><span data-stu-id="cab2d-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="cab2d-p102">Вам следует указать параметр UserAccount, используя формат «домен\пользователь». Использование формата «пользователь@домен.расширение» для ссылки на объекты-компьютеры, созданные для проверки подлинности Kerberos, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cab2d-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="cab2d-117">**Необязательно**: возможно, вы настроили полное доменное имя переопределения (полное доменное имя) для своих веб-служб, как в случае [изменения URL-адрес веб-служб в Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="cab2d-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="cab2d-118">В этом случае вам потребуется также добавить имя субъекта-службы для полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="cab2d-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="cab2d-119">Например, если полное доменное имя было: WebServices. contoso. local, запустите:</span><span class="sxs-lookup"><span data-stu-id="cab2d-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cab2d-120">После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cab2d-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: создание учетной записи проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="71c57-102">Создание учетной записи проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c57-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c57-103">_**Последнее изменение темы:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="71c57-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="71c57-104">Чтобы успешно выполнить процедуру, необходимо выполнить вход на сервер или в домен по крайней мере с правами члена группы "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="71c57-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="71c57-105">Вы можете создать учетные записи проверки подлинности Kerberos для каждого сайта или одну учетную запись для всех сайтов.</span><span class="sxs-lookup"><span data-stu-id="71c57-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="71c57-106">С помощью командлетов Windows PowerShell можно создавать учетные записи и управлять ими, в том числе определять учетные записи, назначенные каждому сайту.</span><span class="sxs-lookup"><span data-stu-id="71c57-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="71c57-107">В построителе топологий и на панели управления Lync Server 2013 не отображаются учетные записи проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="71c57-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="71c57-108">Чтобы создать одну или несколько учетных записей пользователей для проверки подлинности Kerberos используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="71c57-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="71c57-109">Создание учетной записи Kerberos</span><span class="sxs-lookup"><span data-stu-id="71c57-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="71c57-110">В качестве члена группы администраторов домена войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="71c57-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="71c57-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="71c57-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="71c57-112">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71c57-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="71c57-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="71c57-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="71c57-114">Убедитесь в том, что был создан объект компьютера. Для этого откройте оснастку "Active Directory — пользователи и компьютеры", разверните контейнер **Пользователи** и проверьте, имеется ли в нем объект компьютера для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="71c57-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


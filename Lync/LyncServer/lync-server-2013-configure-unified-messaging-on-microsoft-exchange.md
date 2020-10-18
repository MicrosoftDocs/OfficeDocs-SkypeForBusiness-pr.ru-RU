---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями в Microsoft Exchange'
description: 'Lync Server 2013: Настройка единой системы обмена сообщениями в Microsoft Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577525"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="59cef-103">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59cef-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59cef-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="59cef-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="59cef-105">В этом разделе описывается настройка единой системы обмена сообщениями Exchange на сервере Microsoft Exchange для использования с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="59cef-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59cef-106">В примерах, приведенных в этом разделе, представлен синтаксис для Exchange 2007 с помощью командной консоли Exchange.</span><span class="sxs-lookup"><span data-stu-id="59cef-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="59cef-107">Если вы используете Exchange 2010 или Exchange 2013, ознакомьтесь с соответствующей документацией, как показано на этой странице.</span><span class="sxs-lookup"><span data-stu-id="59cef-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="59cef-108">Настройка сервера, на котором работает единая система обмена сообщениями Exchange Server</span><span class="sxs-lookup"><span data-stu-id="59cef-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="59cef-109">Создайте абонентскую группу универсального кода ресурса (URI) SIP для каждого профиля расположения вашей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="59cef-109">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="59cef-110">Если вы решили использовать консоль управления Exchange, создайте новую абонентскую абонентскую систему с **защищенным (предпочтительным)** параметром безопасности.</span><span class="sxs-lookup"><span data-stu-id="59cef-110">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="59cef-111">Если для параметра безопасности задано значение <STRONG>SIP Secured</STRONG> , требующее обязательного шифрования только для трафика SIP, как было сказано ранее, обратите внимание на то, что этот параметр безопасности для абонентской группы недостаточен, если для пула переднего плана настроено требование шифрования, что означает, что для пула требуется шифрование для трафика SIP и RTP.</span><span class="sxs-lookup"><span data-stu-id="59cef-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="59cef-112">Если параметры безопасности абонентской группы и пула несовместимы, все вызовы Exchange единой системы обмена сообщениями из пула переднего плана завершатся ошибкой, что приведет к ошибке, указывающей на то, что параметр безопасности несовместим.</span><span class="sxs-lookup"><span data-stu-id="59cef-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="59cef-113">Если используется Командная консоль Exchange, введите:</span><span class="sxs-lookup"><span data-stu-id="59cef-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="59cef-114">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="59cef-114">For details, see:</span></span>
    
      - <span data-ttu-id="59cef-115">Для Office Communications Server 2007 в разделе "как создать абонентскую систему URI SIP единой системы обмена сообщениями" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) и "New – UMDialPlan: Exchange 2007 Help" [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .</span><span class="sxs-lookup"><span data-stu-id="59cef-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="59cef-116">Для Exchange 2010 в разделе "Создание абонентской группы единой системы обмена сообщениями" [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) и "New – UMDialPlan: Exchange 2010 Help" [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .</span><span class="sxs-lookup"><span data-stu-id="59cef-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="59cef-117">Для Exchange 2013 в разделе "Единая система обмена сообщениями" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="59cef-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59cef-118">Выбор уровня безопасности <STRONG>сипсекуред</STRONG> или <STRONG>Secure зависит от того,</STRONG> активирована или отключена передача протокола безопасности в режиме реального времени (SRTP) для шифрования мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="59cef-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="59cef-119">Для интеграции Lync Server 2010 с единой системой обмена сообщениями Exchange она должна соответствовать уровню шифрования в конфигурации мультимедиа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="59cef-120">Конфигурацию мультимедиа Lync Server можно просмотреть, выполнив командлет <STRONG>Get – CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="59cef-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="59cef-121">Дополнительные сведения можно найти в разделе Get-CsMediaConfiguration в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="59cef-122">Дополнительные сведения о выборе соответствующего параметра безопасности VoIP приведены в разделе <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="59cef-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="59cef-123">Выполните следующий командлет для получения полного доменного имени (FQDN) для каждой абонентской группы единой системы обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="59cef-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="59cef-124">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="59cef-124">For details, see:</span></span>
    
      - <span data-ttu-id="59cef-125">Для Exchange 2007 в разделе "Get – UMDialplan: Exchange 2007 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .</span><span class="sxs-lookup"><span data-stu-id="59cef-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="59cef-126">Для Exchange 2010 в разделе "Get – UMDialplan: Exchange 2010 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .</span><span class="sxs-lookup"><span data-stu-id="59cef-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="59cef-127">Для Exchange 2013 в разделе "Единая система обмена сообщениями" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="59cef-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="59cef-128">Запишите имя абонентской группы каждой абонентской группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="59cef-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="59cef-129">В зависимости от используемой версии Exchange Server может потребоваться использовать полное доменное имя каждого имени абонентской группы в соответствии с именем каждой соответствующей абонентской группы Lync Server, чтобы имена абонентских групп соотнесены.</span><span class="sxs-lookup"><span data-stu-id="59cef-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59cef-130">Имена абонентской группы Lync Server должны сопоставлять имена абонентской группы единой системы обмена сообщениями только в том случае, если абонентская группа единой системы обмена сообщениями работает в более <EM>ранней</EM> версии Exchange, чем Exchange 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="59cef-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="59cef-131">Добавьте абонентскую группу на сервер, на котором работает единая система обмена сообщениями Exchange, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="59cef-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="59cef-132">Если вы решили использовать консоль управления Exchange, вы можете добавить абонентскую схему из страницы свойств для сервера.</span><span class="sxs-lookup"><span data-stu-id="59cef-132">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="59cef-133">Конкретные инструкции можно найти в документации по продукту Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-133">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="59cef-134">В разделе "как добавить сервер единой системы обмена сообщениями в абонентскую абонентию для Exchange 2007" [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .</span><span class="sxs-lookup"><span data-stu-id="59cef-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="59cef-135">Для Exchange 2010 можно ознакомиться в статье "Просмотр или Настройка свойств сервера единой системы обмена сообщениями" по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .</span><span class="sxs-lookup"><span data-stu-id="59cef-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="59cef-136">Для Exchange 2013 в разделе "Единая система обмена сообщениями" [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="59cef-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="59cef-137">Если вы используете командную консоль Exchange, выполните указанные ниже действия для каждого сервера единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="59cef-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59cef-138">Перед выполнением следующего действия Убедитесь, что все пользователи корпоративной голосовой связи настроены с помощью почтового ящика Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="59cef-139">Для Exchange 2007 ознакомьтесь с разадресом библиотеки TechNet для Exchange Server 2007 по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .</span><span class="sxs-lookup"><span data-stu-id="59cef-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="59cef-140">Для Exchange 2010 ознакомьтесь с разадресом библиотеки TechNet для Exchange Server 2010 по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .</span><span class="sxs-lookup"><span data-stu-id="59cef-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="59cef-141">При указании политики почтовых ящиков для каждой абонентской группы, созданной на шаге 1, выберите либо политику по умолчанию, либо одну из созданных.</span><span class="sxs-lookup"><span data-stu-id="59cef-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="59cef-142">Перейдите к разделу \<Exchange installation directory\> \\ сценарии, а затем, если Exchange развернут в отдельном лесу, введите:</span><span class="sxs-lookup"><span data-stu-id="59cef-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="59cef-143">Если Exchange развертывается в нескольких лесах, введите:</span><span class="sxs-lookup"><span data-stu-id="59cef-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="59cef-144">где полное доменное имя леса указывает лес, в котором развернут Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="59cef-145">Если вы используете одну или несколько абонентских групп единой системы обмена сообщениями, которые связаны с несколькими шлюзами IP, перейдите к шагу 6.</span><span class="sxs-lookup"><span data-stu-id="59cef-145">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="59cef-146">Если абонентские группы связаны только с одним шлюзом IP, пропустите шаг 6.</span><span class="sxs-lookup"><span data-stu-id="59cef-146">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59cef-147">Обязательно перезапустите службу <STRONG>Сервер переднего плана Lync Server</STRONG> (rtcsrv.exe) <EM>после</EM> выполнения скрипта exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="59cef-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="59cef-148">В противном случае Lync Server не будет обнаруживать единую систему обмена сообщениями в топологии.</span><span class="sxs-lookup"><span data-stu-id="59cef-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="59cef-149">С помощью командной консоли Exchange или консоли управления Exchange отключите исходящий вызов для всех шлюзов IP, которые связаны с каждой абонентской абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="59cef-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59cef-150">Это необходимо, чтобы убедиться, что исходящие вызовы, выполняемые сервером, на котором работает единая система обмена сообщениями Exchange Server, для внешних пользователей (например, как в случае с помощью сценариев проигрывания на телефоне) надежно проходят через корпоративный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="59cef-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59cef-151">При выборе шлюза IP единой системы обмена сообщениями, с помощью которого можно разрешить исходящие вызовы, выберите один из них, который скорее всего будет обрабатывать весь трафик.</span><span class="sxs-lookup"><span data-stu-id="59cef-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="59cef-152">Не разрешать исходящий трафик через шлюз IP, который подключается к пулу директорий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="59cef-153">Кроме того, не следует использовать пулы на другом центральном сайте или сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="59cef-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="59cef-154">Для блокирования исходящих вызовов через шлюз IP можно использовать любой из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="59cef-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="59cef-155">Если вы используете командную консоль Exchange, отключите каждый шлюз IP, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="59cef-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="59cef-156">Для Exchange 2007, в разделе "Set – UMIPGateway: Exchange 2007 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .</span><span class="sxs-lookup"><span data-stu-id="59cef-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="59cef-157">Для Exchange 2010, в разделе "Set – UMIPGateway: Exchange 2010 Help" в [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .</span><span class="sxs-lookup"><span data-stu-id="59cef-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="59cef-158">Если вы используете консоль управления Exchange, снимите флажок **Разрешить исходящие вызовы через этот шлюз IP** .</span><span class="sxs-lookup"><span data-stu-id="59cef-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59cef-159">Если абонентская группа URI SIP единой системы обмена сообщениями связана только с одним шлюзом IP, не запретите исходящие вызовы через этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="59cef-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="59cef-160">Создание автосекретаря единой системы обмена сообщениями для каждой абонентской группы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59cef-161">Имя автосекретаря не должно содержать пробелов.</span><span class="sxs-lookup"><span data-stu-id="59cef-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="59cef-162">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="59cef-162">For details, see:</span></span>
    
      - <span data-ttu-id="59cef-163">В разделе "New – UMAutoAttendant используется: Exchange 2007 Help" в Exchange 2007 [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .</span><span class="sxs-lookup"><span data-stu-id="59cef-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="59cef-164">В разделе "New – UMAutoAttendant используется: Exchange 2010 Help" в Exchange 2010 [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .</span><span class="sxs-lookup"><span data-stu-id="59cef-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="59cef-165">Следующий шаг необходимо выполнить для каждого пользователя после включения пользователей Lync Server для корпоративной голосовой связи и получения сведений об URI SIP.</span><span class="sxs-lookup"><span data-stu-id="59cef-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="59cef-166">Свяжите пользователей единой системы обмена сообщениями Exchange (каждая из которых должна быть настроена с помощью почтового ящика Exchange) с абонентской группой единой системы обмена сообщениями и Создайте URI SIP для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="59cef-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59cef-167"><STRONG>Сипресаурцеидентифиер</STRONG> в следующем примере должен быть SIP адресом пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59cef-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="59cef-168">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="59cef-168">For details, see:</span></span>
    
      - <span data-ttu-id="59cef-169">Для Exchange 2007 см. в разделе "Enable – UMMailbox: Exchange 2007 Help" [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .</span><span class="sxs-lookup"><span data-stu-id="59cef-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="59cef-170">Для Exchange 2010 см. в разделе "Enable – UMMailbox: Exchange 2010 Help" [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .</span><span class="sxs-lookup"><span data-stu-id="59cef-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


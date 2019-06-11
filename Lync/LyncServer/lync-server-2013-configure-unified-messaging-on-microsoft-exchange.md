---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями на сервере Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcbdbfbca5f532b1ca192cc0e9d89e93e3c8acb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="9704e-102">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9704e-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9704e-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9704e-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9704e-104">В этой статье описано, как настроить единую систему обмена сообщениями Exchange (UM) на сервере Microsoft Exchange для использования с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="9704e-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9704e-105">Примеры командлетов в этом разделе содержат синтаксис для версии Exchange 2007 среды Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9704e-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="9704e-106">Если вы используете Exchange 2010 или Exchange 2013, ознакомьтесь с соответствующей документацией в соответствии с указанными ссылками.</span><span class="sxs-lookup"><span data-stu-id="9704e-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="9704e-107">Настройка сервера, на котором работает UM-сервер Exchange</span><span class="sxs-lookup"><span data-stu-id="9704e-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="9704e-108">Создайте абонентскую группу SIP (универсального кода ресурса) для каждого из профилей местоположения вашего голоса.</span><span class="sxs-lookup"><span data-stu-id="9704e-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="9704e-109">Если вы решили использовать консоль управления Exchange, создайте новую абонентскую группу с защищенным параметром безопасности **(предпочтительно)**.</span><span class="sxs-lookup"><span data-stu-id="9704e-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9704e-110">Если для параметра безопасности задано значение " <STRONG>SIP secures</STRONG> ", для которого требуется шифрование только за трафик SIP, как было рекомендовано, обратите внимание на то, что этот параметр безопасности для абонентской группы недостаточен, если пул переднего плана настроен таким образом, что требуется шифрование. для пула требуется шифрование на трафиках SIP и RTP.</span><span class="sxs-lookup"><span data-stu-id="9704e-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="9704e-111">Если параметры безопасности для абонентской группы и пула несовместимы, все звонки на Exchange UM из пула переднего плана будут завершаться сбоем, что приведет к ошибке, указывающей на то, что у вас есть несовместимый параметр безопасности.</span><span class="sxs-lookup"><span data-stu-id="9704e-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="9704e-112">Если вы используете консоль управления Exchange, введите:</span><span class="sxs-lookup"><span data-stu-id="9704e-112">If you use the Exchange Management Shell, type:</span></span>
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    <span data-ttu-id="9704e-113">Для получения дополнительных сведений см.:</span><span class="sxs-lookup"><span data-stu-id="9704e-113">For details, see:</span></span>
    
      - <span data-ttu-id="9704e-114">В Office Communications Server 2007 вы можете ознакомиться с разрешениями "Создание абонентской группы SIP для единой [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) системы обмена сообщениями" и "New-Умдиалплан: [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)Exchange 2007".</span><span class="sxs-lookup"><span data-stu-id="9704e-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="9704e-115">В [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)Exchange 2010 вы видите раздел "Создание абонентской группы единой системы [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) обмена сообщениями" на странице "New-умдиалплан: Exchange 2010".</span><span class="sxs-lookup"><span data-stu-id="9704e-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="9704e-116">Для Exchange 2013 следует ознакомиться в [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".</span><span class="sxs-lookup"><span data-stu-id="9704e-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9704e-117">Выбор уровня безопасности <STRONG>сипсекуред</STRONG> или <STRONG>Защита</STRONG> зависит от того, активирована или деактивирована ли протокол передачи данных в режиме реального времени (SRTP) для шифрования мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9704e-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="9704e-118">Интеграция с единой системой обмена сообщениями Exchange для интеграции с Lync Server 2010 соответствует уровню шифрования в конфигурации мультимедиа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="9704e-119">Чтобы просмотреть конфигурацию мультимедиа Lync Server, запустите командлет <STRONG>Get-ксмедиаконфигуратион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="9704e-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="9704e-120">Подробности можно найти в разделе Get-Ксмедиаконфигуратион в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="9704e-121">Подробнее о том, как выбрать соответствующий параметр безопасности в службе VoIP, можно найти <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">в разделе процесс развертывания для интеграции локальной системы обработки сообщений и Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9704e-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="9704e-122">Чтобы получить полное доменное имя (FQDN) для каждой абонентской группы единой системы обмена сообщениями, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="9704e-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="9704e-123">Для получения дополнительных сведений см.:</span><span class="sxs-lookup"><span data-stu-id="9704e-123">For details, see:</span></span>
    
      - <span data-ttu-id="9704e-124">Дополнительные сведения об Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)статье "Get-Умдиалплан: Exchange 2007".</span><span class="sxs-lookup"><span data-stu-id="9704e-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="9704e-125">Дополнительные сведения об Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)статье "Get-Умдиалплан: Exchange 2010".</span><span class="sxs-lookup"><span data-stu-id="9704e-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="9704e-126">Для Exchange 2013 следует ознакомиться в [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".</span><span class="sxs-lookup"><span data-stu-id="9704e-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="9704e-127">Запишите имя абонентской группы для каждой абонентской группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9704e-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="9704e-128">В зависимости от используемой версии Exchange Server может потребоваться использовать полное доменное имя каждого имени абонентского плана в соответствии с именем каждой соответствующей абонентской группы Lync Server, чтобы имена абонентских групп соответствовали друг другу.</span><span class="sxs-lookup"><span data-stu-id="9704e-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9704e-129">Имена абонентской группы Lync Server должны совпадать с именами абонентских групп UM только в том случае, если абонентская группа UM <EM></EM> работает в более ранней версии Exchange, чем Exchange 2010 с пакетом обновления 1.</span><span class="sxs-lookup"><span data-stu-id="9704e-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="9704e-130">Добавьте абонентскую группу на сервер, на котором запущена служба Exchange UM, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="9704e-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="9704e-131">Если вы решили использовать консоль управления Exchange, вы можете добавить абонентскую группу из страницы свойств сервера.</span><span class="sxs-lookup"><span data-stu-id="9704e-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="9704e-132">Конкретные инструкции можно найти в документации по продукту Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="9704e-133">Сведения о том, как добавить сервер единой системы обмена сообщениями в абонентскую группу Exchange 2007 [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681), можно найти по адресу ".</span><span class="sxs-lookup"><span data-stu-id="9704e-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="9704e-134">Для Exchange 2010 вы увидите в [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)разделе "Просмотр или Настройка свойств сервера UM".</span><span class="sxs-lookup"><span data-stu-id="9704e-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="9704e-135">Для Exchange 2013 следует ознакомиться в [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)разделе "Единая система обмена сообщениями".</span><span class="sxs-lookup"><span data-stu-id="9704e-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="9704e-136">Если вы используете командную консоль Exchange, выполните указанные ниже действия для каждого из серверов Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="9704e-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umservice -instance $ums[0]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9704e-137">Перед выполнением следующего действия Убедитесь в том, что все пользователи организации голосовой связи настроены с помощью почтового ящика Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="9704e-138">Сведения об Exchange 2007 можно найти в библиотеке TechNet на сайте Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9704e-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="9704e-139">Сведения об Exchange 2010 можно найти в библиотеке TechNet на сайте Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9704e-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="9704e-140">При указании политики почтовых ящиков для каждой абонентской группы, созданной в действии 1, выберите либо политику по умолчанию, либо ее созданную.</span><span class="sxs-lookup"><span data-stu-id="9704e-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="9704e-141">Перейдите к \<разделу\>\\сценарии установки Exchange, а затем, если Exchange развернут в одном лесе, введите:</span><span class="sxs-lookup"><span data-stu-id="9704e-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="9704e-142">Если Exchange развернут в нескольких лесах, введите:</span><span class="sxs-lookup"><span data-stu-id="9704e-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    <span data-ttu-id="9704e-143">где полное доменное имя леса определяет лес, в котором развернут Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="9704e-144">Если у вас есть одна или несколько абонентских групп UM, которые связаны с несколькими IP-шлюзами, перейдите к действию 6.</span><span class="sxs-lookup"><span data-stu-id="9704e-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="9704e-145">Если абонентские группы связаны только с одним IP-шлюзом, пропустите шаг 6.</span><span class="sxs-lookup"><span data-stu-id="9704e-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9704e-146"><EM>После</EM> запуска ексчукутил. ps1 убедитесь в том, что вы перезапустите службу <STRONG>внешнего сервера Lync Server</STRONG> (ртксрв. exe).</span><span class="sxs-lookup"><span data-stu-id="9704e-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="9704e-147">В противном случае Lync Server не будет определять единую систему обмена сообщениями в топологии.</span><span class="sxs-lookup"><span data-stu-id="9704e-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="9704e-148">Используя среду управления Exchange или консоль управления Exchange, отключите исходящие вызовы для всех IP-шлюзов, связанных с каждой из ваших абонентских планов.</span><span class="sxs-lookup"><span data-stu-id="9704e-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9704e-149">Этот этап необходим для того, чтобы убедиться в том, что исходящие вызовы на сервере, на котором работает единая система обмена сообщениями Exchange, (например, как в случае с сценариями воспроизведения на телефоне) надежно просматривают корпоративный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="9704e-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9704e-150">При выборе IP-шлюза UM, через который разрешены исходящие вызовы, выберите тот, который скорее всего будет обрабатывать весь трафик.</span><span class="sxs-lookup"><span data-stu-id="9704e-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="9704e-151">Не разрешать исходящий трафик через шлюз IP, который подключается к группе режиссеров Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="9704e-152">Также Избегайте пулов на другом центральном сайте или сайте ветви.</span><span class="sxs-lookup"><span data-stu-id="9704e-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="9704e-153">Для блокирования исходящих звонков через шлюз IP можно использовать один из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="9704e-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="9704e-154">Если вы используете консоль управления Exchange, отключите каждый шлюз IP, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9704e-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        <span data-ttu-id="9704e-155">Инструкции для Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)разделе "Set-Умипгатевай: Exchange 2007 Help".</span><span class="sxs-lookup"><span data-stu-id="9704e-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="9704e-156">Инструкции для Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)разделе "Set-Умипгатевай: Exchange 2010 Help".</span><span class="sxs-lookup"><span data-stu-id="9704e-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="9704e-157">Если вы используете консоль управления Exchange, снимите флажок **Разрешить исходящие вызовы через этот IP-шлюз** .</span><span class="sxs-lookup"><span data-stu-id="9704e-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9704e-158">Если абонентская группа SIP для обмена сообщениями с URI связана только с одним IP-шлюзом, не запретите исходящие вызовы через этот шлюз.</span><span class="sxs-lookup"><span data-stu-id="9704e-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="9704e-159">Создание автосекретаря UM для каждой абонентской группы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9704e-160">Не включайте пробелы в имя автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="9704e-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    <span data-ttu-id="9704e-161">Для получения дополнительных сведений см.:</span><span class="sxs-lookup"><span data-stu-id="9704e-161">For details, see:</span></span>
    
      - <span data-ttu-id="9704e-162">Дополнительные сведения об Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)статье "New-Умаутоаттендант: Exchange 2007".</span><span class="sxs-lookup"><span data-stu-id="9704e-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="9704e-163">Дополнительные сведения об Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)статье "New-Умаутоаттендант: Exchange 2010".</span><span class="sxs-lookup"><span data-stu-id="9704e-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="9704e-164">Необходимо выполнить описанные ниже действия для каждого пользователя, если вы включили пользователей Lync Server для корпоративного голосовой связи и знаете их URI SIP.</span><span class="sxs-lookup"><span data-stu-id="9704e-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="9704e-165">Свяжите пользователей Exchange UM (каждый из которых должен быть настроен с помощью почтового ящика Exchange) с абонентской группой UM и создайте универсальный код ресурса (URI) SIP для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9704e-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9704e-166"><STRONG>Сипресаурцеидентифиер</STRONG> в следующем примере должен быть адресом SIP пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9704e-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    <span data-ttu-id="9704e-167">Для получения дополнительных сведений см.:</span><span class="sxs-lookup"><span data-stu-id="9704e-167">For details, see:</span></span>
    
      - <span data-ttu-id="9704e-168">Дополнительные сведения об Exchange 2007 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)статье "Enable-Уммаилбокс: Exchange 2007 Help".</span><span class="sxs-lookup"><span data-stu-id="9704e-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="9704e-169">Дополнительные сведения об Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)статье "Enable-Уммаилбокс: Exchange 2010 Help".</span><span class="sxs-lookup"><span data-stu-id="9704e-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: специальные инструкции по настройке для искусственных транзакций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a749e4349f6dae6ab7cae079af443734f9cfbc15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="408d0-102">Специальные инструкции по настройке для искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="408d0-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="408d0-103">_**Последнее изменение темы:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="408d0-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="408d0-p101">Большинство искусственных транзакций может работать на узле-наблюдателе без изменений. То есть, как только искусственная транзакция добавляется в параметры конфигурации узла-наблюдателя, узел-наблюдатель может начать использовать эту искусственную транзакцию во время тестовых проходов. Однако это не относится ко всем искусственным транзакциям. Исключением являются искусственные транзакции, которые нуждаются в специальных инструкциях. Такие транзакции обсуждаются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="408d0-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="408d0-107">Работа с ошибками времени ожидания сервера</span><span class="sxs-lookup"><span data-stu-id="408d0-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="408d0-108">В некоторых случаях может возникнуть сбой искусственных транзакций с ошибками времени ожидания сервера (код ошибки 504).</span><span class="sxs-lookup"><span data-stu-id="408d0-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="408d0-109">Эти ошибки обычно возникают из-за проблем с брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="408d0-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="408d0-110">При выполнении искусственной транзакции эта транзакция выполняется в процессе Мониторингхост. exe; в свою очередь, Мониторингхост. exe запускает экземпляр процесса PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="408d0-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="408d0-111">Если брандмауэр блокирует Мониторингхост. exe или PowerShell. exe, искусственная транзакция завершится ошибкой, и будет выдаваться сообщение об ошибке 504.</span><span class="sxs-lookup"><span data-stu-id="408d0-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="408d0-112">Чтобы устранить эту проблему, необходимо вручную создать правила брандмауэра для входящих подключений для Мониторингхост. exe и PowerShell. exe на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="408d0-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="408d0-113">Это можно сделать с помощью брандмауэра Windows или стороннего локального брандмауэра в зависимости от имеющейся конфигурации сервера.</span><span class="sxs-lookup"><span data-stu-id="408d0-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="408d0-114">Если вы используете устройство сетевого брандмауэра между виртуальным компьютером искусственной транзакции и серверами Lync, которые вы пытаетесь отслеживать, вы должны считать его клиентским компьютером, а все требования к портам [и протоколам брандмауэра для внутренних серверов в Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="408d0-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="408d0-115">Искусственные транзакции в конференц-связи с передачей данных</span><span class="sxs-lookup"><span data-stu-id="408d0-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="408d0-116">Если компьютер узла-наблюдателя находится вне сети периметра, то, возможно, не удастся запустить искусственную транзакцию конференц-связи с данными, пока не будет сначала отключен параметр прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="408d0-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="408d0-117">Чтобы отключить параметры прокси-сервера для этой службы, выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="408d0-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="408d0-118">На компьютере узла-наблюдателя в меню **Пуск** щелкните **Все программы**, выберите **Стандартные**, щелкните правой кнопкой мыши **Командная строка**, а затем выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="408d0-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="408d0-119">В окне консоли введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="408d0-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="408d0-120">В окне командной строки отобразится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="408d0-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="408d0-121">Это сообщение означает, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="408d0-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="408d0-122">Искусственные транзакции единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="408d0-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="408d0-123">Искусственная транзакция единой системы обмена сообщениями Exchange удостоверяется в том, что тестовые пользователи могут подключаться к учетным записям голосовой почты, размещенным в Exchange.</span><span class="sxs-lookup"><span data-stu-id="408d0-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="408d0-124">Для этих тестовых пользователей должны быть предварительно настроены учетные записи голосовой почты, прежде чем можно будет применять тесты единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="408d0-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="408d0-125">Искусственные транзакции сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="408d0-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="408d0-126">Чтобы использовать искусственную транзакцию сохраняемого чата, администраторы должны сначала создать канал и предоставить тестовым пользователям разрешения на его использование.</span><span class="sxs-lookup"><span data-stu-id="408d0-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="408d0-127">Для правильной настройки этих тестовых пользователей можно использовать командлет [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) :</span><span class="sxs-lookup"><span data-stu-id="408d0-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="408d0-128">Эта задача настройки должна быть запущена изнутри предприятия:</span><span class="sxs-lookup"><span data-stu-id="408d0-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="408d0-129">Если запустить ее с компьютера, не являющегося сервером, пользователь, запустивший командлет должен являться членом роли PersistentChatAdministrators в соответствии с управлением доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="408d0-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="408d0-130">Если запустить непосредственно с самого сервера, пользователь, запустивший командлет, должен являться членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="408d0-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="408d0-131">В предыдущей команде параметр Setup был включен и задан как True ($True).</span><span class="sxs-lookup"><span data-stu-id="408d0-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="408d0-132">Если вы включаете параметр Setup, Test-CsPersistentChatMessage создаст специальную комнату сохраняемого чата и заполнит эту комнату тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="408d0-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="408d0-133">Это обеспечит доступность комнаты чата для тестирования.</span><span class="sxs-lookup"><span data-stu-id="408d0-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="408d0-134">Обратите внимание, что параметр Setup должен выполняться только с сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="408d0-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="408d0-135">Комната чата, созданная командлетом Test-CsPersistentChatMessage, может быть удалена администратором.</span><span class="sxs-lookup"><span data-stu-id="408d0-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="408d0-136">Искусственные транзакции одноранговых вызовов ТСОП</span><span class="sxs-lookup"><span data-stu-id="408d0-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="408d0-137">Искусственная транзакция [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) проверяет возможность помещать и принимать вызовы через телефонную сеть общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="408d0-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="408d0-138">Чтобы запустить искусственную транзакцию, администраторы должны настроить следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="408d0-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="408d0-139">Два тестовых пользователя (вызывающий абонент и получатель), включенные для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="408d0-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="408d0-140">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="408d0-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="408d0-141">Политики голосовой связи и маршруты голосовой связи, которые позволяют получать вызовам уходить на шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="408d0-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="408d0-142">Шлюз ТСОП, который принимает вызовы и среда обратных вызовов в домашний пул получателя в зависимости от набранного номера.</span><span class="sxs-lookup"><span data-stu-id="408d0-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="408d0-143">Искусственные транзакции единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="408d0-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="408d0-144">Искусственная транзакция в едином хранилище контактов проверяет, что Lync Server 2013 может получить контакты от имени пользователя из Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="408d0-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="408d0-145">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="408d0-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="408d0-146">[Управление проверкой подлинности между серверами (OAuth) и партнерским приложениями в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) необходимо настроить между Lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="408d0-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="408d0-147">Тестовые пользователи должны иметь действительный почтовый ящик Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="408d0-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="408d0-148">После выполнения этих требований администраторы могут запустить следующую команду для проверки возможности получения пользователем с SIP-адресом kenmyer@litwareinc.com своих контактов из единого хранилища контактов:</span><span class="sxs-lookup"><span data-stu-id="408d0-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="408d0-149">Обратите внимание на использование параметра Setup в предыдущей команде.</span><span class="sxs-lookup"><span data-stu-id="408d0-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="408d0-150">Если параметр Setup включен при выполнении Test-CsUnifiedContactStore, то контакты указанного пользователя (в нашем случае sip:kenmyer@litwareinc.com) будут перемещены в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="408d0-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="408d0-151">(Конечно, если контакты пользователя уже находятся в едином хранилище контактов, их не нужно перемещать). Параметр Setup обычно используется только один раз (при первом запуске test-CsUnifiedContactStore), и его следует использовать только с тестовыми пользователями; то есть учетные записи пользователей, которые никогда не будут входить в систему на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="408d0-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="408d0-152">После миграции тестового пользователя в единое хранилище контактов можно проверить возможность получения контактов пользователя, вызвав командлет Test-CsUnifiedContactStore без параметра Setup:</span><span class="sxs-lookup"><span data-stu-id="408d0-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="408d0-153">Искусственные транзакции XMPP</span><span class="sxs-lookup"><span data-stu-id="408d0-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="408d0-154">Искусственная транзакция мгновенных сообщений XMPP нуждается в настройке компонента XMPP с указанием одного или нескольких федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="408d0-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="408d0-155">Чтобы включить искусственную транзакцию XMPP, необходимо предоставить параметр XmppTestReceiverMailAddress, используя учетную запись пользователя в домене XMPP с поддержкой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="408d0-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="408d0-156">Пример:</span><span class="sxs-lookup"><span data-stu-id="408d0-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="408d0-157">В этом примере для маршрутизации сообщений litwareinc.com на шлюз XMPP необходимо наличие правила Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="408d0-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


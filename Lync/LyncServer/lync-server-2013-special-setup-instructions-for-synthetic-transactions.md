---
title: 'Lync Server 2013: специальные инструкции по настройке для виртуальных операций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="2b1e3-102">Специальные инструкции по настройке для виртуальных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1e3-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b1e3-103">_**Тема последнего изменения:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="2b1e3-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="2b1e3-104">Большинство искусственных транзакций могут выполняться на узле наблюдателя как есть; Это значит, что при добавлении виртуальной транзакции в параметры конфигурации узла-наблюдателя узел-наблюдатель может приступить к использованию искусственной транзакции во время тестовых этапов.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-104">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes.</span></span> <span data-ttu-id="2b1e3-105">Однако это не справедливо для всех виртуальных транзакций.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-105">However, this is not true for all synthetic transactions.</span></span> <span data-ttu-id="2b1e3-106">Исключения — искусственные транзакции, требующие специальных инструкций по настройке — рассматриваются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-106">The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="2b1e3-107">Работа с ошибками времени ожидания сервера</span><span class="sxs-lookup"><span data-stu-id="2b1e3-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="2b1e3-108">В некоторых случаях вы можете столкнуться со сбоем виртуальных транзакций с ошибками таймаута сервера (код ошибки 504).</span><span class="sxs-lookup"><span data-stu-id="2b1e3-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="2b1e3-109">Эти ошибки обычно возникают из-за проблем с брандмауэром.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="2b1e3-110">При выполнении искусственной транзакции эта транзакция выполняется в процессе Мониторингхост. exe; в свою очередь, Мониторингхост. exe запускает экземпляр процесса PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="2b1e3-111">Если ваш брандмауэр блокирует приложение Мониторингхост. exe или PowerShell. exe, то при возникновении ошибки в виртуальной транзакции будет выдаваться ошибка 504.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="2b1e3-112">Чтобы устранить эту проблему, необходимо вручную создать правила брандмауэра для Мониторингхост. exe и PowerShell. exe на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="2b1e3-113">Это можно сделать с помощью брандмауэра Windows или стороннего местного межсетевого экрана в зависимости от конфигурации, установленной на сервере.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="2b1e3-114">Если вы используете сетевое подключение устройства между узлом виртуальной транзакции и серверами Lync, на которых вы пытаетесь наблюдать, вы должны считать его клиентским компьютером, а все требования к порту и протоколам для всех брандмауэров [ для внутренних серверов в Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="2b1e3-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="2b1e3-115">Синтетические транзакции для конференций с данными</span><span class="sxs-lookup"><span data-stu-id="2b1e3-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="2b1e3-116">Если компьютер-наблюдатель находится за пределами сети периметра, возможно, вы не сможете выполнить виртуальную транзакцию для конференц-связи с данными, если только вы не отключите параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="2b1e3-117">Чтобы отключить параметры прокси-сервера для этой службы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="2b1e3-118">На компьютере с узлом-наблюдателем нажмите **кнопку Пуск**, **выберите все программы**, затем **стандартные**, щелкните правой кнопкой мыши **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="2b1e3-119">В окне консоли введите указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="2b1e3-120">В окне командной строки появится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="2b1e3-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="2b1e3-121">Это сообщение означает, что вы отключили параметры прокси-сервера Internet Explorer для учетной записи сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="2b1e3-122">Синтетические транзакции в единой системе обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="2b1e3-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="2b1e3-123">Искусственная транзакция обмена сообщениями Exchange (UM) проверяет, что тестовые пользователи могут подключаться к учетным записям голосовой почты, которые размещаются в Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="2b1e3-124">Эти тестовые пользователи должны быть предварительно настроены с учетными записями голосовой почты, прежде чем они смогут использовать проверки UM Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="2b1e3-125">Синтетическые транзакции для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="2b1e3-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="2b1e3-126">Для использования искусственной транзакции "сохраняемый чат" администраторам необходимо сначала создать канал, а также дать тестовым пользователям разрешения на его использование.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="2b1e3-127">Командлет [Test-ксперсистентчатмессаже](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) можно использовать для правильной настройки этих тестовых пользователей.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="2b1e3-128">Эта задача по установке должна выполняться в рамках предприятия.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="2b1e3-129">При запуске с несерверного компьютера пользователь, который запускает командлет, должен быть членом роли Персистентчатадминистраторс для управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="2b1e3-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="2b1e3-130">При запуске с сервера сам пользователь, который запускает командлет, должен быть членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="2b1e3-131">В приведенной выше команде параметр настройки включен и имеет значение true ($True).</span><span class="sxs-lookup"><span data-stu-id="2b1e3-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="2b1e3-132">Если вы включаете параметр настройки, проверка-Ксперсистентчатмессаже создаст специальную комнату с сохраняемым разговором и заполнит эту комнату тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="2b1e3-133">Это поможет удостовериться в том, что в настоящее время есть комната чата в целях тестирования.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="2b1e3-134">Обратите внимание, что параметр Setup должен выполняться только с сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="2b1e3-135">Комната чата, созданная с помощью Test-Ксперсистентчатмессаже, может быть удалена только администратором.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="2b1e3-136">Синтетические транзакции одноранговых вызовов PSTN</span><span class="sxs-lookup"><span data-stu-id="2b1e3-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="2b1e3-137">Синтетические транзакции [Test-кспстнпиртопиркалл](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) проверяют возможность размещения и приема звонков через коммутируемую телефонную сеть общего пользования (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="2b1e3-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="2b1e3-138">Для выполнения этой искусственной транзакции администраторы должны настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2b1e3-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="2b1e3-139">Два тестовых пользователя (вызывающего абонента и приемника), разрешенные для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="2b1e3-140">Прямые входные номера для каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="2b1e3-141">Голосовые и видеомаршрутные политики, позволяющие звонить по номеру приемника для доступа к шлюзу PSTN.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="2b1e3-142">Шлюз PSTN, принимающий звонки, и носители, которые перенаправляют вызовы обратно на пул домашнего пула получателя в соответствии с набранным номером.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="2b1e3-143">Синтетические транзакции в магазине контактов</span><span class="sxs-lookup"><span data-stu-id="2b1e3-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="2b1e3-144">Виртуальная транзакция в магазине единой системы обмена сообщениями удостоверяется в том, что Lync Server 2013 может получать контакты от имени пользователя из Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="2b1e3-145">Чтобы использовать эту искусственную транзакцию, следует выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="2b1e3-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="2b1e3-146">Управление проверкой подлинности между сервером [(OAuth) и приложениями-партнерами в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) должно быть настроено между lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="2b1e3-147">Тестовые пользователи должны иметь действительный почтовый ящик Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="2b1e3-148">После того как эти условия будут выполнены, администраторы могут выполнить следующую команду, чтобы убедиться в том, что пользователь с SIP Address kenmyer@litwareinc.com может получать свои контакты из хранилища единого контакта:</span><span class="sxs-lookup"><span data-stu-id="2b1e3-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="2b1e3-149">Обратите внимание на использование параметра настройки, используемого в предыдущей команде.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="2b1e3-150">Если параметр настройки включается при запуске test-Ксунифиедконтактсторе, указанные контакты пользователя (в данном случае — sip:kenmyer@litwareinc.com) будут перемещены в единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="2b1e3-151">(Разумеется, если контакты пользователя уже находятся в едином хранилище контактов, они не нужно перемещать.) Параметр "Настройка" обычно используется только один раз (при первом выполнении теста-Ксунифиедконтактсторе), и его следует использовать только для тестовых пользователей; то есть учетные записи пользователей, которые никогда не будут входить на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="2b1e3-152">После того как тестовый пользователь будет перенесен в единое хранилище контактов, вы можете убедиться, что контакты пользователя можно получить, вызвав тест-Ксунифиедконтактсторе без параметра Setup:</span><span class="sxs-lookup"><span data-stu-id="2b1e3-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="2b1e3-153">КСМПП Синтетическые транзакции</span><span class="sxs-lookup"><span data-stu-id="2b1e3-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="2b1e3-154">Для искусственной транзакции обмена мгновенными сообщениями в КСМПП (Extensible Mailing Protocol и присутствие) необходимо, чтобы функция КСМПП была настроена с использованием одного или нескольких федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="2b1e3-155">Чтобы включить виртуальную транзакцию КСМПП, необходимо указать параметр Ксмпптестрецеивермаиладдресс с учетной записью пользователя в маршрутизируемой КСМПП домене.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="2b1e3-156">Например:</span><span class="sxs-lookup"><span data-stu-id="2b1e3-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="2b1e3-157">В этом примере для маршрутизации сообщений для litwareinc.com на шлюз КСМПП необходимо наличие правила Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b1e3-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


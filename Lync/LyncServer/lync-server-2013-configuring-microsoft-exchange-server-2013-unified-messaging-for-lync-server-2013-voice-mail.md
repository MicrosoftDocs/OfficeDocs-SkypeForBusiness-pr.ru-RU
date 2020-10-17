---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Lync Server 2013 Голосовая почта'
description: 'Lync Server 2013: Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Lync Server 2013 Голосовая почта.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57576981e419f96734e4bd2ed62a7d203f7b683c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570755"
---
# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="e05e4-103">Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для голосовой почты Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e05e4-103">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e05e4-104">_**Последнее изменение темы:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="e05e4-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="e05e4-105">Microsoft Lync Server 2013 позволяет использовать сообщения голосовой почты, хранящиеся в Microsoft Exchange Server 2013; Эти сообщения голосовой почты будут отображаться как сообщения электронной почты в папках "Входящие" пользователей.</span><span class="sxs-lookup"><span data-stu-id="e05e4-105">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="e05e4-106">Эта возможность также была обнаружена в выпусках Lync Server и Exchange для 2010. Тем не менее, процесс настройки единой системы обмена сообщениями упрощен в выпусках 2013, благодаря появлением компонента маршрутизатора вызовов единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e05e4-106">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="e05e4-107">Этот компонент устанавливается на сервере клиентского доступа Exchange 2013, а все вызовы единой системы обмена сообщениями Exchange (например, голосовой почты) сначала проходят через маршрутизатор вызовов, а затем перенаправляются на соответствующий сервер почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e05e4-107">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="e05e4-108">Если вы уже настроили межсерверную проверку подлинности между Lync Server 2013 и Exchange 2013, то готовы настроить единую систему обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e05e4-108">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="e05e4-109">Для этого необходимо сначала создать и назначить новую абонентскую схему единой системы обмена сообщениями на сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="e05e4-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="e05e4-110">Например, следующие две команды (выполняются в командной консоли Exchange) настраивают новую абонентскую абонентскую группы для Exchange:</span><span class="sxs-lookup"><span data-stu-id="e05e4-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="e05e4-111">В первой команде в примере параметр VoIPSecurity и значение параметра "Secured" указывают на то, что сигнальный канал шифруется с помощью протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="e05e4-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="e05e4-112">Уритипе "SipName" указывает, что сообщения будут отправлены и получены с помощью протокола SIP, а Каунтрйоррегионкоде 1 указывает на то, что абонентская абонентская абонентская область применяется к нам.</span><span class="sxs-lookup"><span data-stu-id="e05e4-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="e05e4-113">Во второй команде значение параметра, передаваемое параметру Конфигурединкаунтрйоррегионграупс, определяет группы внутри страны, которые можно использовать с этой абонентской группой.</span><span class="sxs-lookup"><span data-stu-id="e05e4-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="e05e4-114">Значение параметра "Anywhere,, \* \* \* " задает следующее:</span><span class="sxs-lookup"><span data-stu-id="e05e4-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="e05e4-115">Имя группы ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="e05e4-115">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="e05e4-116">Параметр allowednumberstring ( \* — подстановочный знак, указывающий на то, что любая числовая строка разрешена)</span><span class="sxs-lookup"><span data-stu-id="e05e4-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="e05e4-117">Параметр dialnumberstring ( \* — подстановочный знак, указывающий на то, что любой набранный номер разрешен)</span><span class="sxs-lookup"><span data-stu-id="e05e4-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="e05e4-118">Параметр textcomment ( \* — подстановочный знак, указывающий на то, что любая Текстовая команда разрешена)</span><span class="sxs-lookup"><span data-stu-id="e05e4-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e05e4-119">При создании новой абонентской группы также будет создана политика почтовых ящиков по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e05e4-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="e05e4-120">После создания и настройки новой абонентской группы необходимо добавить новую абонентскую схему на сервер единой системы обмена сообщениями, а затем изменить режим запуска этого сервера. в частности, необходимо присвоить режиму запуска значение "Dual".</span><span class="sxs-lookup"><span data-stu-id="e05e4-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="e05e4-121">Обе эти задачи можно выполнить в командной консоли Exchange:</span><span class="sxs-lookup"><span data-stu-id="e05e4-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="e05e4-122">После настройки сервера единой системы обмена сообщениями следует выполнить командлет Enable-ExchangeCertificate, чтобы убедиться, что сертификат Exchange применяется к службе единой системы обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="e05e4-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="e05e4-123">После правильного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e05e4-123">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server.</span></span> <span data-ttu-id="e05e4-124">Эту службу необходимо остановить и перезапустить при каждом изменении режима запуска.</span><span class="sxs-lookup"><span data-stu-id="e05e4-124">This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="e05e4-125">После завершения настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e05e4-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="e05e4-126">Так как режим запуска изменился, необходимо остановить и перезапустить службу MsExchangeUMCR на компьютере, на котором размещается маршрутизатор вызовов единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e05e4-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="e05e4-127">Чтобы завершить настройку единой системы обмена сообщениями, необходимо создать политику почтовых ящиков единой системы обмена сообщениями и затем использовать эту политику, чтобы разрешить пользователям единую систему обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e05e4-127">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging.</span></span> <span data-ttu-id="e05e4-128">Вы можете создать политику почтовых ящиков с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e05e4-128">You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="e05e4-129">Вы также можете включить для пользователя единую систему обмена сообщениями с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e05e4-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="e05e4-130">В предыдущей команде параметр Extensions представляет добавочный номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="e05e4-130">In the preceding command, the Extensions parameter represents the telephone extension number for the user.</span></span> <span data-ttu-id="e05e4-131">В этом примере у пользователя есть добавочный номер 100.</span><span class="sxs-lookup"><span data-stu-id="e05e4-131">In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="e05e4-132">После включения почтового ящика пользователь kenmyer@litwareinc.com должен иметь возможность использовать единую систему обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="e05e4-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="e05e4-133">Чтобы убедиться, что пользователь может подключаться к единой системе обмена сообщениями Exchange, выполните командлет [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e05e4-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e05e4-134">Если у вас есть второй пользователь, для которого включена поддержка единой системы обмена сообщениями, можно воспользоваться командлетом [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) , чтобы проверить, может ли второй пользователь оставить сообщение голосовой почты для первого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e05e4-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>


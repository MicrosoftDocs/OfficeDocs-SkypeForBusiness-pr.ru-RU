---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Lync Server 2013 Голосовая почта'
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
ms.openlocfilehash: 367f4cc517771f51d7a1452293ad9803075d285f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="a44b5-102">Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Microsoft Lync Server 2013 для голосовой почты</span><span class="sxs-lookup"><span data-stu-id="a44b5-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a44b5-103">_**Тема последнего изменения:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="a44b5-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="a44b5-104">Microsoft Lync Server 2013 позволяет использовать голосовые сообщения, хранящиеся в Microsoft Exchange Server 2013; Эти голосовые сообщения будут отображаться как сообщения электронной почты в ящиках пользователей.</span><span class="sxs-lookup"><span data-stu-id="a44b5-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="a44b5-105">Эта возможность также была обнаружена в выпусках 2010 для Lync Server и Exchange; Однако процесс настройки этого параметра "Единая система обмена сообщениями" упрощен в выпусках 2013, благодаря введению компонента маршрутизатора UM.</span><span class="sxs-lookup"><span data-stu-id="a44b5-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="a44b5-106">Этот компонент установлен на сервере клиентского доступа Exchange 2013, а все вызовы к единой системе обмена сообщениями Exchange (например, голосовой почте) сначала пересылаются через маршрутизатор вызовов, а затем перенаправляются на соответствующий сервер почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="a44b5-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="a44b5-107">Если вы уже настроили проверку подлинности "сервер-сервер" между Lync Server 2013 и Exchange 2013, вы можете настроить единую систему обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a44b5-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="a44b5-108">Для этого необходимо сначала создать и назначить новую абонентскую группу единой системы обмена сообщениями на сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="a44b5-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="a44b5-109">Например, эти две команды (выполняются из командной консоли Exchange) настраивают новый 3-значный абонентский тариф для Exchange:</span><span class="sxs-lookup"><span data-stu-id="a44b5-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="a44b5-p103">В первой команде в этом примере параметр VoIPSecurity и его значение "Secured" указывают, что сигнальный канал зашифрован с помощью протокола TLS. Значение "SipName" параметра URIType указывает, что сообщения будут отправляться и получаться посредством протокола SIP, а если для параметра CountryOrRegionCode выбрано значение "1", это свидетельствует о том, что абонентская группа применима для США.</span><span class="sxs-lookup"><span data-stu-id="a44b5-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="a44b5-112">Во второй команде значение, переданное в параметр ConfiguredInCountryOrRegionGroups, определяет группы внутри страны, которые можно использовать в этой абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="a44b5-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="a44b5-113">Значение параметра "везде\*\*",\*"," задает указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="a44b5-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="a44b5-114">Имя группы ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="a44b5-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="a44b5-115">Алловеднумберстринг (\*— подстановочный знак, указывающий на то, что любая строка с цифрами разрешена)</span><span class="sxs-lookup"><span data-stu-id="a44b5-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="a44b5-116">Диалнумберстринг (\*— подстановочный знак, указывающий на то, что все номера разрешены)</span><span class="sxs-lookup"><span data-stu-id="a44b5-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="a44b5-117">Тексткоммент (\*— подстановочный знак, указывающий на то, что какая-либо из текстовых команд разрешена)</span><span class="sxs-lookup"><span data-stu-id="a44b5-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a44b5-118">При создании новой абонентской группы создается также используемая по умолчанию политика почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="a44b5-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="a44b5-119">После создания и настройки новой абонентской группы необходимо добавить ее на сервере единой системы обмена сообщениями и затем изменить режим запуска этого сервера: в частности, задать режим запуска "Двойной".</span><span class="sxs-lookup"><span data-stu-id="a44b5-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="a44b5-120">Вы можете выполнять обе эти задачи в командной консоли Exchange:</span><span class="sxs-lookup"><span data-stu-id="a44b5-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="a44b5-121">После того как вы настроили сервер единой системы обмена сообщениями, необходимо выполнить командлет Enable-ExchangeCertificate, чтобы убедиться в том, что сертификат Exchange применен к службе единой системы обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="a44b5-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="a44b5-p106">После корректного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями. Эту службу необходимо останавливать и запускать после каждого изменения режима запуска.</span><span class="sxs-lookup"><span data-stu-id="a44b5-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="a44b5-124">По завершении настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов в единую систему обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="a44b5-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="a44b5-125">Поскольку режим запуска был изменен, необходимо остановить и перезапустить службу MsExchangeUMCR на том, компьютере, где размещен маршрутизатор вызовов в единую систему обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a44b5-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="a44b5-p107">Для завершения настройки единой системы обмена сообщениями необходимо создать политику почтовых ящиков единой системы обмена мгновенными сообщениями, после чего использовать ее, чтобы разрешить пользователям работу с единой системой обмена сообщениями. Для создания политики почтовых ящиков можно использовать команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="a44b5-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="a44b5-128">Чтобы разрешить пользователям работу с единой системой обмена сообщениями, можно также использовать команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="a44b5-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="a44b5-p108">В предыдущей команде параметр Extensions представляет добавочный номер телефона для пользователя. В этом примере добавочный номер пользователя — 100.</span><span class="sxs-lookup"><span data-stu-id="a44b5-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="a44b5-131">После активации почтового ящика пользователь kenmyer@litwareinc.com может работать с единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="a44b5-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="a44b5-132">Вы можете убедиться, что пользователь может подключаться к UM-среде Exchange, запустив в командной консоли Lync Server командлет [Test – ксексумконнективити](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) .</span><span class="sxs-lookup"><span data-stu-id="a44b5-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a44b5-133">При наличии второго пользователя, которому разрешена работа с единой системой обмена сообщениями, можно с помощью командлета [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) проверить, может ли второй пользователь оставлять сообщения голосовой почты для первого пользователя.</span><span class="sxs-lookup"><span data-stu-id="a44b5-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>


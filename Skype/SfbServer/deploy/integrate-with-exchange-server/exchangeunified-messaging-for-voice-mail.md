---
title: Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Сводка: Настройка единой системы обмена сообщениями Exchange Server для Скайп Business Server голосовой почты.'
ms.openlocfilehash: 5cc8825e04e348004f4105d483eb7a92dd0e5c60
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569224"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="e9e13-103">Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="e9e13-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="e9e13-104">**Сводка:** Настройка единой системы обмена сообщениями Exchange Server для Скайп Business Server голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="e9e13-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="e9e13-105">Скайп для Business Server 2015 позволяет иметь сообщения голосовой почты, хранящиеся в Exchange Server 2016 или Exchange Server 2013; Эти сообщения голосовой почты появится в виде сообщения электронной почты в почтовые ящики пользователей.</span><span class="sxs-lookup"><span data-stu-id="e9e13-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="e9e13-106">Если вы уже настроили проверки подлинности сервер сервер между Скайп Business Server 2015, Exchange Server 2016 или Exchange Server 2013, затем вы готовы для настройки единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e9e13-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="e9e13-107">Для этого необходимо сначала создать и Назначение новой единой системы обмена сообщениями абонентской группы на сервере Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9e13-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="e9e13-108">К примеру следующие команды (выполнять в командной консоли Exchange) настроить новый абонентскую цифра 3 для Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9e13-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="e9e13-p102">В первой команде в этом примере параметр VoIPSecurity и его значение "Secured" указывают, что сигнальный канал зашифрован с помощью протокола TLS. Значение "SipName" параметра URIType указывает, что сообщения будут отправляться и получаться посредством протокола SIP, а если для параметра CountryOrRegionCode выбрано значение "1", это свидетельствует о том, что абонентская группа применима для США.</span><span class="sxs-lookup"><span data-stu-id="e9e13-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="e9e13-111">Во второй команде значение, переданное в параметр ConfiguredInCountryOrRegionGroups, определяет группы внутри страны, которые можно использовать в этой абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="e9e13-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="e9e13-112">Значение параметра «в любом месте,\*,\*,\*"Задает следующее:</span><span class="sxs-lookup"><span data-stu-id="e9e13-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="e9e13-113">Имя группы ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="e9e13-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="e9e13-114">AllowedNumberString (\*, подстановочный знак, указывающего на то, что может любая строка номера)</span><span class="sxs-lookup"><span data-stu-id="e9e13-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="e9e13-115">DialNumberString (\*, подстановочный знак, указывающего на то, что разрешен любой набранный номер)</span><span class="sxs-lookup"><span data-stu-id="e9e13-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="e9e13-116">Параметр TextComment (\*, подстановочный знак, указывающего на то, что может Любая текстовая команда)</span><span class="sxs-lookup"><span data-stu-id="e9e13-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="e9e13-117">При создании новой абонентской группы создается также используемая по умолчанию политика почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e9e13-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="e9e13-118">После создания и настройки новой абонентской группы необходимо добавить ее на сервере единой системы обмена сообщениями и затем изменить режим запуска этого сервера: в частности, задать режим запуска "Двойной".</span><span class="sxs-lookup"><span data-stu-id="e9e13-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="e9e13-119">Необходимо выполнить оба эти операции в командной консоли Exchange:</span><span class="sxs-lookup"><span data-stu-id="e9e13-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="e9e13-120">После настройки единой системы обмена сообщениями сервера необходимо выполнить командлет Enable-ExchangeCertificate, чтобы убедиться, что сертификат Exchange применяется к службе единой системы обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="e9e13-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="e9e13-p105">После корректного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями. Эту службу необходимо останавливать и запускать после каждого изменения режима запуска.</span><span class="sxs-lookup"><span data-stu-id="e9e13-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="e9e13-123">По завершении настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов в единую систему обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="e9e13-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="e9e13-124">Поскольку режим запуска был изменен, необходимо остановить и перезапустить службу MsExchangeUMCR на том, компьютере, где размещен маршрутизатор вызовов в единую систему обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e9e13-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="e9e13-p106">Для завершения настройки единой системы обмена сообщениями необходимо создать политику почтовых ящиков единой системы обмена мгновенными сообщениями, после чего использовать ее, чтобы разрешить пользователям работу с единой системой обмена сообщениями. Для создания политики почтовых ящиков можно использовать команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="e9e13-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="e9e13-127">Чтобы разрешить пользователям работу с единой системой обмена сообщениями, можно также использовать команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="e9e13-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="e9e13-p107">В предыдущей команде параметр Extensions представляет добавочный номер телефона для пользователя. В этом примере добавочный номер пользователя — 100.</span><span class="sxs-lookup"><span data-stu-id="e9e13-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="e9e13-130">После активации почтового ящика пользователь kenmyer@litwareinc.com может работать с единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="e9e13-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="e9e13-131">Чтобы удостовериться, что пользователи могут подключаться к Exchange единой системы обмена СООБЩЕНИЯМИ с помощью командлета [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) из внутри Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="e9e13-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="e9e13-132">При наличии второй пользователь, который был включен для единой системы обмена сообщениями можно использовать командлет [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) , чтобы убедиться, что этот второго пользователя можно оставить сообщение голосовой почты для первого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9e13-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```
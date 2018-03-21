---
title: "Управление единой системы обмена сообщениями Exchange и размещенной голосовой почты"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: cc4904768cbb7f6bbcbbd9921efebfe7d4765c55
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="3e7cb-103">Управление единой системы обмена сообщениями Exchange и размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="3e7cb-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="3e7cb-104">[] Вы можете управлять единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса online с помощью набора командлетов.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="3e7cb-105">Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой</span><span class="sxs-lookup"><span data-stu-id="3e7cb-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="3e7cb-106">Следующие командлеты можно использовать для управления единой системой обмена сообщениями Exchange и политиками размещенной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="3e7cb-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="3e7cb-107">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="3e7cb-107">**Cmdlet**</span></span>|<span data-ttu-id="3e7cb-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3e7cb-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3e7cb-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="3e7cb-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="3e7cb-110">Новый CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="3e7cb-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="3e7cb-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="3e7cb-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="3e7cb-112">SET-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="3e7cb-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="3e7cb-113">Создает объекты контактов, используемые для автосекретаря и служб абонентского доступа, и управляет ими, если единая система обмена сообщениями Exchange является размещенной службой.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="3e7cb-p101">Skype для бизнеса online вместе с единой системой обмена сообщениями Exchange предоставляет несколько возможностей, связанных с голосом, включая автосекретарь и абонентский доступ. Автосекретарь позволяет автоматически отвечать на звонки и перенаправлять их нужному человеку. С помощью абонентского доступа пользователи подключаются к единой системе обмена сообщениями Exchange и извлекают письма, голосовые сообщения, контакты и сведения о календаре.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-p101">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access. Auto Attendant provides a way for calls to automatically be answered and routed to the correct person. Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.  </span></span><br/><br/> <span data-ttu-id="3e7cb-p102">Если единая система обмена сообщениями Exchange предоставляется как размещенная служба, объекты контактов, используемые для автосекретаря и служб абонентского доступа, нужно создать с помощью Microsoft PowerShell. Эти объекты создаются и управляются с помощью командлетов **CsExUmContact**.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-p102">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell. These objects are created and managed by using the **CsExUmContact** cmdlets. </span></span><br/> |
|[<span data-ttu-id="3e7cb-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3e7cb-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="3e7cb-120">GRANT-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3e7cb-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="3e7cb-p103">Управляет политиками размещенной голосовой почты, используемыми в организации. Политики размещенной голосовой почты определяют, как неотвеченные звонки перенаправляются в службу единой системы обмена сообщениями Exchange. Эти политики затрагивают только пользователей, у которых разрешена размещенная голосовая почта единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-p103">Manages hosted voicemail policies used in the organization. Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service. These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="3e7cb-124">Чтобы проверить, разрешена ли размещенная голосовая почта для пользователя, запустите команду, аналогичную следующей, из приглашения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="3e7cb-125">"Get-CsOnlineUser-Identity «kenmyer@litwareinc.com»</span><span class="sxs-lookup"><span data-stu-id="3e7cb-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="3e7cb-126">SELECT-Object HostedVoiceMail "</span><span class="sxs-lookup"><span data-stu-id="3e7cb-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="3e7cb-127">See also</span><span class="sxs-lookup"><span data-stu-id="3e7cb-127">Related topics</span></span>
[<span data-ttu-id="3e7cb-128">Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e7cb-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a><span data-ttu-id="3e7cb-129">Отзыв?</span><span class="sxs-lookup"><span data-stu-id="3e7cb-129">Feedback?</span></span>
<span data-ttu-id="3e7cb-130">Для предоставления продукта свои отзывы и предложения или сообщите нам знать, как в нашем [Скайп для бизнеса свои отзывы и предложения](https://www.skypefeedback.com)см.</span><span class="sxs-lookup"><span data-stu-id="3e7cb-130">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
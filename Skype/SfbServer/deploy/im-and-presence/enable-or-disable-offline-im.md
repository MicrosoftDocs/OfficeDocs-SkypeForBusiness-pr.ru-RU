---
title: Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801949"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="7bf4d-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7bf4d-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="7bf4d-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="7bf4d-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7bf4d-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="7bf4d-106">Автономный обмен мгновенными сообщениями — это клиентская функция, встроенная в клиент Skype для бизнеса (сборка 2016 C2R 16.0.6701.1000 или выше), которая использует веб-службы Exchange (EWS) для отправки сообщений из клиента Skype для бизнеса в почтовый ящик Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="7bf4d-107">Автономный обмен мгновенными сообщениями использует веб-службы Exchange (EWS) для отправки автономных сообщений из клиента Skype для бизнеса в почтовый ящик получателя.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="7bf4d-108">EWS должен быть доступен клиенту Skype для бизнеса, чтобы отправлять автономные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="7bf4d-109">Дополнительные информацию о планировании обмена мгновенными сообщениями и присутствия см. в этой теме, в этой теме вы узнаете, как планировать обмен мгновенными сообщениями и присутствие [в Skype для бизнеса Server.](../../plan-your-deployment/instant-messaging-and-presence.md)</span><span class="sxs-lookup"><span data-stu-id="7bf4d-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7bf4d-110">Если почтовый ящик пользователя находится в локальной сети Exchange, требуется клиент Skype для бизнеса (сборка 2016 C2R 16.0.6920.1000)</span><span class="sxs-lookup"><span data-stu-id="7bf4d-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="7bf4d-111">To enable or disable Offline IM in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7bf4d-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="7bf4d-112">Откройте оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="7bf4d-113">Чтобы включить автономный мгновенный доступ, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7bf4d-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="7bf4d-114">В Skype для бизнеса Server 2015 CU3 для параметра EnableOfflineIM $True по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="7bf4d-115">Чтобы отключить, установите для этого значения значение $False.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="7bf4d-116">Чтобы подтвердить, что установлена возможность хранения автономных мгновенных мгновенных данных, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="7bf4d-117">Интеграция автономного обмена мгновенными мгновенными данными с Exchange</span><span class="sxs-lookup"><span data-stu-id="7bf4d-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="7bf4d-118">Автономный обмен мгновенными сообщениями не будет доступен отправителям, если у них есть политика клиента, которая отключает автоматическое сохранение автономных сообщений в папку истории бесед (EnableIMAutoArchiving = $false).</span><span class="sxs-lookup"><span data-stu-id="7bf4d-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="7bf4d-119">Механизм проверки возможности получения сообщений в автономном режиме не существует.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="7bf4d-120">Для автономных сообщений, отправленных в пределах той же организации, они будут получены в качестве сообщения электронной  почты с классом сообщений IM.Note.MissedConversation и будут включены в папку "Пропущенная беседа" Outlook, а также историю бесед, которую можно получить на вкладке "Последние списки" или "История бесед" в клиентах Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="7bf4d-121">Для автономных сообщений, отправленных из федерационной организации, они будут получены как сообщения электронной почты без im.Note.MisssedConversation и не будут отображены в папках пропущенных бесед или истории бесед.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="7bf4d-122">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="7bf4d-122">Troubleshooting</span></span>

<span data-ttu-id="7bf4d-123">Существует двухминутный период времени, с того времени, когда автономное сообщение отправляется, когда оно было обработано и обработано.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="7bf4d-124">Если автономные сообщения не могут быть обработаны, они будут отображаться в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="7bf4d-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="7bf4d-125">Основной журнал ETL Skype для бизнеса будет содержать сведения об обработке автономных сообщений и является лучшим источником для исследования и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7bf4d-126">Сообщалось о проблеме, из-за которой автономные сообщения не удалось отправить, а папка "Черновики" заполнялась сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="7bf4d-127">Это произошло с почтовыми ящиками локального exchange.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="7bf4d-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span><span class="sxs-lookup"><span data-stu-id="7bf4d-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  

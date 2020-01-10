---
title: Включение и отключение автономной работы с мгновенными сообщениями в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Сведения о включении и отключении автономной работы с мгновенными сообщениями в Skype для бизнеса Server.
ms.openlocfilehash: 02056618aff8a2dcaa6edc2023b67ad38aa9f314
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003049"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="5fab5-103">Включение и отключение автономной работы с мгновенными сообщениями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fab5-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="5fab5-104">Сведения о включении и отключении автономной работы с мгновенными сообщениями в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5fab5-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="5fab5-105">Включение автономной работы с мгновенными сообщениями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fab5-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="5fab5-106">Автономный обмен мгновенными сообщениями — это клиентская функция, встроенная в клиент Skype для бизнеса (2016 C2R Build 16.0.6701.1000 или более позднюю версию), которая использует веб-службы Exchange (EWS) для отправки сообщений из клиента Skype для бизнеса в почтовый ящик Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="5fab5-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="5fab5-107">Автономное сообщение использует веб-службы Exchange (EWS) для отправки автономных сообщений от клиента Skype для бизнеса в почтовый ящик получателя.</span><span class="sxs-lookup"><span data-stu-id="5fab5-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="5fab5-108">Для отправки сообщений в автономном режиме в клиенте Skype для бизнеса необходимо иметь доступ к этой версии.</span><span class="sxs-lookup"><span data-stu-id="5fab5-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="5fab5-109">Дополнительные сведения о планировании обмена мгновенными сообщениями и их присутствием можно найти [в статье Планирование обмена мгновенными сообщениями и их присутствия в Skype для бизнеса Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="5fab5-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fab5-110">Если почтовый ящик пользователя размещен в локальной среде Exchange, требуется клиент Skype для бизнеса (2016 C2R Build 16.0.6920.1000)</span><span class="sxs-lookup"><span data-stu-id="5fab5-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="5fab5-111">Включение и отключение автономного обмена мгновенными сообщениями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fab5-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="5fab5-112">Откройте консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5fab5-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5fab5-113">Выполните следующую команду, чтобы включить службу отправки автономных мгновенных сообщений:</span><span class="sxs-lookup"><span data-stu-id="5fab5-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="5fab5-114">В Skype для бизнеса Server 2015 CU3 по умолчанию параметр Енаблеоффлинеим имеет значение "$True".</span><span class="sxs-lookup"><span data-stu-id="5fab5-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="5fab5-115">Чтобы отключить службу, задайте значение $False.</span><span class="sxs-lookup"><span data-stu-id="5fab5-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="5fab5-116">Выполните следующую команду, чтобы убедиться, что параметр сохранить автономный обмен мгновенными сообщениями установлен.</span><span class="sxs-lookup"><span data-stu-id="5fab5-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="5fab5-117">Интеграция службы отправки автономных мгновенных сообщений с Exchange</span><span class="sxs-lookup"><span data-stu-id="5fab5-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="5fab5-p103">Отправка автономных мгновенных сообщений будет недоступна для отправителей, если их политика клиента запрещает автоматическое сохранение автономных мгновенных сообщений в папке журнала бесед (EnableIMAutoArchiving = $false). Механизм, позволяющий убедиться, что получатель может принимать автономные мгновенные сообщения, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5fab5-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="5fab5-120">Для автономных сообщений, отправляемых в рамках той же организации, они будут получены в виде сообщения электронной почты с классом сообщений для обмена мгновенными сообщениями. Note. Мисседконверсатион и будет включена в папку " **пропущенные беседы** Outlook", а также историю бесед, которая будет выбрана на вкладке "последние" и "Журнал бесед" в клиентах Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5fab5-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="5fab5-121">Автономные сообщения, отправляемые из федеративной организации, будут получены как сообщения электронной почты без пометки IM.Note.MisssedConversation: они не будут сохраняться в папках пропущенной беседы и журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="5fab5-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="5fab5-122">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="5fab5-122">Troubleshooting</span></span>

<span data-ttu-id="5fab5-123">Если при отправке сообщения в автономном режиме, когда оно будет отправлено и обработано, существует два минутных таймера.</span><span class="sxs-lookup"><span data-stu-id="5fab5-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="5fab5-124">Если не удается обработать автономные сообщения, они будут отображаться в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="5fab5-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="5fab5-125">Основной журнал ETL для Skype для бизнеса содержит сведения об автономной обработке сообщений и является лучшим источником для исследования и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="5fab5-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5fab5-p105">Было сообщено о следующей проблеме: сбой отправки автономных сообщений и заполнение сообщениями папки "Черновики". Эта проблема наблюдалась для почтовых ящиков локальной организации Exchange. На 14 июня 2016 г данная проблема была устранена для всех каналов C2R. </span><span class="sxs-lookup"><span data-stu-id="5fab5-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  

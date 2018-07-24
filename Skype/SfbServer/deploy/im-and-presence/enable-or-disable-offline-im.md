---
title: Включение или отключение автономного мгновенного обмена Мгновенными сообщениями в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Узнайте включить или отключить автономный режим мгновенного обмена Мгновенными сообщениями в Скайп для Business Server.
ms.openlocfilehash: f033a3953e2be215f4acb587414cad4faf35855f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019561"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="ff3d0-103">Включение или отключение автономного мгновенного обмена Мгновенными сообщениями в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ff3d0-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="ff3d0-104">Узнайте включить или отключить автономный режим мгновенного обмена Мгновенными сообщениями в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="ff3d0-105">Включение автономных мгновенного обмена Мгновенными сообщениями в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ff3d0-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="ff3d0-106">Автономные мгновенные сообщения является компонентом со стороны клиента, встроенной в Скайп для клиента Business (2016 C2R построения 16.0.6701.1000 или более поздней версии), который использует Exchange Web Services (EWS) для отправки сообщений из Скайп для клиента Business почтовый ящик Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="ff3d0-107">Не в сети обмена мгновенными Сообщениями используется веб-служб Exchange (EWS) на отправку автономные сообщения из Скайп для клиента Business в почтовый ящик получателя.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="ff3d0-108">Должен быть доступен для Скайп для клиента Business для автономных сообщения в веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="ff3d0-109">Для получения дополнительных сведений о планировании обмен мгновенными сообщениями и присутствия, видеть [Планирование обмена мгновенными сообщениями и присутствия в Скайп для Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="ff3d0-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff3d0-110">Если почтовый ящик пользователя находится в локальную систему Exchange, Скайп для клиента Business (2016 C2R построения 16.0.6920.1000) является обязательным</span><span class="sxs-lookup"><span data-stu-id="ff3d0-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="ff3d0-111">Чтобы включить или отключить автономный режим обмена мгновенными Сообщениями в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ff3d0-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="ff3d0-112">Откройте Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="ff3d0-113">Выполните следующую команду, чтобы включить службу отправки автономных мгновенных сообщений:</span><span class="sxs-lookup"><span data-stu-id="ff3d0-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="ff3d0-114">В Скайп Business Server 2015 накопительным пакетом обновления 3 параметр EnableOfflineIM имеет значение $True по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="ff3d0-115">Чтобы отключить службу, задайте значение $False.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="ff3d0-116">Выполните следующую команду, чтобы подтвердить, что хранящихся в автономном режиме обмена мгновенными Сообщениями имеет значение.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="ff3d0-117">Интеграция службы отправки автономных мгновенных сообщений с Exchange</span><span class="sxs-lookup"><span data-stu-id="ff3d0-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="ff3d0-p103">Отправка автономных мгновенных сообщений будет недоступна для отправителей, если их политика клиента запрещает автоматическое сохранение автономных мгновенных сообщений в папке журнала бесед (EnableIMAutoArchiving = $false). Механизм, позволяющий убедиться, что получатель может принимать автономные мгновенные сообщения, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="ff3d0-120">Для автономных сообщений, отправленных в рамках одной организации они будут получены как сообщения электронной почты с помощью класса сообщений для обмена мгновенными Сообщениями. Note.MissedConversation и будет включено в папке Outlook **Пропущенные беседы** , а также журнал бесед, который будет обработан последние на вкладке журнал списка/бесед в Скайп пользователей.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="ff3d0-121">Автономные сообщения, отправляемые из федеративной организации, будут получены как сообщения электронной почты без пометки IM.Note.MisssedConversation: они не будут сохраняться в папках пропущенной беседы и журнала бесед.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="ff3d0-122">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ff3d0-122">Troubleshooting</span></span>

<span data-ttu-id="ff3d0-123">Существует две минуты таймера из при автономной сообщение отправляется при обработан и обработки.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="ff3d0-124">Если не удается обработать автономных сообщений они будут отображаться в следующий каталог:</span><span class="sxs-lookup"><span data-stu-id="ff3d0-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="ff3d0-125">Основной Скайп для бизнеса ETL журнала будет содержать сведения об обработке автономных сообщений и — Лучший источник для исследования и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="ff3d0-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ff3d0-p105">Было сообщено о следующей проблеме: сбой отправки автономных сообщений и заполнение сообщениями папки "Черновики". Эта проблема наблюдалась для почтовых ящиков локальной организации Exchange. На 14 июня 2016 г данная проблема была устранена для всех каналов C2R. </span><span class="sxs-lookup"><span data-stu-id="ff3d0-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
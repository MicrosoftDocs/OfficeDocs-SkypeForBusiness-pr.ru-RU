---
title: 'Lync Server 2013: функции интегрированной единой системы обмена сообщениями'
description: 'Lync Server 2013: функции интегрированной единой системы обмена сообщениями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2caa75504c0468293ced8f20946500fad7cf54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543405"
---
# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="129ee-103">Функции интегрированной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="129ee-103">Features of integrated Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="129ee-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="129ee-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="129ee-105">Lync Server 2013, корпоративный голос использует инфраструктуру единой системы обмена сообщениями Exchange для предоставления автоответчика, уведомления о вызовах, голосового доступа (в том числе голосовой почты) и служб автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="129ee-105">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="129ee-106">Автоответчик</span><span class="sxs-lookup"><span data-stu-id="129ee-106">Call Answering</span></span>

<span data-ttu-id="129ee-p101">Функция автоответчика обеспечивает прием голосовых сообщений от имени пользователя, который не может ответить на звонок. При этом воспроизводится персональное приветствие и записывается сообщение, которое затем помещается в очередь на доставку в почтовый ящик пользователя, хранящийся на сервере почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="129ee-p101">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy. It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="129ee-p102">Если звонящий оставляет сообщение, оно помещается в ящик входящих сообщений пользователя. Если звонящий решает не оставлять сообщение, в почтовом ящике сохраняется уведомление о пропущенном звонке. Пользователь затем может получить доступ к своему ящику входящих сообщений с помощью клиента обмена сообщениями и совместной работы Microsoft Outlook, Outlook Web Access, технологии Exchange ActiveSync или голосового доступа к Outlook. Темы и приоритет звонков могут отображаться так же, как для электронной почты.</span><span class="sxs-lookup"><span data-stu-id="129ee-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="129ee-113">Голосовой доступ к Outlook</span><span class="sxs-lookup"><span data-stu-id="129ee-113">Outlook Voice Access</span></span>

<span data-ttu-id="129ee-114">Голосовой доступ к Outlook позволяет пользователю корпоративной голосовой связи получать доступ не только к голосовой почте, но и к папке "Входящие" Exchange, в том числе к электронной почте, календарю и контактам из интерфейса телефонии.</span><span class="sxs-lookup"><span data-stu-id="129ee-114">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="129ee-115">Номер абонентского доступа назначается администратором единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="129ee-115">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="129ee-116">Автосекретарь</span><span class="sxs-lookup"><span data-stu-id="129ee-116">Auto Attendant</span></span>

<span data-ttu-id="129ee-117">Автосекретарь — это функция единой системы обмена сообщениями Exchange, которую можно использовать для настройки номера телефона, который внешние пользователи могут набрать для связи с представителями компании.</span><span class="sxs-lookup"><span data-stu-id="129ee-117">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="129ee-118">В частности, она предоставляет ряд голосовых подсказок, облегчающих звонящему навигацию по системе меню.</span><span class="sxs-lookup"><span data-stu-id="129ee-118">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="129ee-119">Список доступных параметров настраивается на сервере единой системы обмена сообщениями Exchange администратор единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="129ee-119">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="129ee-120">Службы факсов</span><span class="sxs-lookup"><span data-stu-id="129ee-120">Fax Services</span></span>

<span data-ttu-id="129ee-121">Единая система обмена сообщениями Exchange включает функции факса, которые позволяют пользователям принимать входящие факсы в своих почтовых ящиках Exchange.</span><span class="sxs-lookup"><span data-stu-id="129ee-121">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="129ee-122">Для получения дополнительных сведений обратитесь к разделу "Единая система обмена сообщениями" в документации по Microsoft Exchange Server по адресу [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652) .</span><span class="sxs-lookup"><span data-stu-id="129ee-122">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?linkId=135652](https://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="129ee-123">Службы факсов, предоставляемые сервером единой системы обмена сообщениями Exchange, недоступны в развертываниях Lync Server, интегрированных с Microsoft Exchange Server 2010, Exchange 2010 с последним пакетом обновления или Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="129ee-123">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


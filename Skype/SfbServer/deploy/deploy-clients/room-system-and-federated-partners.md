---
title: Федеративные партнеры системы комнат Skype и Skype для бизнеса
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: В этом разделе описывается настройка Системы комнат Skype для федеративных партнеров Skype для бизнеса.
ms.openlocfilehash: 8ded7ba9be24cf1ac700be0ead1c7e0c3637becd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002999"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="9af77-103">Федеративные партнеры системы комнат Skype и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9af77-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="9af77-104">В этом разделе описывается настройка Системы комнат Skype для федеративных партнеров Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9af77-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="9af77-105">Федеративные партнеры системы комнат Skype и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9af77-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="9af77-106">В приглашении на собрание в календаре для системы комнат Skype используется ссылка "присоединиться к собранию Skype для бизнеса".</span><span class="sxs-lookup"><span data-stu-id="9af77-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="9af77-107">The join link is usually found in the body of a meeting request.</span><span class="sxs-lookup"><span data-stu-id="9af77-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="9af77-108">Тем не менее, система комнаты Skype зависит от этой ссылки, которая должна быть представлена в свойствах MAPI сообщения.</span><span class="sxs-lookup"><span data-stu-id="9af77-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="9af77-109">Если это приглашение на собрание будет отправлено в удаленные Организации (Федеративные партнеры Skype для бизнеса), по умолчанию в системе комнаты Skype удаленной организации не отображается ссылка присоединение к собранию в календаре.</span><span class="sxs-lookup"><span data-stu-id="9af77-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="9af77-110">На самом деле пользователи Outlook в удаленной организации не смогут присоединиться к собранию Skype для бизнеса, щелкнув правой кнопкой мыши элемент календаря или в рамках напоминания о собрании.</span><span class="sxs-lookup"><span data-stu-id="9af77-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="9af77-111">Они должны открыть приглашение на собрание и щелкнуть присоединиться к собранию Skype для бизнеса в тексте сообщения.</span><span class="sxs-lookup"><span data-stu-id="9af77-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="9af77-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span><span class="sxs-lookup"><span data-stu-id="9af77-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="9af77-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span><span class="sxs-lookup"><span data-stu-id="9af77-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="9af77-114">Для отображения ссылки присоединения к собранию в удаленной системе комнат Skype необходимо включить TNEF с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9af77-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="9af77-115">Когда метод TNEF включен для удаленной организации, сообщения, отправляемые организации через Интернет, будут представлены в виде вложения в формате TNEF.</span><span class="sxs-lookup"><span data-stu-id="9af77-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="9af77-116">При включенном формате TNEF при отправке приглашений на собрание Skype для бизнеса для федеративного партнера Skype для бизнеса система комнат Skype сможет отобразить собрание Skype для бизнеса, и удаленные пользователи смогут присоединиться к собраниям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9af77-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 

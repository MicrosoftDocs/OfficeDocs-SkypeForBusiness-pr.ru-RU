---
title: Система комнат Skype и федераированные партнеры Skype для бизнеса
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: В этом разделе вы узнаете, как настроить систему комнат Skype для федераированных партнеров Skype для бизнеса.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820809"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="4ed50-103">Система комнат Skype и федераированные партнеры Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4ed50-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="4ed50-104">В этом разделе вы узнаете, как настроить систему комнат Skype для федераированных партнеров Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4ed50-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="4ed50-105">Система комнат Skype и федераированные партнеры Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4ed50-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="4ed50-106">Система комнат Skype использует ссылку "Присоединиться к собранию Skype для бизнеса" в календарном запросе на собрание.</span><span class="sxs-lookup"><span data-stu-id="4ed50-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="4ed50-107">Ссылка на присоединиться обычно находится в теле запроса на собрание.</span><span class="sxs-lookup"><span data-stu-id="4ed50-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="4ed50-108">Однако система комнат Skype зависит от того, присутствует ли эта ссылка в свойствах MAPI сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ed50-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="4ed50-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span><span class="sxs-lookup"><span data-stu-id="4ed50-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="4ed50-110">Пользователи Outlook в удаленной организации не смогут присоединиться к собранию Skype для бизнеса, щелкнув правой кнопкой мыши элемент календаря или из напоминания о собрании.</span><span class="sxs-lookup"><span data-stu-id="4ed50-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="4ed50-111">Они должны открыть приглашение на собрание и щелкнуть "Присоединиться к собранию Skype для бизнеса" в тексте сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ed50-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="4ed50-112">Причина этого ограничения заключается в том, что Outlook и Microsoft Exchange не используют специальный метод для упаковки сведений для отправки сообщений через Интернет.</span><span class="sxs-lookup"><span data-stu-id="4ed50-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="4ed50-113">Этот метод, который называется форматом TNEF, по умолчанию отключен для сообщений, отправленных извне из организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="4ed50-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="4ed50-114">Чтобы ссылка на присоединиться к собранию появлялась в удаленной системе комнат Skype, отправляя организация должна включить TNEF с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4ed50-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="4ed50-115">После включения формата TNEF для удаленной организации все сообщения, отправленные в организацию через Интернет, отправляются в виде вложения в формате TNEF.</span><span class="sxs-lookup"><span data-stu-id="4ed50-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="4ed50-116">Если TNEF включен, то при отправлении запроса на собрание Skype для бизнеса федератированному партнеру Skype для бизнеса система комнат Skype сможет отрисовки собрания перейти к собранию Skype для бизнеса, а удаленные пользователи смогут присоединяться к собраниям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4ed50-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 

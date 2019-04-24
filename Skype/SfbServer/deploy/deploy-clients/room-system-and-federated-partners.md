---
title: Федеративные партнеры системы комнат Skype и Skype для бизнеса
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: В этом разделе описывается настройка Системы комнат Skype для федеративных партнеров Skype для бизнеса.
ms.openlocfilehash: e954bf5d7586c651d9d045b2d428f86f01de8a30
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219390"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="4d393-103">Федеративные партнеры системы комнат Skype и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4d393-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="4d393-104">В этом разделе описывается настройка Системы комнат Skype для федеративных партнеров Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4d393-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="4d393-105">Федеративные партнеры системы комнат Skype и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4d393-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="4d393-106">Система комнаты Скайп полагается на Скайп присоединиться к для собраний ссылку в приглашении на собрание календаря.</span><span class="sxs-lookup"><span data-stu-id="4d393-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="4d393-107">The join link is usually found in the body of a meeting request.</span><span class="sxs-lookup"><span data-stu-id="4d393-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="4d393-108">Тем не менее система комнаты Скайп зависит от этой ссылке, чтобы быть представлены в разделе свойства MAPI сообщения.</span><span class="sxs-lookup"><span data-stu-id="4d393-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="4d393-109">При этом собрание отправляется удаленного организаций (Скайп для федеративных партнеров), по умолчанию будет Скайп комнаты системы удаленного организации не показывать ссылку присоединения к собранию в календаре.</span><span class="sxs-lookup"><span data-stu-id="4d393-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="4d393-110">На самом деле пользователей Outlook в удаленную организацию смогут присоединяться к Скайп для собраний с правой кнопкой мыши календаря, элемента или из в рамках собрания напоминание.</span><span class="sxs-lookup"><span data-stu-id="4d393-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="4d393-111">Они должны откройте приглашение и нажмите кнопку Скайп присоединиться к собранию Business в тексте сообщения.</span><span class="sxs-lookup"><span data-stu-id="4d393-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="4d393-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span><span class="sxs-lookup"><span data-stu-id="4d393-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="4d393-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span><span class="sxs-lookup"><span data-stu-id="4d393-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="4d393-114">Для участия в собрании ссылку присоединиться к отображаться в удаленной системе комнаты Скайп, отправляющим организации необходимо включить TNEF с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4d393-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="4d393-115">Когда метод TNEF включен для удаленной организации, сообщения, отправляемые организации через Интернет, будут представлены в виде вложения в формате TNEF.</span><span class="sxs-lookup"><span data-stu-id="4d393-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="4d393-116">С поддержкой TNEF при Скайп для бизнеса приглашения на собрание отправляется Скайп для федеративного партнера, система комнаты Скайп будет иметь возможность отображения Скайп присоединиться к собранию бизнес и удаленные пользователи смогут присоединиться к Скайп для деловых встреч.</span><span class="sxs-lookup"><span data-stu-id="4d393-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
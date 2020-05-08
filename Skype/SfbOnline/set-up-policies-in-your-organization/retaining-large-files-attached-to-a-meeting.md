---
title: Сохранение больших файлов, вложенных в собрание Skype для бизнеса
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Вы можете прикрепить файлы к собранию Skype для бизнеса, после чего участники смогут открыть и загрузить его. Файлы, вложенные в собрания Skype для бизнеса, сохраняются в почтовых ящиках любого участника, чей почтовый ящик размещен на удержании судебного разбирательства, имеет политику хранения Microsoft 365 или Office 365 или размещается на удержании, связанном с делом обнаружения электронных данных в центре соответствия требованиям Microsoft 365. Это содержимое сохраняется в папках "элементы с возможностью восстановления" в своих почтовых ящиках участников.
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164078"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="65086-105">Сохранение больших файлов, вложенных в собрание Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="65086-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="65086-106">Вы можете прикрепить файлы к собранию Skype для бизнеса, после чего участники смогут открыть и загрузить его.</span><span class="sxs-lookup"><span data-stu-id="65086-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="65086-107">Файлы, вложенные в собрания Skype для бизнеса, сохраняются в почтовых ящиках любого участника, чей почтовый ящик размещен на удержании судебного разбирательства, имеет политику хранения Microsoft 365 или Office 365 или размещается на удержании, связанном с делом обнаружения электронных данных в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65086-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="65086-108">Это содержимое сохраняется в папках " **элементы с возможностью восстановления** " в своих почтовых ящиках участников.</span><span class="sxs-lookup"><span data-stu-id="65086-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="65086-109">Файлы, которые хранятся в почтовых ящиках на удержании, индексируются, и их можно просматривать при выполнении поиска содержимого &amp; в центре соответствия требованиям безопасности при поиске в почтовом ящике участника.</span><span class="sxs-lookup"><span data-stu-id="65086-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="65086-110">Тем не менее, вложенные файлы размером более 30 МБ делятся на несколько меньших файлов и сохраняются как сжатые ZIP-файлы.</span><span class="sxs-lookup"><span data-stu-id="65086-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="65086-111">*Содержимое* этих файлов не индексируется для поиска и может не возвращаться при поиске контента.</span><span class="sxs-lookup"><span data-stu-id="65086-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="65086-112">Однако *метаданные* этих файлов (например, имя файла и автор) индексируются для поиска и могут возвращаться при поиске контента.</span><span class="sxs-lookup"><span data-stu-id="65086-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65086-113">Параметры MaxReceiveSize и MaxSendSize для почтового ящика Exchange Online могут повлиять на возможность сохранять большие файлы в собраниях Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="65086-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="65086-114">Параметры по умолчанию для MaxReceiveSize и MaxSendSize — 36 МБ и 35 МБ соответственно.</span><span class="sxs-lookup"><span data-stu-id="65086-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="65086-115">Однако эти параметры по умолчанию слишком малы для сохранения файлов из собрания Skype для бизнеса, превышающего 30 МБ.</span><span class="sxs-lookup"><span data-stu-id="65086-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="65086-116">Это происходит из-за того, что в Exchange Online используется кодировка Base64 и другие двоичные данные.</span><span class="sxs-lookup"><span data-stu-id="65086-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="65086-117">При кодировании сообщения его размер увеличивается на 33%.</span><span class="sxs-lookup"><span data-stu-id="65086-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="65086-118">Таким образом, чтобы гарантировать хранение больших файлов из собраний Skype для бизнеса, рекомендуется увеличить значения для MaxReceiveSize и MaxSendSize до 39 MB (примерно 33% больше, чем в 30 МБ, более чем в течение 50 Мбайт) для пользователей, которые помещаются на удержание.</span><span class="sxs-lookup"><span data-stu-id="65086-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="65086-119">В противном случае большой файл, вложенный в собрание Skype для бизнеса, может не поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="65086-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="65086-120">Дополнительные сведения об использовании команд **Set-Mailbox-MaxReceiveSize** и **Set-Mailbox-MaxSendSize** в Exchange Online PowerShell можно найти в статьях [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span><span class="sxs-lookup"><span data-stu-id="65086-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="65086-121">Почтовые ящики, не включенные в удержание, не будут сохранять данные о собрании.</span><span class="sxs-lookup"><span data-stu-id="65086-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="65086-122">Например, на собрании с тремя сотрудниками, в котором пометки почтовых ящиков двух участников помечены для хранения, данные собраний сохраняются в почтовые ящики этих двух участников, но не в почтовый ящик третьего участника, чей почтовый ящик не находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="65086-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="65086-123">См. также</span><span class="sxs-lookup"><span data-stu-id="65086-123">Related topics</span></span>
[<span data-ttu-id="65086-124">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="65086-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="65086-125">Блокировка передачи файлов между точками</span><span class="sxs-lookup"><span data-stu-id="65086-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="65086-126">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="65086-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="65086-127">Настройка политик конференц-связи в Организации</span><span class="sxs-lookup"><span data-stu-id="65086-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 

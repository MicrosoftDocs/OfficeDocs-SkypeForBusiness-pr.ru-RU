---
title: Сохранение больших файлов, вложенных в Skype для бизнеса собрания
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
description: Вы можете вложенные файлы в Skype для бизнеса, которые затем участники смогут открывать и скачивать. Файлы, вложенные в собрания Skype для бизнеса, сохраняются в почтовых ящиках всех участников, почтовый ящик которых помещен на хранение для судебного разбирательства, к которым применена политика хранения Microsoft 365 или Office 365, или помещается на удержание, связанное с делом eDiscovery в Центре Microsoft 365 соответствия требованиям. Это содержимое будет сохранено в папках "Элементы с возможностью восстановления" участников в их почтовых ящиках.
ms.openlocfilehash: 74605b9aebf6d83619282d9cfc9094216d2fe6f1
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240111"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="f7d5f-105">Сохранение больших файлов, вложенных в Skype для бизнеса собрания</span><span class="sxs-lookup"><span data-stu-id="f7d5f-105">Retaining large files attached to a Skype for Business meeting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="f7d5f-106">Вы можете вложенные файлы в Skype для бизнеса, которые затем участники смогут открывать и скачивать.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="f7d5f-107">Файлы, вложенные в собрания Skype для бизнеса, сохраняются в почтовых ящиках всех участников, почтовый ящик которых помещен на хранение для судебного разбирательства, к которым применена политика хранения Microsoft 365 или Office 365, или помещается на удержание, связанное с делом eDiscovery в Центре Microsoft 365 соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="f7d5f-108">Это содержимое будет сохранено в папках **"Элементы** с возможностью восстановления" участников в их почтовых ящиках.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="f7d5f-109">Файлы, которые сохраняются в почтовых ящиках на удержании, индексация, поэтому при выполнении поиска контента в Центре соответствия требованиям безопасности можно искать при поиске в почтовом ящике &amp; участника.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="f7d5f-110">Однако вложенные файлы размером более 30 МБ разделены на несколько файлов и сохраняются как сжатые (.zip).</span><span class="sxs-lookup"><span data-stu-id="f7d5f-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="f7d5f-111">Содержимое  *таких*  небольших файлов не индексется для поиска и может не быть возвращено при поиске контента.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="f7d5f-112">Однако *метаданные этих файлов*  (например, имя файла и автор) индексироваться для поиска и могут быть возвращены при поиске контента.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7d5f-113">Параметры MaxReceiveSize и MaxSendSize для почтового ящика Exchange Online могут повлиять на возможность сохранения больших файлов Skype для бизнеса собраний.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="f7d5f-114">По умолчанию для maxReceiveSize и MaxSendSize заданы значения 36 и 35 МБ соответственно.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="f7d5f-115">Однако эти параметры по умолчанию слишком малы для сохранения файла из собрания Skype для бизнеса размером более 30 МБ.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="f7d5f-116">Это потому, Exchange Online использует кодику Base64 для вложений в сообщения и других двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="f7d5f-117">При кодировании сообщения его размер увеличивается примерно на 33 %.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="f7d5f-118">Поэтому для сохранения больших файлов из собраний Skype для бизнеса рекомендуется увеличить значение для maxReceiveSize и MaxSendSize до 39 МБ (что примерно на 33 % больше, чем ранее объяснялось ограничение в 30 МБ) для пользователей, помещенных на удержание.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="f7d5f-119">В противном случае большой файл, вложенный в Skype для бизнеса собрания, может не сохраниться.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="f7d5f-120">Дополнительные сведения об использовании команд **Set-Mailbox -MaxReceiveSize** и **Set-Mailbox -MaxSendSize** в powerShell см. в Exchange Online PowerShell. [](/powershell/module/exchange/mailboxes/Set-Mailbox)</span><span class="sxs-lookup"><span data-stu-id="f7d5f-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="f7d5f-121">В почтовых ящиках, которые не находятся на удержании, не сохраняются данные собраний.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="f7d5f-122">Например, на собрании с тремя участниками, где почтовые ящики двух участников помечены для хранения, данные собрания сохраняются в почтовых ящиках этих двух участников, но не в почтовые ящики третьего участника, почтовый ящик которого не находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="f7d5f-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f7d5f-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f7d5f-123">Related topics</span></span>
[<span data-ttu-id="f7d5f-124">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="f7d5f-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="f7d5f-125">Блокировка передачи файлов по точкам</span><span class="sxs-lookup"><span data-stu-id="f7d5f-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="f7d5f-126">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="f7d5f-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="f7d5f-127">Настройка политик conferencing в организации</span><span class="sxs-lookup"><span data-stu-id="f7d5f-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  

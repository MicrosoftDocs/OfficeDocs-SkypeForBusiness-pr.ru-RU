---
title: Хранение больших файлов, подключенного к Скайп для собраний
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Вы можете прикрепить файлы с Скайп для собраний, кто из пользователей, затем можно открыть и загрузите. Файлами, подключенными к Скайп для деловых встреч, сохраняются в почтовых ящиках любой участник почтовый ящик которого размещается на хранение для судебного разбирательства, имеет применена политика хранения Office 365 или ставится на удержание, связанные с вариантом eDiscovery безопасности Office 365 &amp; Центре соответствия требованиям. Это содержимое сохраняется папки элементов для восстановления участников в их почтовые ящики.
ms.openlocfilehash: b38f2ec56fb53932c08ede2a8c6f39557216a6b8
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864978"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="1a9c9-105">Хранение больших файлов, подключенного к Скайп для собраний</span><span class="sxs-lookup"><span data-stu-id="1a9c9-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="1a9c9-106">Вы можете прикрепить файлы с Скайп для собраний, кто из пользователей, затем можно открыть и загрузите.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="1a9c9-107">Файлами, подключенными к Скайп для деловых встреч, сохраняются в почтовых ящиках любой участник почтовый ящик которого размещается на хранение для судебного разбирательства, имеет применена политика хранения Office 365 или ставится на удержание, связанные с вариантом eDiscovery безопасности Office 365 &amp; Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="1a9c9-108">Это содержимое сохраняется папки **Элементов для восстановления** участников в их почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="1a9c9-109">Файлы, которые сохраняются в почтовые ящики на удержание, индексируются и поэтому может быть выполнен при выполнении поиска контента в системы &amp; центре соответствия требованиям при поиске почтового ящика участника.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="1a9c9-110">Тем не менее вложенные файлы, размер которых превышает 39 МБ, разделенных на несколько файлов меньшего размера и сохраняются в виде ZIP-файлов.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="1a9c9-111">*Содержимое* этих файлов меньшего размера не индексироваться для поиска и не может быть возвращено при поиске содержимого.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="1a9c9-112">Тем не менее, *метаданные* из этих файлов (например, имя файла и автор) индексироваться для поиска и могут возвращаться в поиска контента.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a9c9-113">Если почтовый ящик заполнен или администратору клиента настроил MaxSendSize быть меньше 39 МБ, отправить файл данных не должны сохраняться вообще.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="1a9c9-114">По умолчанию MaxSendSize 150 МБ, но клиент администраторы могут настраивать MaxSendSize быть как 1 МБ.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="1a9c9-115">Почтовые ящики, которые не являются на удержание не будет сохранен данные собрания.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="1a9c9-116">Например на собрании три человека в которой почтовые ящики двух участников помечены как для хранения, собрания данные сохраняются в почтовые ящики этих двух участников, но не к почтовому ящику третий участник, почтовый ящик которого нет на удержание.</span><span class="sxs-lookup"><span data-stu-id="1a9c9-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1a9c9-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a9c9-117">Related topics</span></span>
[<span data-ttu-id="1a9c9-118">Создание настраиваемых политик внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="1a9c9-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="1a9c9-119">Передача файлов точка-точка блока</span><span class="sxs-lookup"><span data-stu-id="1a9c9-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="1a9c9-120">Настройка политик клиента в организации</span><span class="sxs-lookup"><span data-stu-id="1a9c9-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="1a9c9-121">Настройка политик конференц-связи в вашей организации</span><span class="sxs-lookup"><span data-stu-id="1a9c9-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 
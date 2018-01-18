---
title: "Поддержка Skype для бизнеса Online в веб-приложении Outlook"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Outlook в Интернете (Outlook Web App) в Office 365 предлагает базового Скайп для веб-клиента Business панели навигации. Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365. Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально. Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app."
ms.openlocfilehash: 8688123f0e19a648dae7706dc346a647ecd99211
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="6cd8c-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="6cd8c-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="6cd8c-107">Outlook в Интернете (Outlook Web App) в Office 365 предлагает базового Скайп для веб-клиента Business панели навигации.</span><span class="sxs-lookup"><span data-stu-id="6cd8c-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="6cd8c-108">Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cd8c-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="6cd8c-109">Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально.</span><span class="sxs-lookup"><span data-stu-id="6cd8c-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="6cd8c-110">Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="6cd8c-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="6cd8c-111">В следующей таблице перечислены различные параметры настройки, которые могут иметь и веб-клиент, который используется.</span><span class="sxs-lookup"><span data-stu-id="6cd8c-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6cd8c-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="6cd8c-112">**User account is located**</span></span> <br/> |<span data-ttu-id="6cd8c-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="6cd8c-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="6cd8c-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="6cd8c-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="6cd8c-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6cd8c-115">Online</span></span>  <br/> |<span data-ttu-id="6cd8c-116">Нет</span><span class="sxs-lookup"><span data-stu-id="6cd8c-116">No</span></span>  <br/> |<span data-ttu-id="6cd8c-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6cd8c-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="6cd8c-118">Online</span></span>  <br/> |<span data-ttu-id="6cd8c-119">Да</span><span class="sxs-lookup"><span data-stu-id="6cd8c-119">Yes</span></span>  <br/> |<span data-ttu-id="6cd8c-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="6cd8c-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="6cd8c-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="6cd8c-122">Нет</span><span class="sxs-lookup"><span data-stu-id="6cd8c-122">No</span></span>  <br/> |<span data-ttu-id="6cd8c-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6cd8c-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="6cd8c-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="6cd8c-125">Да</span><span class="sxs-lookup"><span data-stu-id="6cd8c-125">Yes</span></span>  <br/> |<span data-ttu-id="6cd8c-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="6cd8c-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="6cd8c-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="6cd8c-128">Нет</span><span class="sxs-lookup"><span data-stu-id="6cd8c-128">No</span></span>  <br/> |<span data-ttu-id="6cd8c-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="6cd8c-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="6cd8c-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="6cd8c-131">Да</span><span class="sxs-lookup"><span data-stu-id="6cd8c-131">Yes</span></span>  <br/> |<span data-ttu-id="6cd8c-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="6cd8c-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-133">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="6cd8c-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="6cd8c-134">Нет</span><span class="sxs-lookup"><span data-stu-id="6cd8c-134">No</span></span>  <br/> |<span data-ttu-id="6cd8c-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="6cd8c-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="6cd8c-136">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="6cd8c-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="6cd8c-137">Да</span><span class="sxs-lookup"><span data-stu-id="6cd8c-137">Yes</span></span>  <br/> |<span data-ttu-id="6cd8c-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="6cd8c-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="6cd8c-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="6cd8c-139">Related topics</span></span>
[<span data-ttu-id="6cd8c-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6cd8c-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6cd8c-141">Сообщите Скайп для бизнес-пользователям добавлять контакты Скайп</span><span class="sxs-lookup"><span data-stu-id="6cd8c-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
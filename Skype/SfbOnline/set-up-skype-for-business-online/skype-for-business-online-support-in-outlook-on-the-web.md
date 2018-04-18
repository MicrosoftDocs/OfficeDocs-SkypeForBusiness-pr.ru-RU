---
title: Поддержка Skype для бизнеса Online в веб-приложении Outlook
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Веб-приложение Outlook в Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365. Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально. Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app.
ms.openlocfilehash: 03491bb0cb200cac8eecb0ae2282a7003a85f8dc
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="2f2f9-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="2f2f9-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="2f2f9-107">Веб-приложение Outlook в Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="2f2f9-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="2f2f9-108">Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f2f9-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="2f2f9-109">Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально.</span><span class="sxs-lookup"><span data-stu-id="2f2f9-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="2f2f9-110">Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="2f2f9-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="2f2f9-111">В следующей таблице перечислены различные параметры настройки, которые могут иметь и веб-клиент, который используется.</span><span class="sxs-lookup"><span data-stu-id="2f2f9-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="2f2f9-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="2f2f9-112">**User account is located**</span></span> <br/> |<span data-ttu-id="2f2f9-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="2f2f9-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="2f2f9-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="2f2f9-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="2f2f9-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="2f2f9-115">Online</span></span>  <br/> |<span data-ttu-id="2f2f9-116">Нет</span><span class="sxs-lookup"><span data-stu-id="2f2f9-116">No</span></span>  <br/> |<span data-ttu-id="2f2f9-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2f2f9-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="2f2f9-118">Online</span></span>  <br/> |<span data-ttu-id="2f2f9-119">Да</span><span class="sxs-lookup"><span data-stu-id="2f2f9-119">Yes</span></span>  <br/> |<span data-ttu-id="2f2f9-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="2f2f9-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="2f2f9-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="2f2f9-122">Нет</span><span class="sxs-lookup"><span data-stu-id="2f2f9-122">No</span></span>  <br/> |<span data-ttu-id="2f2f9-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2f2f9-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="2f2f9-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="2f2f9-125">Да</span><span class="sxs-lookup"><span data-stu-id="2f2f9-125">Yes</span></span>  <br/> |<span data-ttu-id="2f2f9-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="2f2f9-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="2f2f9-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="2f2f9-128">Нет</span><span class="sxs-lookup"><span data-stu-id="2f2f9-128">No</span></span>  <br/> |<span data-ttu-id="2f2f9-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="2f2f9-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="2f2f9-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="2f2f9-131">Да</span><span class="sxs-lookup"><span data-stu-id="2f2f9-131">Yes</span></span>  <br/> |<span data-ttu-id="2f2f9-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="2f2f9-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-133">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="2f2f9-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="2f2f9-134">Нет</span><span class="sxs-lookup"><span data-stu-id="2f2f9-134">No</span></span>  <br/> |<span data-ttu-id="2f2f9-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="2f2f9-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="2f2f9-136">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="2f2f9-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="2f2f9-137">Да</span><span class="sxs-lookup"><span data-stu-id="2f2f9-137">Yes</span></span>  <br/> |<span data-ttu-id="2f2f9-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="2f2f9-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="2f2f9-139">See also</span><span class="sxs-lookup"><span data-stu-id="2f2f9-139">Related topics</span></span>
[<span data-ttu-id="2f2f9-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2f2f9-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="2f2f9-141">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2f2f9-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
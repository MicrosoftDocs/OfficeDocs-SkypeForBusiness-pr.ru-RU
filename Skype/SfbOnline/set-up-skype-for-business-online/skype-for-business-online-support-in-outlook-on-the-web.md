---
title: Поддержка Skype для бизнеса Online в веб-приложении Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
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
description: Outlook в Интернете (Outlook Web App) в Microsoft 365 или Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступен для пользователей Online, администратор которых не настроил им такой URL-адрес для Microsoft 365 и Office 365. Если учетная запись пользователя находится в сети и у него нет иммеривного URL-адреса, интерфейс будет по-прежнему работать, даже если в организации есть некоторые учетные записи пользователей, которые находятся локально. Пользователи, у которых есть учетные записи пользователей локально (вне зависимости от того, имеют ли они им иместивший им URL-адрес) или управляются Корпорацией Майкрософт, будут видеть интерфейс Lync в веб-приложении Outlook.
ms.openlocfilehash: ab426bdaf0261dcfb3375934eb1e5a6f5bd6df79
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164115"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="09729-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="09729-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="09729-p102">Outlook в Интернете (Outlook Web App) в Microsoft 365 или Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступен для пользователей Online, администратор которых не настроил им такой URL-адрес для Microsoft 365 и Office 365. Если учетная запись пользователя находится в сети и у него нет иммеривного URL-адреса, интерфейс будет по-прежнему работать, даже если в организации есть некоторые учетные записи пользователей, которые находятся локально. Пользователи, у которых есть учетные записи пользователей локально (вне зависимости от того, имеют ли они им иместивший им URL-адрес) или управляются Корпорацией Майкрософт, будут видеть интерфейс Lync в веб-приложении Outlook.</span><span class="sxs-lookup"><span data-stu-id="09729-p102">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="09729-111">В таблице ниже общались различные настройки и используемый веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="09729-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="09729-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="09729-112">**User account is located**</span></span> <br/> |<span data-ttu-id="09729-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="09729-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="09729-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="09729-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="09729-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="09729-115">Online</span></span>  <br/> |<span data-ttu-id="09729-116">Нет</span><span class="sxs-lookup"><span data-stu-id="09729-116">No</span></span>  <br/> |<span data-ttu-id="09729-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09729-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="09729-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="09729-118">Online</span></span>  <br/> |<span data-ttu-id="09729-119">Да</span><span class="sxs-lookup"><span data-stu-id="09729-119">Yes</span></span>  <br/> |<span data-ttu-id="09729-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09729-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09729-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="09729-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="09729-122">Нет</span><span class="sxs-lookup"><span data-stu-id="09729-122">No</span></span>  <br/> |<span data-ttu-id="09729-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09729-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="09729-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="09729-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="09729-125">Да</span><span class="sxs-lookup"><span data-stu-id="09729-125">Yes</span></span>  <br/> |<span data-ttu-id="09729-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09729-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09729-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="09729-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="09729-128">Нет</span><span class="sxs-lookup"><span data-stu-id="09729-128">No</span></span>  <br/> |<span data-ttu-id="09729-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09729-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09729-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="09729-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="09729-131">Да</span><span class="sxs-lookup"><span data-stu-id="09729-131">Yes</span></span>  <br/> |<span data-ttu-id="09729-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09729-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09729-133">Только предварительная</span><span class="sxs-lookup"><span data-stu-id="09729-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="09729-134">Нет</span><span class="sxs-lookup"><span data-stu-id="09729-134">No</span></span>  <br/> |<span data-ttu-id="09729-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09729-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09729-136">Только предварительная</span><span class="sxs-lookup"><span data-stu-id="09729-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="09729-137">Да</span><span class="sxs-lookup"><span data-stu-id="09729-137">Yes</span></span>  <br/> |<span data-ttu-id="09729-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09729-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="09729-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="09729-139">Related topics</span></span>
[<span data-ttu-id="09729-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="09729-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="09729-141">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09729-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

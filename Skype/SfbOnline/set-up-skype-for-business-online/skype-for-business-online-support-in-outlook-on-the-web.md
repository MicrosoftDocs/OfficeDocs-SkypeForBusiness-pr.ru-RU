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
description: Outlook веб-браузере (Outlook Web App) Microsoft 365 или Office 365 на панели навигации Skype для бизнеса веб-клиент. Этот базовый клиент доступен для пользователей Online, администратор которых не настроил им Microsoft 365 и Office 365. Если учетная запись пользователя находится в сети и у нее нет простого URL-адреса, интерфейс будет по-прежнему видеться, даже если в организации есть некоторые учетные записи пользователей, которые находятся локально. Пользователи, у которых есть учетные записи пользователей в локальной версии (независимо от того, имеют ли они такой url-адрес) или управляются корпорацией Майкрософт, будут видеть интерфейс Lync в веб-приложении Outlook.
ms.openlocfilehash: aa6f82f6647db1816c630486bee0d415d05b3b77
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239574"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="d008e-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="d008e-106">Skype for Business Online support in Outlook on the web</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="d008e-107">Outlook веб-браузере (Outlook Web App) Microsoft 365 или Office 365 на панели навигации Skype для бизнеса веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="d008e-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="d008e-108">Этот базовый клиент доступен для пользователей Online, администратор которых не настроил им Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="d008e-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="d008e-109">Если учетная запись пользователя находится в сети и у нее нет простого URL-адреса, интерфейс будет по-прежнему видеться, даже если в организации есть некоторые учетные записи пользователей, которые находятся локально.</span><span class="sxs-lookup"><span data-stu-id="d008e-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="d008e-110">Пользователи, у которых есть учетные записи пользователей в локальной версии (независимо от того, имеют ли они такой url-адрес) или управляются корпорацией Майкрософт, будут видеть интерфейс Lync в веб-приложении Outlook.</span><span class="sxs-lookup"><span data-stu-id="d008e-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="d008e-111">В следующей таблице 2010 2010 2016 2016 2016 2016 2013 2016 2016 2016 2016 2016</span><span class="sxs-lookup"><span data-stu-id="d008e-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d008e-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="d008e-112">**User account is located**</span></span> <br/> |<span data-ttu-id="d008e-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="d008e-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="d008e-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="d008e-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="d008e-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="d008e-115">Online</span></span>  <br/> |<span data-ttu-id="d008e-116">Нет</span><span class="sxs-lookup"><span data-stu-id="d008e-116">No</span></span>  <br/> |<span data-ttu-id="d008e-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d008e-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="d008e-118">Online</span></span>  <br/> |<span data-ttu-id="d008e-119">Да</span><span class="sxs-lookup"><span data-stu-id="d008e-119">Yes</span></span>  <br/> |<span data-ttu-id="d008e-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="d008e-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="d008e-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d008e-122">Нет</span><span class="sxs-lookup"><span data-stu-id="d008e-122">No</span></span>  <br/> |<span data-ttu-id="d008e-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d008e-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="d008e-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d008e-125">Да</span><span class="sxs-lookup"><span data-stu-id="d008e-125">Yes</span></span>  <br/> |<span data-ttu-id="d008e-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="d008e-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="d008e-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d008e-128">Нет</span><span class="sxs-lookup"><span data-stu-id="d008e-128">No</span></span>  <br/> |<span data-ttu-id="d008e-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="d008e-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="d008e-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d008e-131">Да</span><span class="sxs-lookup"><span data-stu-id="d008e-131">Yes</span></span>  <br/> |<span data-ttu-id="d008e-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="d008e-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-133">Только на предугол</span><span class="sxs-lookup"><span data-stu-id="d008e-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="d008e-134">Нет</span><span class="sxs-lookup"><span data-stu-id="d008e-134">No</span></span>  <br/> |<span data-ttu-id="d008e-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="d008e-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d008e-136">Только на предугол</span><span class="sxs-lookup"><span data-stu-id="d008e-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="d008e-137">Да</span><span class="sxs-lookup"><span data-stu-id="d008e-137">Yes</span></span>  <br/> |<span data-ttu-id="d008e-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="d008e-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="d008e-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d008e-139">Related topics</span></span>
[<span data-ttu-id="d008e-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d008e-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d008e-141">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d008e-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

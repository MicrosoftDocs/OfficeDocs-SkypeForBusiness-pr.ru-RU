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
description: Outlook в Интернете (Outlook Web App) в Office 365 предлагается простой веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступен для пользователей в сети, администратор не настроил запоминающиеся URL-адрес для своей организации Office 365. Несмотря на то, что учетная запись пользователя подключена к сети и не имеет URL-адреса запоминающиеся, она по-прежнему будет видеть интерфейс, даже если в Организации есть некоторые учетные записи пользователей, которые были размещены локально. Пользователи, у которых есть локальные учетные записи (у которых есть URL-адрес запоминающиеся) или управляемые корпорацией Майкрософт, будут видеть взаимодействие с Lync в Outlook Web App.
ms.openlocfilehash: 7eab3ce7c8d6ea8c1f004559ea92f64f554fb010
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692854"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="5ca77-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="5ca77-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="5ca77-p102">Outlook в Интернете (Outlook Web App) в Office 365 предлагается простой веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступен для пользователей в сети, администратор не настроил запоминающиеся URL-адрес для своей организации Office 365. Несмотря на то, что учетная запись пользователя подключена к сети и не имеет URL-адреса запоминающиеся, она по-прежнему будет видеть интерфейс, даже если в Организации есть некоторые учетные записи пользователей, которые были размещены локально. Пользователи, у которых есть локальные учетные записи (у которых есть URL-адрес запоминающиеся) или управляемые корпорацией Майкрософт, будут видеть взаимодействие с Lync в Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="5ca77-p102">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="5ca77-111">В следующей таблице перечислены различные настройки, которые вы можете использовать, и используемые веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="5ca77-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="5ca77-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="5ca77-112">**User account is located**</span></span> <br/> |<span data-ttu-id="5ca77-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="5ca77-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="5ca77-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="5ca77-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="5ca77-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="5ca77-115">Online</span></span>  <br/> |<span data-ttu-id="5ca77-116">Нет</span><span class="sxs-lookup"><span data-stu-id="5ca77-116">No</span></span>  <br/> |<span data-ttu-id="5ca77-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5ca77-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="5ca77-118">Online</span></span>  <br/> |<span data-ttu-id="5ca77-119">Да</span><span class="sxs-lookup"><span data-stu-id="5ca77-119">Yes</span></span>  <br/> |<span data-ttu-id="5ca77-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="5ca77-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="5ca77-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="5ca77-122">Нет</span><span class="sxs-lookup"><span data-stu-id="5ca77-122">No</span></span>  <br/> |<span data-ttu-id="5ca77-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5ca77-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="5ca77-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="5ca77-125">Да</span><span class="sxs-lookup"><span data-stu-id="5ca77-125">Yes</span></span>  <br/> |<span data-ttu-id="5ca77-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="5ca77-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="5ca77-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="5ca77-128">Нет</span><span class="sxs-lookup"><span data-stu-id="5ca77-128">No</span></span>  <br/> |<span data-ttu-id="5ca77-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="5ca77-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="5ca77-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="5ca77-131">Да</span><span class="sxs-lookup"><span data-stu-id="5ca77-131">Yes</span></span>  <br/> |<span data-ttu-id="5ca77-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="5ca77-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-133">Только в локальной среде</span><span class="sxs-lookup"><span data-stu-id="5ca77-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="5ca77-134">Нет</span><span class="sxs-lookup"><span data-stu-id="5ca77-134">No</span></span>  <br/> |<span data-ttu-id="5ca77-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="5ca77-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="5ca77-136">Только в локальной среде</span><span class="sxs-lookup"><span data-stu-id="5ca77-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="5ca77-137">Да</span><span class="sxs-lookup"><span data-stu-id="5ca77-137">Yes</span></span>  <br/> |<span data-ttu-id="5ca77-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="5ca77-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="5ca77-139">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5ca77-139">Related topics</span></span>
[<span data-ttu-id="5ca77-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5ca77-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5ca77-141">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5ca77-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

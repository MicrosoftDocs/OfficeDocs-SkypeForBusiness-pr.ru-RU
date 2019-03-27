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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Веб-приложение Outlook в Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365. Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально. Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app.
ms.openlocfilehash: 0d98d2490510b54ec0aabd4fefb7ed4137b449b7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891040"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="09d97-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="09d97-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="09d97-107">[] Веб-приложение Outlook в Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="09d97-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="09d97-108">Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="09d97-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="09d97-109">Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально.</span><span class="sxs-lookup"><span data-stu-id="09d97-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="09d97-110">Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="09d97-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="09d97-111">В следующей таблице перечислены различные параметры настройки, которые могут иметь и веб-клиент, который используется.</span><span class="sxs-lookup"><span data-stu-id="09d97-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="09d97-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="09d97-112">**User account is located**</span></span> <br/> |<span data-ttu-id="09d97-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="09d97-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="09d97-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="09d97-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="09d97-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="09d97-115">Online</span></span>  <br/> |<span data-ttu-id="09d97-116">Нет</span><span class="sxs-lookup"><span data-stu-id="09d97-116">No</span></span>  <br/> |<span data-ttu-id="09d97-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09d97-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="09d97-118">Online</span></span>  <br/> |<span data-ttu-id="09d97-119">Да</span><span class="sxs-lookup"><span data-stu-id="09d97-119">Yes</span></span>  <br/> |<span data-ttu-id="09d97-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09d97-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="09d97-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="09d97-122">Нет</span><span class="sxs-lookup"><span data-stu-id="09d97-122">No</span></span>  <br/> |<span data-ttu-id="09d97-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09d97-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="09d97-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="09d97-125">Да</span><span class="sxs-lookup"><span data-stu-id="09d97-125">Yes</span></span>  <br/> |<span data-ttu-id="09d97-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09d97-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="09d97-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="09d97-128">Нет</span><span class="sxs-lookup"><span data-stu-id="09d97-128">No</span></span>  <br/> |<span data-ttu-id="09d97-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09d97-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="09d97-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="09d97-131">Да</span><span class="sxs-lookup"><span data-stu-id="09d97-131">Yes</span></span>  <br/> |<span data-ttu-id="09d97-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09d97-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-133">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="09d97-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="09d97-134">Нет</span><span class="sxs-lookup"><span data-stu-id="09d97-134">No</span></span>  <br/> |<span data-ttu-id="09d97-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09d97-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="09d97-136">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="09d97-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="09d97-137">Да</span><span class="sxs-lookup"><span data-stu-id="09d97-137">Yes</span></span>  <br/> |<span data-ttu-id="09d97-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="09d97-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="09d97-139">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="09d97-139">Related topics</span></span>
[<span data-ttu-id="09d97-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="09d97-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="09d97-141">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="09d97-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 

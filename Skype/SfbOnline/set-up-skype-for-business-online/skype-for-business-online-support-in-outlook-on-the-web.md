---
title: "Поддержка Skype для бизнеса Online в веб-приложении Outlook"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: "Веб-приложение Outlook в Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации. Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365. Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально. Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app."
ms.openlocfilehash: 153cf2599afdd6961126307ca2b5f88fcff3f6fd
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="24078-106">Поддержка Skype для бизнеса Online в веб-приложении Outlook</span><span class="sxs-lookup"><span data-stu-id="24078-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="24078-107">Веб-приложение Outlook в Office 365 предлагает базовый веб-клиент Skype для бизнеса на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="24078-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="24078-108">Этот базовый клиент доступна для пользователей Online которого администратор еще не настроены запоминающиеся URL-адрес для своей организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="24078-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="24078-109">Поскольку учетная запись пользователя находится в сети, не имеет запоминающиеся URL-адрес, он будет по-прежнему видеть взаимодействия пользователя со даже в том случае, если их организации есть некоторые учетные записи пользователей, которые являются, размещенные локально.</span><span class="sxs-lookup"><span data-stu-id="24078-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="24078-110">Пользователи, у пользователя учетные записи в локальной (есть ли у них запоминающиеся URL-адрес или нет) или управляют Microsoft будут видеть взаимодействия Lync в Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="24078-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="24078-111">В следующей таблице перечислены различные параметры настройки, которые могут иметь и веб-клиент, который используется.</span><span class="sxs-lookup"><span data-stu-id="24078-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="24078-112">**Учетная запись пользователя находится**</span><span class="sxs-lookup"><span data-stu-id="24078-112">**User account is located**</span></span> <br/> |<span data-ttu-id="24078-113">**Запоминающийся URL-адрес настроен, или существует выделенная организация**</span><span class="sxs-lookup"><span data-stu-id="24078-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="24078-114">**Интерфейс Skype для бизнеса или Lync?**</span><span class="sxs-lookup"><span data-stu-id="24078-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="24078-115">В Интернете</span><span class="sxs-lookup"><span data-stu-id="24078-115">Online</span></span>  <br/> |<span data-ttu-id="24078-116">Нет</span><span class="sxs-lookup"><span data-stu-id="24078-116">No</span></span>  <br/> |<span data-ttu-id="24078-117">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="24078-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="24078-118">В Интернете</span><span class="sxs-lookup"><span data-stu-id="24078-118">Online</span></span>  <br/> |<span data-ttu-id="24078-119">Да</span><span class="sxs-lookup"><span data-stu-id="24078-119">Yes</span></span>  <br/> |<span data-ttu-id="24078-120">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="24078-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="24078-121">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="24078-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="24078-122">Нет</span><span class="sxs-lookup"><span data-stu-id="24078-122">No</span></span>  <br/> |<span data-ttu-id="24078-123">Веб-интерфейс Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="24078-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="24078-124">Гибридное, но находится в сети</span><span class="sxs-lookup"><span data-stu-id="24078-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="24078-125">Да</span><span class="sxs-lookup"><span data-stu-id="24078-125">Yes</span></span>  <br/> |<span data-ttu-id="24078-126">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="24078-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="24078-127">Гибридное, но размещено локально</span><span class="sxs-lookup"><span data-stu-id="24078-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="24078-128">Нет</span><span class="sxs-lookup"><span data-stu-id="24078-128">No</span></span>  <br/> |<span data-ttu-id="24078-129">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="24078-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="24078-130">Гибридное, но размещено локальное</span><span class="sxs-lookup"><span data-stu-id="24078-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="24078-131">Да</span><span class="sxs-lookup"><span data-stu-id="24078-131">Yes</span></span>  <br/> |<span data-ttu-id="24078-132">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="24078-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="24078-133">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="24078-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="24078-134">Нет</span><span class="sxs-lookup"><span data-stu-id="24078-134">No</span></span>  <br/> |<span data-ttu-id="24078-135">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="24078-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="24078-136">Чистая на prem</span><span class="sxs-lookup"><span data-stu-id="24078-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="24078-137">Да</span><span class="sxs-lookup"><span data-stu-id="24078-137">Yes</span></span>  <br/> |<span data-ttu-id="24078-138">Веб-интерфейс Lync</span><span class="sxs-lookup"><span data-stu-id="24078-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="24078-139">See also</span><span class="sxs-lookup"><span data-stu-id="24078-139">Related topics</span></span>
[<span data-ttu-id="24078-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="24078-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="24078-141">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="24078-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="24078-142">Отзыв?</span><span class="sxs-lookup"><span data-stu-id="24078-142">Feedback?</span></span>
<span data-ttu-id="24078-143">Для предоставления продукта свои отзывы и предложения или сообщите нам знать, как в нашем [Скайп для бизнеса свои отзывы и предложения](https://www.skypefeedback.com)см.</span><span class="sxs-lookup"><span data-stu-id="24078-143">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
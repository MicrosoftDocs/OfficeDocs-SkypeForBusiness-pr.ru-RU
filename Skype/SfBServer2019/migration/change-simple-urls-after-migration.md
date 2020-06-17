---
title: Изменение простых URL-адресов после миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype для бизнеса Server поддерживает простые URL-адреса.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753909"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="ac751-103">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="ac751-103">Change simple URLs after migration</span></span>

<span data-ttu-id="ac751-104">Skype для бизнеса Server поддерживает три простых URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="ac751-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="ac751-105">**Meet** is used as the base URL for all conferences in the site or organization.</span><span class="sxs-lookup"><span data-stu-id="ac751-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="ac751-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span><span class="sxs-lookup"><span data-stu-id="ac751-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="ac751-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span><span class="sxs-lookup"><span data-stu-id="ac751-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="ac751-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span><span class="sxs-lookup"><span data-stu-id="ac751-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="ac751-109">**Администратор** обеспечивает быстрый доступ к панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ac751-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ac751-110">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="ac751-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="ac751-111">После перехода на Skype для бизнеса Server необходимо знать, как это изменение влияет на записи DNS и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="ac751-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="ac751-112">Если устаревший директор Skype для бизнеса Server не используется в топологии, изменения простых URL-адресов не требуются.</span><span class="sxs-lookup"><span data-stu-id="ac751-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="ac751-113">Если директор Skype для бизнеса Server удален из топологии после миграции, DNS-записи простых URL-адресов необходимо обновить, чтобы указать один из пулов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ac751-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="ac751-114">Однако при любом изменении простого URL-адреса вам необходимо выполнить командлет Enable-CsComputer на каждом Директоре и сервере переднего плана, чтобы зарегистрировать это изменение.</span><span class="sxs-lookup"><span data-stu-id="ac751-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="ac751-115">Обновление простого URL-адреса собраний</span><span class="sxs-lookup"><span data-stu-id="ac751-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="ac751-116">В построителе топологий щелкните правой кнопкой мыши верхний узел в **Skype для бизнеса Server**, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ac751-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ac751-117">В левой области выберите **простые URL** -адреса, а затем в разделе URL **-адреса собраний:** выберите URL-адрес соответствия, а затем щелкните **изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="ac751-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="ac751-118">Задайте для URL-адреса требуемое значение и нажмите кнопку **ОК**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="ac751-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="ac751-119">Обновление простого URL-адреса администратора</span><span class="sxs-lookup"><span data-stu-id="ac751-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="ac751-120">В построителе топологий щелкните правой кнопкой мыши верхний узел в **Skype для бизнеса Server**, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ac751-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ac751-121">Выберите **простые URL-адреса** в левой области, а затем в поле **URL-адрес административного доступа** введите простой URL-адрес, который требуется использовать для административного доступа к панели управления Skype для бизнеса Server, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac751-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="ac751-122">Рекомендуется использовать самый простой URL-адрес для административного доступа.</span><span class="sxs-lookup"><span data-stu-id="ac751-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="ac751-123">Самый простой вариант — https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="ac751-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ac751-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ac751-124">See also</span></span>

[<span data-ttu-id="ac751-125">Требования DNS для простых URL-адресов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ac751-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)

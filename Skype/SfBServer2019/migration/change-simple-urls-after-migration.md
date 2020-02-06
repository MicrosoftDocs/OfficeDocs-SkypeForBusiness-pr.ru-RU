---
title: Изменение простых URL-адресов после миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype для бизнеса Server поддерживает простые URL-адреса.
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813887"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="54513-103">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="54513-103">Change simple URLs after migration</span></span>

<span data-ttu-id="54513-104">Skype для бизнеса Server поддерживает три простых URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="54513-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="54513-105">" **Встреча** " используется в качестве базового URL-адреса для всех конференций на сайте или в Организации.</span><span class="sxs-lookup"><span data-stu-id="54513-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="54513-106">С помощью простого URL-адреса вы можете легко усвоеновать ссылки на собрания, а также легко и распространены.</span><span class="sxs-lookup"><span data-stu-id="54513-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="54513-107">С помощью **телефонного подключения** можно получить доступ к веб-странице параметров конференций с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="54513-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="54513-108">Простой URL-адрес телефонного подключения включается во все приглашения на собрания. Таким образом пользователи, которые хотят подключиться к собранию по телефону, могут найти в нем необходимый номер телефона и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="54513-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="54513-109">**Простой URL-адрес администратора** обеспечивает быстрый доступ к панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="54513-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="54513-110">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="54513-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="54513-111">После перехода на сервер Skype для бизнеса необходимо учитывать, как это изменение влияет на записи DNS и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="54513-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="54513-112">Если стандартный режиссер сервера Skype для бизнеса не используется в топологии, никаких изменений в простых URL-адресах не требуется.</span><span class="sxs-lookup"><span data-stu-id="54513-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="54513-113">Если после миграции служба режиссера сервера Skype для бизнеса удалена из топологии, для нее нужно обновить простые URL-записи, чтобы они указывали на один из пулов сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="54513-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="54513-114">Однако каждый раз, когда вы изменяете простое имя URL-адреса, вы должны выполнить команду Enable-Кскомпутер для каждого директора и сервера переднего плана для регистрации изменения.</span><span class="sxs-lookup"><span data-stu-id="54513-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="54513-115">Обновление простого URL-адреса для собрания</span><span class="sxs-lookup"><span data-stu-id="54513-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="54513-116">В построителе топологии щелкните правой кнопкой мыши верхний узел в **Skype для бизнеса Server**и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="54513-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="54513-117">В левой области выберите **простые URL** -адреса, а затем — URL-адреса для **собраний:** выберите в поле "адрес для собрания" и нажмите кнопку **изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="54513-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="54513-118">Установите для URL-адреса нужное значение и нажмите кнопку **ОК**, чтобы сохранить измененный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="54513-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="54513-119">Обновление простого URL-адреса администратора</span><span class="sxs-lookup"><span data-stu-id="54513-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="54513-120">В построителе топологии щелкните правой кнопкой мыши верхний узел в **Skype для бизнеса Server**и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="54513-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="54513-121">Выберите **простые URL-адреса** в левой области, а затем в поле **URL-адрес администратора** введите простой URL-адрес, который вы хотите использовать для административного доступа к панели управления "Skype для бизнеса Server", а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="54513-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="54513-122">В качестве URL-адреса администрирования рекомендуется использовать максимально простой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="54513-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="54513-123">Это https://adminсамый простой вариант. <em>Domain (домен\>). \<</em></span><span class="sxs-lookup"><span data-stu-id="54513-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="54513-124">См. также</span><span class="sxs-lookup"><span data-stu-id="54513-124">See also</span></span>

[<span data-ttu-id="54513-125">Требования к DNS для простых URL-адресов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="54513-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)

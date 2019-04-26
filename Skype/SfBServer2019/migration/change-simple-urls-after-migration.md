---
title: Изменение простых URL-адресов после миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Скайп для Business Server поддерживает простых URL-адресов.
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238753"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="90d4c-103">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="90d4c-103">Change simple URLs after migration</span></span>

<span data-ttu-id="90d4c-104">Скайп для Business Server поддерживает три простых URL-адресов:</span><span class="sxs-lookup"><span data-stu-id="90d4c-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="90d4c-105">**Провести** используется как базовый URL-адрес для всех конференций в веб-сайта или организации.</span><span class="sxs-lookup"><span data-stu-id="90d4c-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="90d4c-106">Meet простых URL-адрес ссылки на присоединение к собраниям более понятными и удобными для обмена и распространения.</span><span class="sxs-lookup"><span data-stu-id="90d4c-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="90d4c-107">**-Связи** обеспечивает доступ к веб-странице параметров конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="90d4c-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="90d4c-108">-Связи простых URL-адрес включен в все приглашения на собрания, чтобы пользователи, которым необходим для присоединения к собранию могут использовать необходимые телефонный номер и ПИН-код информацию.</span><span class="sxs-lookup"><span data-stu-id="90d4c-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="90d4c-109">**Admin** позволяет быстро получить доступ к Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="90d4c-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="90d4c-110">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="90d4c-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="90d4c-111">После миграции в Скайп for Business Server, необходимо знать о том, как изменить влияет на DNS-записей и сертификатов для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="90d4c-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="90d4c-112">Если Скайп прежних версий для директоров Business Server остается используемых в топологии, для простых URL-адреса не требуется.</span><span class="sxs-lookup"><span data-stu-id="90d4c-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="90d4c-113">Если Скайп для директоров Business Server удаляется из топологии после миграции, необходимо обновить простых URL-адреса DNS-записей для указания на один из Скайп для пулов Business Server.</span><span class="sxs-lookup"><span data-stu-id="90d4c-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="90d4c-114">При любом изменении простого URL-адреса, тем не менее, необходимо выполнить командлет Enable-CsComputer на каждом директора и сервера переднего плана, чтобы зарегистрировать это изменение.</span><span class="sxs-lookup"><span data-stu-id="90d4c-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="90d4c-115">Обновление собраний простых URL-адреса</span><span class="sxs-lookup"><span data-stu-id="90d4c-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="90d4c-116">В построителе топологий щелкните правой кнопкой мыши верхний узел **Скайп для Business Server**и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="90d4c-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="90d4c-117">Затем установите **Простых URL-адресов** в области слева под **URL-адреса собрания:** выберите URL-адрес собраний и нажмите кнопку **Изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="90d4c-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="90d4c-118">Установите для URL-адреса нужное значение и нажмите кнопку **ОК**, чтобы сохранить измененный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="90d4c-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="90d4c-119">Обновление простого URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="90d4c-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="90d4c-120">В построителе топологий щелкните правой кнопкой мыши верхний узел **Скайп для Business Server**и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="90d4c-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="90d4c-121">Установите **Простых URL-адресов** в области слева выберите ниже поле **URL-адрес административного доступа** введите простой URL-адрес для административного доступа к Скайп для панели управления Business Server и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="90d4c-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="90d4c-122">В качестве URL-адреса администрирования рекомендуется использовать максимально простой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="90d4c-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="90d4c-123">— Это самый простой вариант https://admin. <em> \<домена\></em>.</span><span class="sxs-lookup"><span data-stu-id="90d4c-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="90d4c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="90d4c-124">See also</span></span>

[<span data-ttu-id="90d4c-125">Требования DNS для простых URL-адресов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="90d4c-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)

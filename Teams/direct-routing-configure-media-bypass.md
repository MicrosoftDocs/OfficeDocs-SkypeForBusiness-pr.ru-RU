---
title: Настройка сервера-посредника при прямой маршрутизации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Прочтите этот раздел, чтобы узнать, как настроить обход сервера-посредника при прямой маршрутизации телефонной системы.
ms.openlocfilehash: 405f71fd0a1e0ea3e8fec6ee1061786c93fabf1b
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631078"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="2122c-103">Настройка сервера-посредника при прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2122c-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="2122c-104">До настройки обхода медиаданных при прямой маршрутизации, убедитесь, что вы прочли [Планирование мультимедиа обходить при прямой маршрутизации](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="2122c-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="2122c-105">Чтобы включить обход сервера-посредника, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="2122c-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="2122c-106">Убедитесь в том, что поставщик пограничный контроллер сеансов (SBC) выбора поддерживает обход сервера-посредника и предоставляет инструкции по настройке обхода для SBC.</span><span class="sxs-lookup"><span data-stu-id="2122c-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="2122c-107">Обратитесь к сертификации страницы, чтобы узнать о их изготовителей, какие области поддержки сервера-посредника, а также инструкции.</span><span class="sxs-lookup"><span data-stu-id="2122c-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="2122c-108">Необходимо включить обход сервера-посредника на линии связи, с помощью следующей команды: **Set CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="2122c-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="2122c-109">Убедитесь в том, что открыты необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="2122c-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="2122c-110">Переход от магистральных линий связи не применяется к магистрали с поддержкой веб-сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="2122c-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="2122c-111">Возможность переключать всех пользователей одновременно или вы можете реализовать поэтапный достижении (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="2122c-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="2122c-112">**Переключение всех пользователей одновременно.**</span><span class="sxs-lookup"><span data-stu-id="2122c-112">**Switch all users at once.**</span></span> <span data-ttu-id="2122c-113">Если все условия, можно включить режим обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="2122c-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="2122c-114">Тем не менее все пользователи рабочей переключается в то же время.</span><span class="sxs-lookup"><span data-stu-id="2122c-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="2122c-115">Так как некоторые проблемы могут возникнуть изначально при настройке магистральных линий связи и порты, может повлиять на взаимодействие с пользователем рабочей.</span><span class="sxs-lookup"><span data-stu-id="2122c-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="2122c-116">Подход **Phased. (Рекомендуется)**.</span><span class="sxs-lookup"><span data-stu-id="2122c-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="2122c-117">Создание новой линии связи для одной SBC (с другой порт) и проверить его изменить политику маршрутизации online голосовой связи для пользователей для указания на новой магистрали.</span><span class="sxs-lookup"><span data-stu-id="2122c-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="2122c-118">Это рекомендуемый подход, поскольку он обеспечивает плавный переход и бесперебойный пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2122c-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="2122c-119">Такой подход необходимо настроить пограничный контроллер Сеансов, новое имя полного доменного ИМЕНИ и настройки брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="2122c-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="2122c-120">Обратите внимание, что вам понадобится убедитесь в том, что сертификат поддерживает оба магистральных линий связи.</span><span class="sxs-lookup"><span data-stu-id="2122c-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="2122c-121">В сети хранения данных необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или иметь групповой сертификат.</span><span class="sxs-lookup"><span data-stu-id="2122c-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Перенос из магистральных линий связи не применяется в магистралей с поддержкой веб-сервера-посредника)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="2122c-123">Инструкции по настройке магистралях и выполнение миграции обратитесь к документации от поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="2122c-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="2122c-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2122c-124">AudioCodes</span></span>
- <span data-ttu-id="2122c-125">Лента</span><span class="sxs-lookup"><span data-stu-id="2122c-125">Ribbon</span></span>
- <span data-ttu-id="2122c-126">TE-систем (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="2122c-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="2122c-127">В настоящее время данное сообщение полностью протестированные и сертифицированные для работы с обходом сервера-посредника следующие их изготовителей:</span><span class="sxs-lookup"><span data-stu-id="2122c-127">At the moment of this announcement, the following SBCs are fully tested and certified to work with media bypass:</span></span>

- <span data-ttu-id="2122c-128">V7.20A.204.222 9000 AudioCodes, AudioCodes M800B-SBC / V7.20A.250.003</span><span class="sxs-lookup"><span data-stu-id="2122c-128">AudioCodes 9000 V7.20A.204.222, AudioCodes M800B-SBC/ V7.20A.250.003</span></span>

-   <span data-ttu-id="2122c-129">Лента</span><span class="sxs-lookup"><span data-stu-id="2122c-129">Ribbon</span></span>
    - <span data-ttu-id="2122c-130">5210 v06.02.xx-xxx</span><span class="sxs-lookup"><span data-stu-id="2122c-130">5210 v06.02.xx-xxx</span></span> 
    - <span data-ttu-id="2122c-131">5400, v06.02.xx-xxx</span><span class="sxs-lookup"><span data-stu-id="2122c-131">5400, v06.02.xx-xxx</span></span>
    - <span data-ttu-id="2122c-132">5110, v06.02.xx-xxx</span><span class="sxs-lookup"><span data-stu-id="2122c-132">5110, v06.02.xx-xxx</span></span>

-   <span data-ttu-id="2122c-133">V TE системы AnyNode 3.16.2</span><span class="sxs-lookup"><span data-stu-id="2122c-133">TE-System AnyNode v 3.16.2</span></span> 


## <a name="see-also"></a><span data-ttu-id="2122c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2122c-134">See also</span></span>

[<span data-ttu-id="2122c-135">Планирование сервера-посредника при прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2122c-135">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)




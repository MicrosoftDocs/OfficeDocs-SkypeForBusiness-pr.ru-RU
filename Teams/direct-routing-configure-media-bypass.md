---
title: Настройка обхода сервера-посредника с прямой маршрутизацией
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
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232699"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="d46b6-103">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="d46b6-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="d46b6-104">До настройки обхода медиаданных при прямой маршрутизации, убедитесь, что вы прочли [Планирование мультимедиа обходить при прямой маршрутизации](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="d46b6-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="d46b6-105">Чтобы включить обход сервера-посредника, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="d46b6-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="d46b6-106">Убедитесь в том, что поставщик пограничный контроллер сеансов (SBC) выбора поддерживает обход сервера-посредника и предоставляет инструкции по настройке обхода для SBC.</span><span class="sxs-lookup"><span data-stu-id="d46b6-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="d46b6-107">Обратитесь к сертификации страницы, чтобы узнать о их изготовителей, какие области поддержки сервера-посредника, а также инструкции.</span><span class="sxs-lookup"><span data-stu-id="d46b6-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="d46b6-108">Необходимо включить обход сервера-посредника на линии связи, с помощью следующей команды: **Set CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="d46b6-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="d46b6-109">Убедитесь в том, что открыты необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="d46b6-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="d46b6-110">Переход от магистральных линий связи не применяется к магистрали с поддержкой веб-сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="d46b6-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="d46b6-111">Возможность переключать всех пользователей одновременно или вы можете реализовать поэтапный достижении (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="d46b6-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="d46b6-112">**Переключение всех пользователей одновременно.**</span><span class="sxs-lookup"><span data-stu-id="d46b6-112">**Switch all users at once.**</span></span> <span data-ttu-id="d46b6-113">Если все условия, можно включить режим обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d46b6-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="d46b6-114">Тем не менее все пользователи рабочей переключается в то же время.</span><span class="sxs-lookup"><span data-stu-id="d46b6-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="d46b6-115">Так как некоторые проблемы могут возникнуть изначально при настройке магистральных линий связи и порты, может повлиять на взаимодействие с пользователем рабочей.</span><span class="sxs-lookup"><span data-stu-id="d46b6-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="d46b6-116">Подход **Phased. (Рекомендуется)**.</span><span class="sxs-lookup"><span data-stu-id="d46b6-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="d46b6-117">Создание новой линии связи для одной SBC (с другой порт) и проверить его изменить политику маршрутизации online голосовой связи для пользователей для указания на новой магистрали.</span><span class="sxs-lookup"><span data-stu-id="d46b6-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="d46b6-118">Это рекомендуемый подход, поскольку он обеспечивает плавный переход и бесперебойный пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d46b6-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="d46b6-119">Такой подход необходимо настроить пограничный контроллер Сеансов, новое имя полного доменного ИМЕНИ и настройки брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="d46b6-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="d46b6-120">Обратите внимание, что вам понадобится убедитесь в том, что сертификат поддерживает оба магистральных линий связи.</span><span class="sxs-lookup"><span data-stu-id="d46b6-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="d46b6-121">В сети хранения данных необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или иметь групповой сертификат.</span><span class="sxs-lookup"><span data-stu-id="d46b6-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Перенос из магистральных линий связи не применяется в магистралей с поддержкой веб-сервера-посредника)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="d46b6-123">Инструкции по настройке магистралях и выполнение миграции обратитесь к документации от поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="d46b6-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="d46b6-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d46b6-124">AudioCodes</span></span>
- <span data-ttu-id="d46b6-125">Лента</span><span class="sxs-lookup"><span data-stu-id="d46b6-125">Ribbon</span></span>
- <span data-ttu-id="d46b6-126">TE-систем (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="d46b6-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="d46b6-127">Список пограничных контроллеров сеансов (SBC) сертифицированный для прямой маршрутизации в разделе [список из сеанса Broder контроллеры сертифицированный для прямой маршрутизации](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="d46b6-127">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="d46b6-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d46b6-128">See also</span></span>

[<span data-ttu-id="d46b6-129">Планирование сервера-посредника при прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="d46b6-129">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)




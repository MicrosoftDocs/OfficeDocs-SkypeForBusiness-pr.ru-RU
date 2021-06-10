---
title: Настройка обхода сервера-посредника с прямой маршрутизацией
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как настроить обход мультимедиа с помощью телефонная система прямой маршрутии для Microsoft Teams путем одновременного переключения всех пользователей или поэтапной реализации (рекомендуется).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416899"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="c8877-103">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="c8877-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="c8877-104">Перед настройкой обхода мультимедиа при прямой маршрутике убедитесь, что у вас есть прочитать статью Планирование обхода мультимедиа [с прямой маршрутией.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="c8877-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="c8877-105">Чтобы включить обход мультимедиа, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="c8877-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="c8877-106">Убедитесь, что поставщик SBC поддерживает обход мультимедиа и предоставляет инструкции по настройке обхода на SBC.</span><span class="sxs-lookup"><span data-stu-id="c8877-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="c8877-107">На странице сертификации вы узнаете, какие из них поддерживают обход мультимедиа, и инструкции.</span><span class="sxs-lookup"><span data-stu-id="c8877-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="c8877-108">Чтобы включить обход мультимедиа на линии, следуйте следующей команде: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**</span><span class="sxs-lookup"><span data-stu-id="c8877-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="c8877-109">Убедитесь, что открыты необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="c8877-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="c8877-110">Переход с невключаемой туловища на обойденные.</span><span class="sxs-lookup"><span data-stu-id="c8877-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="c8877-111">Вы можете переключить всех пользователей одновременно или реализовать поэтапный подход (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="c8877-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="c8877-112">**Одновременное переключение всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="c8877-112">**Switch all users at once.**</span></span> <span data-ttu-id="c8877-113">Если выполнены все условия, вы можете включить режим обхода.</span><span class="sxs-lookup"><span data-stu-id="c8877-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="c8877-114">Однако все ваши производственные пользователи будут переключаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="c8877-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="c8877-115">Так как первоначально при настройке связи и портов могут возникнуть некоторые проблемы, это может повлиять на пользовательский интерфейс вашей компании.</span><span class="sxs-lookup"><span data-stu-id="c8877-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="c8877-116">**Поэтапный подход. (Рекомендуется)**.</span><span class="sxs-lookup"><span data-stu-id="c8877-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="c8877-117">Создайте новую магистраль для того же SBC (с другим портом), протестировать ее и измените политику маршрутинга голосовой связи в Интернете, чтобы пользователи навести указатель на новую туловище.</span><span class="sxs-lookup"><span data-stu-id="c8877-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="c8877-118">Это рекомендуемый подход, так как он обеспечивает более плавный переход и непрерывный пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c8877-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="c8877-119">Для этого подхода требуется конфигурация SBC, новое имя FQDN и конфигурация брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="c8877-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="c8877-120">Обратите внимание, что сертификат должен поддерживать обе стороны.</span><span class="sxs-lookup"><span data-stu-id="c8877-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="c8877-121">В САН у вас должны быть два имена **(sbc1.contoso.com** и **sbc2.contoso.com**) или поддиз.сертификат.</span><span class="sxs-lookup"><span data-stu-id="c8877-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Переход с неинтегрирования на обойденные магистрали)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="c8877-123">Инструкции по настройке магистральных телефонов и выполнению миграции см. в документации поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="c8877-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="c8877-124">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="c8877-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="c8877-125">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="c8877-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="c8877-126">Документация по развертыванию коммуникаций на ленте</span><span class="sxs-lookup"><span data-stu-id="c8877-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="c8877-127">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="c8877-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="c8877-128">Список SBCs, сертифицированных для прямой маршрутики, см. в списке Контроллеров приобринга сеанса, сертифицированных для прямой [маршрутики.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="c8877-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="c8877-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c8877-129">Related topics</span></span>

[<span data-ttu-id="c8877-130">Планирование обхода мультимедиа с помощью прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="c8877-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)




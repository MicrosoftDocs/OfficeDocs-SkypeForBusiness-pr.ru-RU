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
description: В этой статье объясняется, как настроить обход мультимедиа с прямой маршрутизацией на телефонную систему для Microsoft Teams, переключив всех пользователей за один раз или реализовав поэтапный подход (рекомендуется).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416899"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="86501-103">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="86501-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="86501-104">Перед настройкой обхода мультимедиа с помощью прямой маршрутизации убедитесь, что у вас есть [план обхода мультимедийных файлов с прямой маршрутизацией](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="86501-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="86501-105">Чтобы включить обход мультимедиа, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="86501-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="86501-106">Убедитесь в том, что вендором, используемым для выбора вашего сеанса связи (SBC), поддерживается обход мультимедиа, и инструкции по настройке параметров "пропустить" для SBC.</span><span class="sxs-lookup"><span data-stu-id="86501-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="86501-107">Ознакомьтесь со статьей "сертификация", чтобы узнать о том, какие из них поддерживают обход мультимедиа, а также о каких-либо инструкциях.</span><span class="sxs-lookup"><span data-stu-id="86501-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="86501-108">Необходимо включить обход мультимедиа на магистральной сети с помощью следующей команды: **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="86501-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="86501-109">Убедитесь в том, что нужные порты открыты.</span><span class="sxs-lookup"><span data-stu-id="86501-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="86501-110">Переход с необходных каналов на магистральные и недоступные для обхода</span><span class="sxs-lookup"><span data-stu-id="86501-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="86501-111">Вы можете переключить всех пользователей за один раз или реализовать поэтапный подход (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="86501-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="86501-112">**Одновременное переключение всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="86501-112">**Switch all users at once.**</span></span> <span data-ttu-id="86501-113">Если все условия выполнены, вы можете включить режим обхода.</span><span class="sxs-lookup"><span data-stu-id="86501-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="86501-114">Однако все ваши производственные пользователи будут переключаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="86501-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="86501-115">Из-за того, что при настройке магистральных каналов и портов могут возникнуть некоторые проблемы, это может повлиять на работу пользователя.</span><span class="sxs-lookup"><span data-stu-id="86501-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="86501-116">**Поэтапный подход. (Рекомендуемый вариант)**.</span><span class="sxs-lookup"><span data-stu-id="86501-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="86501-117">Создание новой магистрали для одного и того же SBC (с другим портом), проверка и изменение политики голосовой маршрутизации в сети для пользователей, чтобы они указывали на новую магистраль.</span><span class="sxs-lookup"><span data-stu-id="86501-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="86501-118">Этот подход является рекомендуемым, так как он обеспечивает более плавный переход и бесперебойную работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="86501-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="86501-119">Этот подход требует настройки SBC, нового полного доменного имени и конфигурации брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="86501-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="86501-120">Примечание. необходимо убедиться, что ваш сертификат поддерживает обе магистральные линии.</span><span class="sxs-lookup"><span data-stu-id="86501-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="86501-121">В сети SAN необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или использовать подстановочный сертификат.</span><span class="sxs-lookup"><span data-stu-id="86501-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Переход с необходных каналов в магистральы с поддержкой обхода](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="86501-123">Инструкции по настройке магистральных каналов и выполнению миграции можно найти в документации, предоставленной поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="86501-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="86501-124">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="86501-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="86501-125">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="86501-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="86501-126">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="86501-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="86501-127">Документация по развертыванию системы TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="86501-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="86501-128">Список контроллеров границ сеансов (SBCs), сертифицированных для прямой маршрутизации, можно найти в разделе [список контроллеров границами сеансов, сертифицированных для прямой маршрутизации](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="86501-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="86501-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="86501-129">Related topics</span></span>

[<span data-ttu-id="86501-130">Планирование обхода мультимедиа с помощью прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="86501-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)




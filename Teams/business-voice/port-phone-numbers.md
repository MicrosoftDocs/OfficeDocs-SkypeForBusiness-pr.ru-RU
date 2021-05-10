---
title: Перенос номеров телефонов в корпоративную голосовую связь
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Узнайте, как перенести существующие номера телефонов от текущего поставщика в Голосовую связь Microsoft 365 бизнес.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26f686197963f53f20477ccd9a16935c86a16d9f
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282616"
---
# <a name="step-7-port-phone-numbers-to-business-voice-optional"></a><span data-ttu-id="f42fa-103">Шаг 7. Перенос номеров телефонов в Голосовую связь Microsoft 365 бизнес (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f42fa-103">Step 7: Port phone numbers to Business Voice (optional)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f42fa-104">Сведения этой статьи применимы только к корпоративной голосовой связи **с** тарифным планом.</span><span class="sxs-lookup"><span data-stu-id="f42fa-104">The information in this article is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="f42fa-105">Корпоративная голосовая связь с тарифным планом доступна только в некоторых странах и регионах.</span><span class="sxs-lookup"><span data-stu-id="f42fa-105">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="f42fa-106">Перед прочтением этой статьи ознакомьтесь со статьей [Страны и регионы, в которых доступна корпоративная голосовая связь](country-region-availability.md), чтобы узнать, поддерживается ли в вашей стране или регионе корпоративная голосовая связь с тарифным планом.</span><span class="sxs-lookup"><span data-stu-id="f42fa-106">Before reading this article, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="f42fa-107">Если ваш клиент находится в стране или регионе, не поддерживающем корпоративную голосовую связь с тарифным планом, ознакомьтесь со статьей [Получение справки от торгового представителя или партнера Майкрософт](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="f42fa-107">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>

<span data-ttu-id="f42fa-108">Ранее в этом руководстве по настройке вы получили номера телефонов основной линии компании и всех пользователей, которым назначена лицензия на использование корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f42fa-108">Earlier in this setup guide, you acquired phone numbers for the main company line and for any users that you've assigned a Business Voice license to.</span></span> <span data-ttu-id="f42fa-109">**Если вы новое предприятие и у вас нет существующих номеров телефонов, которые вы хотите использовать в Голосовой связи Microsoft 365 бизнес, вы можете пропустить этот шаг.**</span><span class="sxs-lookup"><span data-stu-id="f42fa-109">**If you're a new business and don't have any existing phone numbers that you want to bring to Business Voice, you can skip this step.**</span></span>

<span data-ttu-id="f42fa-110">Если у вас уже есть номера телефонов, которые вы хотите сохранить при переходе на корпоративную голосовую связь, воспользуйтесь процессом переноса номеров телефонов, чтобы использовать их в корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f42fa-110">If you already have phone numbers that you want to keep when you move to Business Voice, you can bring them with you by using a process called phone number porting to bring them over to Business Voice.</span></span> <span data-ttu-id="f42fa-111">После переноса номеров в корпоративную голосовую связь нужно назначить их пользователям и службам.</span><span class="sxs-lookup"><span data-stu-id="f42fa-111">After you port your phone numbers to Business Voice, you assign them to users and services.</span></span> <span data-ttu-id="f42fa-112">Старые номера заменяют временные номера, полученные ранее в этом руководстве по настройке.</span><span class="sxs-lookup"><span data-stu-id="f42fa-112">The old numbers replace the temporary numbers that you acquired earlier in this setup guide.</span></span>

<span data-ttu-id="f42fa-113">Перед переносом номеров в корпоративную голосовую связь ознакомьтесь со статьей [Часто задаваемые вопросы о переносе номеров телефонов](../phone-number-calling-plans/port-order-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f42fa-113">Before you move numbers to Business Voice, take a look at [Transferring phone numbers common questions](../phone-number-calling-plans/port-order-overview.md).</span></span> <span data-ttu-id="f42fa-114">В этой статье приведены ответы на вопросы о том, в каких странах и регионах предоставляется поддержка, какие номера можно переносить и какие сведения вам понадобятся.</span><span class="sxs-lookup"><span data-stu-id="f42fa-114">This article includes answers to questions including what countries and regions are supported, what numbers can and can't be transferred, and what information you'll need.</span></span>

<span data-ttu-id="f42fa-115">Когда вы будете готовы перенести номера телефонов в корпоративную голосовую связь, выполните действия, описанные в статье [Перенос номеров телефонов в Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md), чтобы создать заказ на перенос номера.</span><span class="sxs-lookup"><span data-stu-id="f42fa-115">When you're ready to move your phone numbers to Business Voice, follow the steps in [Transfer phone numbers to Office 365](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to create a port order.</span></span> <span data-ttu-id="f42fa-116">Этот заказ включает необходимую информацию для переноса номера от текущего оператора телефонной службы в корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="f42fa-116">The order includes the information that's needed to move your numbers from your current phone service carrier to Business Voice.</span></span>

<span data-ttu-id="f42fa-117">После переноса номеров нужно назначить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="f42fa-117">After your phone numbers have been moved to Business Voice, you need to assign them to people.</span></span> <span data-ttu-id="f42fa-118">Для этого выполните действия, описанные в статье [Изменение номера телефона пользователя](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="f42fa-118">To do that, follow the steps in [Change a phone number for a user](../assign-change-or-remove-a-phone-number-for-a-user.md#change-a-phone-number-for-a-user).</span></span> <span data-ttu-id="f42fa-119">Выполнив эти действия, вы замените номер телефона, временно назначенный пользователю, его перенесенным первоначальным номером.</span><span class="sxs-lookup"><span data-stu-id="f42fa-119">When you follow these steps, you'll replace the phone number that was temporarily assigned to the user with their original phone number that you ported over.</span></span>

<span data-ttu-id="f42fa-120">Свяжитесь с нами, если вам понадобится помощь.</span><span class="sxs-lookup"><span data-stu-id="f42fa-120">If you need help, let us know!</span></span> <span data-ttu-id="f42fa-121">Мы поможем вам перенести номера телефонов в корпоративную голосовую связь без всяких проблем.</span><span class="sxs-lookup"><span data-stu-id="f42fa-121">We're here to help you get your phone numbers moved to Business Voice as easy as possible.</span></span> <span data-ttu-id="f42fa-122">Обязательно укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="f42fa-122">Be sure to include the following information:</span></span>

- <span data-ttu-id="f42fa-123">идентификатор вашей организации (например, ***contoso***.onmicrosoft.com);</span><span class="sxs-lookup"><span data-stu-id="f42fa-123">Your organization ID (such as ***contoso***.onmicrosoft.com)</span></span>
- <span data-ttu-id="f42fa-124">типы и количество номеров, с которыми требуется помощь;</span><span class="sxs-lookup"><span data-stu-id="f42fa-124">What types and how many numbers you need help with</span></span>
- <span data-ttu-id="f42fa-125">уполномоченное лицо в вашей учетной записи;</span><span class="sxs-lookup"><span data-stu-id="f42fa-125">The authorizing person on your account</span></span>
- <span data-ttu-id="f42fa-126">описание возникшей проблемы.</span><span class="sxs-lookup"><span data-stu-id="f42fa-126">A description of the issue or question that you have</span></span>

<span data-ttu-id="f42fa-127">Чтобы получить помощь с номерами телефонов в Канаде и США, отправьте запрос по адресу [ptn@microsoft.com](mailto:ptn@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f42fa-127">For help with phone numbers in Canada and the United States, send your request to [ptn@microsoft.com](mailto:ptn@microsoft.com).</span></span>

<span data-ttu-id="f42fa-128">Чтобы получить помощь с номерами телефонов в Европе, отправьте запрос по адресу [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f42fa-128">For help with phone numbers in Europe, send your request to [ptneu@microsoft.com](mailto:ptneu@microsoft.com).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f42fa-129">Следующий шаг: завершите настройку Голосовой связи Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="f42fa-129">Next step: Finish Business Voice setup</span></span>](set-up-finish.md)

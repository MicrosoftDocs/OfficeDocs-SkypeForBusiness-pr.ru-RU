---
title: Настройка Голосовая связь Microsoft 365 бизнес
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Узнайте, как настроить Голосовая связь Microsoft 365 бизнес для малого и среднего бизнеса или организации.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 892b093003accf782b7fb6c0a6234bf1f8beb952
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656042"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="29560-103">Настройка Голосовая связь Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="29560-103">Set up Microsoft 365 Business Voice</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEu8R]  

</br>

<span data-ttu-id="29560-104">Business Voice — это полная телефонная система, которая может заменить существующего поставщика телефонии.</span><span class="sxs-lookup"><span data-stu-id="29560-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="29560-105">Независимо от того, работаете ли вы в новой компании, настраивая номера телефонов в первый раз или переходим от устаревшего локального поставщика телефонии, с помощью действий, указанных в этих статьях, можно прибегать к бизнес-голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="29560-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="29560-106">Завершив настройку бизнес-голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="29560-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="29560-107">Вы сможете принимать платные и бесплатные телефонные звонки на основной телефонной линии компании.</span><span class="sxs-lookup"><span data-stu-id="29560-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="29560-108">При этом вы даже можете настроить меню звонка.</span><span class="sxs-lookup"><span data-stu-id="29560-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="29560-109">У пользователей, которые настроены с помощью бизнес-голосовой связи, будут собственные телефонные номера для прямого набора, которые они могут использовать для телефонных звонков с любого устройства, на Teams телефонов.</span><span class="sxs-lookup"><span data-stu-id="29560-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="29560-110">Участники собрания смогут присоединяться к собраниям с помощью обычного телефона, если не могут присоединиться с помощью Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="29560-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="29560-111">Если у вас уже есть номера телефонов, вы сможете продолжать использовать их после их перенаселя на business Voice.</span><span class="sxs-lookup"><span data-stu-id="29560-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="29560-112">Если вы хотите узнать больше о бизнес-голосовой информации, ознакомьтесь со [Голосовая связь Microsoft 365 бизнес.](whats-business-voice.md)</span><span class="sxs-lookup"><span data-stu-id="29560-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29560-113">Сведения в этих статьях применимы только к бизнес-голосовой связи **с планом** звонков.</span><span class="sxs-lookup"><span data-stu-id="29560-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="29560-114">Корпоративная голосовая связь с тарифным планом доступна только в некоторых странах и регионах.</span><span class="sxs-lookup"><span data-stu-id="29560-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="29560-115">Прежде чем приступить к [](country-region-availability.md) настройке бизнес-голосовой связи, проверьте, поддерживается ли в вашей стране или регионе деловая голосовая почта с планом звонков.</span><span class="sxs-lookup"><span data-stu-id="29560-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="29560-116">Если ваш клиент находится в стране или регионе, не поддерживающем корпоративную голосовую связь с тарифным планом, ознакомьтесь со статьей [Получение справки от торгового представителя или партнера Майкрософт](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="29560-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="29560-117">Microsoft Teams и корпоративная голосовая связь работает, только если почтовые ящики пользователей находятся в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29560-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="29560-118">Почтовые ящики, размещенные на локальном сервере Exchange Server, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="29560-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="29560-119">Этот процесс настройки не поддерживает Skype для бизнеса гибридных развертывании.</span><span class="sxs-lookup"><span data-stu-id="29560-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="29560-120">Если вы используете гибридное развертывание Skype для бизнеса и хотите настроить корпоративную голосовую связь, ознакомьтесь со статьей [Настройка телефонной системы в организации](../setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="29560-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="29560-121">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="29560-121">Before you begin</span></span>

<span data-ttu-id="29560-122">Перед началом работы с бизнес-голосовой почтой необходимо сделать несколько вещей.</span><span class="sxs-lookup"><span data-stu-id="29560-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="29560-123">В следующих задачах ваша организация должна быть готова к бизнес-голосовой голосовой функции.</span><span class="sxs-lookup"><span data-stu-id="29560-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="29560-124">**Приобретай лицензии на** голосовую связь для бизнеса и, если вы хотите получить бесплатный номер или сделать междугородние телефонные звонки, кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="29560-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="29560-125">Дополнительные сведения см. в [этой Голосовая связь Microsoft 365 бизнес.](what-to-buy.md)</span><span class="sxs-lookup"><span data-stu-id="29560-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="29560-126">**Убедитесь, что подключение к Интернету поддерживает бизнес-голос.**</span><span class="sxs-lookup"><span data-stu-id="29560-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="29560-127">Дополнительные сведения см. в [теме Проверка подключения к](get-ready-internet.md)Интернету для бизнеса Voice.</span><span class="sxs-lookup"><span data-stu-id="29560-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="29560-128">**Настройка Teams на устройствах** пользователей, настройка приветствий голосовой почты и помощь пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="29560-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="29560-129">Дополнительные сведения см. в [Голосовая связь Microsoft 365 бизнес.](prepare-users.md)</span><span class="sxs-lookup"><span data-stu-id="29560-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="29560-130">Подготовив организацию к бизнес-голосовой почте, выберите следующий **шаг: Начало настройки бизнес-голосовой почты**.</span><span class="sxs-lookup"><span data-stu-id="29560-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="29560-131">Следующий шаг: начало настройки бизнес-голосовой почты</span><span class="sxs-lookup"><span data-stu-id="29560-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)

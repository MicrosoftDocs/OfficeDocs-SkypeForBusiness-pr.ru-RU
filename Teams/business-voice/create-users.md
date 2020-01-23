---
title: Создание пользователей Microsoft 365, добавление лицензий на корпоративную голосовую связь и назначение номеров телефонов
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb8277c11cbcc459da9da8fd8d4f5b9c329470f3
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269285"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="30eb3-102">Создание пользователей, предоставление им лицензии на корпоративную голосовую связь и назначение им номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="30eb3-102">Create and license users and assign phone numbers to them</span></span>

<span data-ttu-id="30eb3-103">Чтобы использовать :::no-loc text="Microsoft 365 Business Voice":::, требуется учетная запись :::no-loc text="Microsoft 365"::: с лицензией на :::no-loc text="Microsoft 365 Business Voice with SMS":::.</span><span class="sxs-lookup"><span data-stu-id="30eb3-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license.</span></span> <span data-ttu-id="30eb3-104">Если у вас есть учетная запись и лицензия, ей можно назначить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="30eb3-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="30eb3-105">Создание и лицензирование пользователей</span><span class="sxs-lookup"><span data-stu-id="30eb3-105">Create and license users</span></span>

<span data-ttu-id="30eb3-106">Выполните действия, описанные в статье [Добавление пользователей по одному или массово в :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users).</span><span class="sxs-lookup"><span data-stu-id="30eb3-106">Follow the steps in [Add users individually or in bulk to :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users) to add one or more users.</span></span>

> [!NOTE]
> <span data-ttu-id="30eb3-107">В области **Назначение лицензий на продукты** выберите пункт **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-107">In the **Assign product licenses** pane, be sure to select **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="30eb3-108">Назначение номеров телефонов пользователям</span><span class="sxs-lookup"><span data-stu-id="30eb3-108">Assign phone numbers to users</span></span>

<span data-ttu-id="30eb3-109">После создания пользователей и назначения им лицензии :::no-loc text="Microsoft 365 Business Voice with SMS"::: им можно присвоить номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="30eb3-109">After users have been created and assigned a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="30eb3-110">Для каждого пользователя, которому требуется выполнять или принимать звонки на внешние номера телефонов, потребуется один неназначенный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="30eb3-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="30eb3-111">Если у вас недостаточно неназначенных номеров телефонов, см. раздел [Получить дополнительные номера телефонов](#get-more-phone-numbers) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="30eb3-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="30eb3-112">Перейдите на сайт https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="30eb3-112">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="30eb3-113">Введите имя и описание запроса на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="30eb3-113">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="30eb3-114">Выберите **Голосовая связь** > **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-114">Select **Voice** > **Phone numbers**</span></span>
4. <span data-ttu-id="30eb3-115">Выберите номер телефона, который нужно назначить пользователю, и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-115">Select a phone number you want to assign to a user and select **Edit**</span></span>
5. <span data-ttu-id="30eb3-116">В области **Изменить** введите имя пользователя, которому нужно назначить номер телефона в разделе **Назначено**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-116">In the **Edit** panel, enter the name of the user you want to assign the number to in **Assigned to** and select Assign</span></span> <span data-ttu-id="30eb3-117">Затем нажмите **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="30eb3-118">В поле **Местоположение для реагирования экстренных служб** введите расположение, в котором находится пользователь, и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-118">In **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="30eb3-119">Получение дополнительных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="30eb3-119">Get more phone numbers</span></span>

<span data-ttu-id="30eb3-120">Если у вас недостаточно номеров телефонов для назначения новым пользователям, вы можете получить дополнительные номера.</span><span class="sxs-lookup"><span data-stu-id="30eb3-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="30eb3-121">Может потребоваться до 24 часов, чтобы заказанные номера стали доступны.</span><span class="sxs-lookup"><span data-stu-id="30eb3-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="30eb3-122">Перейдите на сайт https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="30eb3-122">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="30eb3-123">Введите имя и описание запроса на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="30eb3-123">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="30eb3-124">Выберите **Голосовая связь** > **Номера телефонов** > **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="30eb3-125">Выберите страну или регион для номера телефона.</span><span class="sxs-lookup"><span data-stu-id="30eb3-125">Choose the country or region where the phone number should be created</span></span>
5. <span data-ttu-id="30eb3-126">В поле **Тип номера** выберите **Пользователь (подписчик)**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-126">In **Number type**, select **User (subscriber)**</span></span>
6. <span data-ttu-id="30eb3-127">В поле **Расположение** найдите расположение пользователя и выберите его.</span><span class="sxs-lookup"><span data-stu-id="30eb3-127">In **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="30eb3-128">Вы также можете выбрать параметр **Добавить расположение**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="30eb3-129">Выберите код города, введите количество нужных телефонных номеров и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-129">Choose an area code, enter the number of phone numbers to get, and then click **Next**</span></span>
8. <span data-ttu-id="30eb3-130">Дождитесь резервирования номеров телефонов, а затем проверьте номера, которые вы получите.</span><span class="sxs-lookup"><span data-stu-id="30eb3-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="30eb3-131">Если все в порядке, нажмите **Разместить заказ** и **Завершить**.</span><span class="sxs-lookup"><span data-stu-id="30eb3-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>

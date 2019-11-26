---
title: Создавайте пользователей Microsoft 365, добавляйте лицензии на корпоративную голосовую связь в Microsoft 365 и назначайте номера телефонов
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
ms.openlocfilehash: a789300c7b7b646ab7b7d288ce5679b6fe3dfff2
ms.sourcegitcommit: 000957709b841ce55a6813ccc2fbe745b1a9295b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2019
ms.locfileid: "39218026"
---
# <a name="create-and-license-users-and-assign-phone-numbers-to-them"></a><span data-ttu-id="8aa4f-102">Создавайте пользователей, предоставляйте им лицензии и назначайте им номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-102">Create and license users and assign phone numbers to them</span></span>

<span data-ttu-id="8aa4f-103">Чтобы использовать :::no-loc text="Microsoft 365 Business Voice":::, пользователю необходима учетная запись :::no-loc text="Microsoft 365"::: с лицензией :::no-loc text="Microsoft 365 Business Voice with SMS":::.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-103">To use Microsoft 365 Business Voice, a user needs an Microsoft 365 account with a Microsoft 365 Business Voice with SMS license.</span></span> <span data-ttu-id="8aa4f-104">После того как будет создана учетная запись с лицензией :::no-loc text="Microsoft 365 Business Voice with SMS":::, ей можно назначить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-104">After an account has been created with a Microsoft 365 Business Voice with SMS license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="8aa4f-105">Создание и лицензирование пользователей</span><span class="sxs-lookup"><span data-stu-id="8aa4f-105">Create and license users</span></span>

1. <span data-ttu-id="8aa4f-106">Чтобы добавить одного или нескольких пользователей, выполните действия, описанные в разделе [Добавление пользователей по одному или массово в :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users).</span><span class="sxs-lookup"><span data-stu-id="8aa4f-106">Follow the steps in Add users individually or in bulk to Office 365 to add one or more users.</span></span>
2. <span data-ttu-id="8aa4f-107">В области **Назначить лицензии продукта** выберите пункт **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-107">In the Assign product licenses pane, be sure to select Microsoft 365 Business Voice with SMS.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="8aa4f-108">Назначение номеров телефонов пользователям</span><span class="sxs-lookup"><span data-stu-id="8aa4f-108">Assign phone numbers to users</span></span>

<span data-ttu-id="8aa4f-109">После того как будут созданы пользователи и им будет назначена лицензия :::no-loc text="Microsoft 365 Business Voice with SMS":::, им можно назначить номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-109">After users have been created and assigned a Microsoft 365 Business Voice with SMS license, you can assign phone numbers to them.</span></span> <span data-ttu-id="8aa4f-110">Для каждого пользователя, которому требуется номер телефона, потребуется один неназначенный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-110">You need one unassigned phone number for each user that needs one.</span></span> <span data-ttu-id="8aa4f-111">Если у вас недостаточно неназначенных номеров телефонов, см. раздел [Получить дополнительные номера телефонов](#get-more-phone-numbers) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="8aa4f-112">Перейдите к https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-112">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="8aa4f-113">Введите имя и описание запроса на номер телефона</span><span class="sxs-lookup"><span data-stu-id="8aa4f-113">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="8aa4f-114">Выберите пункт **Голосовая связь** > **Номера телефонов**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-114">Select **Voice** > **Phone numbers**</span></span>
4. <span data-ttu-id="8aa4f-115">Выберите номер телефона, который вы хотите назначить пользователю, и нажмите кнопку **Изменить**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-115">Select a phone number you want to assign to a user and select **Edit**</span></span>
5. <span data-ttu-id="8aa4f-116">В области **Изменить** введите имя пользователя, которому вы хотите назначить номер телефона в разделе **Назначено...** и выберите **Назначить**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-116">In the **Edit** panel, enter the name of the user you want to assign the number to in **Assigned to** and select **Assign**</span></span>
6. <span data-ttu-id="8aa4f-117">В пункте **Местоположение для экстренного реагирования** введите расположение, в котором находится пользователь, и затем нажмите кнопку **Применить**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-117">In **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>


## <a name="get-more-phone-numbers"></a><span data-ttu-id="8aa4f-118">Получение дополнительных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="8aa4f-118">Get more phone numbers</span></span>

<span data-ttu-id="8aa4f-119">Если у вас недостаточно номеров телефонов для назначения новым пользователям, вы можете получить дополнительные номера.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-119">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="8aa4f-120">После размещения вами заказа может потребоваться до 24 часов, чтобы номера стали доступны.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-120">After you've placed your order, it might take up to 24 hours for the numbers to become available.</span></span>

1. <span data-ttu-id="8aa4f-121">Перейдите к https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-121">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="8aa4f-122">Введите имя и описание запроса на номер телефона</span><span class="sxs-lookup"><span data-stu-id="8aa4f-122">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="8aa4f-123">Выберите пункт **Голосовая связь** > **Номера телефонов**, и затем **Добавить**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-123">Select **Voice** > **Phone numbers**, and then **Add**</span></span>
4. <span data-ttu-id="8aa4f-124">Выберите страну или регион, для которых необходимо создать номер телефона</span><span class="sxs-lookup"><span data-stu-id="8aa4f-124">Choose the country or region where the phone number should be created</span></span>
5. <span data-ttu-id="8aa4f-125">В пункте **Тип номера**выберите **Пользователь (подписчик)**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-125">In **Number type**, select **User (subscriber)**</span></span>
6. <span data-ttu-id="8aa4f-126">В пункте **Расположение** выполните поиск расположения пользователя и выберите его.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-126">In **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="8aa4f-127">При необходимости добавления нового расположения, нажмите кнопку **Добавить расположение**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-127">If you need to add a new location, select **Add a location**</span></span>
7. <span data-ttu-id="8aa4f-128">Выберите код города, введите количество телефонных номеров, которое нужно получить, и нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="8aa4f-128">Choose an area code, enter the number of phone numbers to get, and then click **Next**</span></span>
8. <span data-ttu-id="8aa4f-129">Дождитесь резервирования номеров телефонов, проверьте выбранные номера, и затем, если все правильно, нажмите кнопку **Разместить заказ**, а затем **Завершить**.</span><span class="sxs-lookup"><span data-stu-id="8aa4f-129">Wait for the phone numbers to be reserved, review the numbers chosen and then, if everything looks ok, select **Place order** and then **Finish**.</span></span>


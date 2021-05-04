---
title: Настройка учетной записи Голосовая связь Microsoft 365 бизнес ресурса
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
description: Узнайте, как настроить учетную запись Голосовая связь Microsoft 365 бизнес ресурсов для использования с автоотчетами.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130440"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="339e6-103">Шаг 4. Настройка учетной записи ресурса Business Voice</span><span class="sxs-lookup"><span data-stu-id="339e6-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="339e6-104">В Microsoft Teams требуется учетная запись ресурса для каждого автозавода или очереди вызовов.</span><span class="sxs-lookup"><span data-stu-id="339e6-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="339e6-105">Учетным записям ресурсов также могут быть назначены телефонные номера служб.</span><span class="sxs-lookup"><span data-stu-id="339e6-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="339e6-106">Таким образом вы назначаете номера телефонов автоотводчикам и очередям звонков, чтобы звонив Teams могли связаться с автозаводчиком или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="339e6-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="339e6-107">Получение лицензий виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="339e6-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="339e6-108">Учетным записям ресурсов необходима лицензия для работы с автозаказщиками и очередями вызовов.</span><span class="sxs-lookup"><span data-stu-id="339e6-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="339e6-109">Вы можете использовать бесплатную *лицензию Microsoft 365 телефонная система — виртуальный* пользователь.</span><span class="sxs-lookup"><span data-stu-id="339e6-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="339e6-110">Войдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="339e6-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="339e6-111">Перейти к **надстройкам**"Приобретение служб вы выставлением  >    >  **счета"**  >  **См. все продукты надстройки**</span><span class="sxs-lookup"><span data-stu-id="339e6-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="339e6-112">Прокрутите список до конца, чтобы найти **Microsoft 365 телефонная система — виртуальный пользователь.**</span><span class="sxs-lookup"><span data-stu-id="339e6-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="339e6-113">Выберите **Сведения**, а затем **Купить**.</span><span class="sxs-lookup"><span data-stu-id="339e6-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="339e6-114">На странице приобретения лицензии выберите нужное количество виртуальных пользовательских лицензий.</span><span class="sxs-lookup"><span data-stu-id="339e6-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="339e6-115">Для каждого автозавода и очереди вызовов, которые вы планируете настроить, требуется одна виртуальная лицензия.</span><span class="sxs-lookup"><span data-stu-id="339e6-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="339e6-116">Рекомендуем выбрать по крайней мере пять лицензий, чтобы в будущем можно было легко настроить дополнительных автозаполнения и очереди вызовов, не приобретая дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="339e6-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="339e6-117">Отключите автоматические назначения всем пользователям **без лицензий.**</span><span class="sxs-lookup"><span data-stu-id="339e6-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="339e6-118">Выберите **"Проверить сейчас"**.</span><span class="sxs-lookup"><span data-stu-id="339e6-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="339e6-119">Подтвердите заказ, выберите **Далее**, а затем **Заказать**.</span><span class="sxs-lookup"><span data-stu-id="339e6-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="339e6-120">Помните, что вам  необходимо приобрести лицензию, даже если она имеет нулевую стоимость.</span><span class="sxs-lookup"><span data-stu-id="339e6-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="339e6-121">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="339e6-121">Create a resource account</span></span>

<span data-ttu-id="339e6-122">После получения лицензии *Microsoft 365 телефонная система виртуальный* пользователь вы можете создать учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="339e6-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Снимок экрана: добавление пользовательского интерфейса учетной записи ресурса](../media/resource-account-add.png)

1. <span data-ttu-id="339e6-124">В центре Teams разметка **параметров** для всей организации и нажмите кнопку **Учетные записи ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="339e6-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="339e6-125">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="339e6-125">Select **Add**.</span></span>
3. <span data-ttu-id="339e6-126">В области **Добавление учетной записи** ресурса в заполните **отображаемом имени**, а затем **имя пользователя**.</span><span class="sxs-lookup"><span data-stu-id="339e6-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="339e6-127">Чтобы описать назначение учетной записи ресурса, выберите описательное имя, например "Автоотслевод основной строки".</span><span class="sxs-lookup"><span data-stu-id="339e6-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="339e6-128">В **типе учетной записи ресурса** выберите **Автоотекатарь**.</span><span class="sxs-lookup"><span data-stu-id="339e6-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="339e6-129">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="339e6-129">Select **Save**.</span></span>

![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="339e6-131">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="339e6-131">Assign a license</span></span>

<span data-ttu-id="339e6-132">После создания учетной записи ресурса необходимо назначить лицензию на *Microsoft 365 телефонная система —* виртуальный пользователь или телефонная система *лицензию.*</span><span class="sxs-lookup"><span data-stu-id="339e6-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Снимок экрана: пользовательский интерфейс назначения лицензий в центре Microsoft 365 администрирования](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="339e6-134">В центре Microsoft 365 пользователей перейдите в **группу Пользователи**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="339e6-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="339e6-135">Выберите учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="339e6-135">Select your resource account.</span></span>
1. <span data-ttu-id="339e6-136">На **вкладке Лицензии и приложения** в области **Лицензии** выберите Microsoft 365 телефонная система **— виртуальный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="339e6-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="339e6-137">Выберите **сохранить изменения и** **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="339e6-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="339e6-138">Назначение номера службы</span><span class="sxs-lookup"><span data-stu-id="339e6-138">Assign a service number</span></span>

![Снимок экрана: пользовательский интерфейс назначения номера службы](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="339e6-140">В центре Teams администрирования перейдите в параметры для всей организации, а **затем** — Учетные **записи ресурсов.**</span><span class="sxs-lookup"><span data-stu-id="339e6-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="339e6-141">Выберите только что созданную учетную запись ресурса и нажмите кнопку **Назначить/отозначить**.</span><span class="sxs-lookup"><span data-stu-id="339e6-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="339e6-142">В Телефон **числовом типе** выберите В **сети**.</span><span class="sxs-lookup"><span data-stu-id="339e6-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="339e6-143">В **поле Назначен номер телефона** найдите нужный номер и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="339e6-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="339e6-144">Не забудьте включить код страны (например, **+1** 250 555 0012).</span><span class="sxs-lookup"><span data-stu-id="339e6-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="339e6-145">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="339e6-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="339e6-146">Вам не нужно выбирать автозаводщика в области Назначить, так как автозаводщик, в который вы хотите добавить номер, уже выбран. </span><span class="sxs-lookup"><span data-stu-id="339e6-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="339e6-147">Следующий шаг: назначение номеров телефонов пользователям</span><span class="sxs-lookup"><span data-stu-id="339e6-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)

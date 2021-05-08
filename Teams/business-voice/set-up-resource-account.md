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
ms.openlocfilehash: 618f26394f2b4acc44d56b814bd31c20ffe1a370
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282781"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="940c5-103">Шаг 4. Настройка учетной записи ресурса Business Voice</span><span class="sxs-lookup"><span data-stu-id="940c5-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="940c5-104">Учетные записи ресурсов не назначены конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="940c5-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="940c5-105">Вместо них учетные записи ресурсов, которые используют бесплатную виртуальную лицензию пользователя, используются устройствами и службами в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="940c5-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="940c5-106">В Microsoft Teams, учетным записям ресурсов назначены номера телефонов, которые затем связываются с автоспутниками и очередями звонков.</span><span class="sxs-lookup"><span data-stu-id="940c5-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="940c5-107">Связав учетные записи ресурсов с автоотехами и очередями звонков, вы можете добавить к ним один или несколько платных или бесплатных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="940c5-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="940c5-108">Например, вы можете связать одну учетную запись ресурса с платным номером с автозаполненным номером для локальных вызывающих пользователей.</span><span class="sxs-lookup"><span data-stu-id="940c5-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="940c5-109">Для междугородных звонков можно связать другую учетную запись ресурса с бесплатным номером для того же автоответа.</span><span class="sxs-lookup"><span data-stu-id="940c5-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="940c5-110">В разделах этой статьи поется о том, как настроить учетную запись ресурса и назначить для нее номер телефона.</span><span class="sxs-lookup"><span data-stu-id="940c5-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="940c5-111">Позже вы соберем учетную запись ресурса с автоотчетом.</span><span class="sxs-lookup"><span data-stu-id="940c5-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="940c5-112">Получение лицензий виртуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="940c5-112">Obtain virtual user licenses</span></span>

<span data-ttu-id="940c5-113">Учетным записям ресурсов необходима лицензия для работы с автозаказщиками и очередями вызовов.</span><span class="sxs-lookup"><span data-stu-id="940c5-113">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="940c5-114">Вы можете использовать бесплатную *лицензию Microsoft 365 телефонная система — виртуальный* пользователь.</span><span class="sxs-lookup"><span data-stu-id="940c5-114">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="940c5-115">Если вы озвучили пробный период для бизнес-голосовой почты, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="940c5-115">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="940c5-116">Если вы приобрели лицензии на business Voice, для вашей учетной записи уже должны быть применены виртуальные лицензии.</span><span class="sxs-lookup"><span data-stu-id="940c5-116">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="940c5-117">Чтобы узнать, есть ли у вас виртуальные лицензии, войдите в Microsoft 365 учетную запись с разрешениями глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="940c5-117">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="940c5-118">Затем перейдите в выставление > [ваши продукты](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span><span class="sxs-lookup"><span data-stu-id="940c5-118">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="940c5-119">Если у вас есть виртуальные лицензии, они будут отображаться в Microsoft 365 телефонная система **- Виртуальный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="940c5-119">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="940c5-120">Откройте Центр Microsoft 365 администрирования и войдите с учетной записью глобального администратора (обычно это учетная запись, которую вы использовали для регистрации в Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="940c5-120">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="940c5-121">В левой области навигации <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">   > </a>перейдите в надстройки "Приобретение служб вы выставление счета" См. все продукты  >    >  **надстройки**.</span><span class="sxs-lookup"><span data-stu-id="940c5-121">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="940c5-122">Прокрутите список до конца, чтобы найти **Microsoft 365 телефонная система — виртуальный пользователь.**</span><span class="sxs-lookup"><span data-stu-id="940c5-122">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="940c5-123">Выберите **Сведения**, а затем **Купить**.</span><span class="sxs-lookup"><span data-stu-id="940c5-123">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="940c5-124">На странице приобретения лицензии выберите нужное количество виртуальных пользовательских лицензий.</span><span class="sxs-lookup"><span data-stu-id="940c5-124">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="940c5-125">Для каждого автозавода и очереди вызовов, которые вы планируете настроить, требуется одна виртуальная лицензия.</span><span class="sxs-lookup"><span data-stu-id="940c5-125">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="940c5-126">Рекомендуем выбрать по крайней мере пять лицензий, чтобы в будущем можно было легко настроить дополнительных автозаполнения и очереди вызовов, не приобретая дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="940c5-126">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="940c5-127">Отключите автоматические назначения всем пользователям **без лицензий.**</span><span class="sxs-lookup"><span data-stu-id="940c5-127">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="940c5-128">Выберите **"Проверить сейчас"**.</span><span class="sxs-lookup"><span data-stu-id="940c5-128">Select **Check out now**.</span></span>
7. <span data-ttu-id="940c5-129">Подтвердите заказ, выберите **Далее**, а затем **Заказать**.</span><span class="sxs-lookup"><span data-stu-id="940c5-129">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="940c5-130">Помните, что вам  необходимо приобрести лицензию, даже если она имеет нулевую стоимость.</span><span class="sxs-lookup"><span data-stu-id="940c5-130">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="940c5-131">Создание учетной записи ресурса</span><span class="sxs-lookup"><span data-stu-id="940c5-131">Create a resource account</span></span>

<span data-ttu-id="940c5-132">После получения лицензии *Microsoft 365 телефонная система виртуальный* пользователь вы можете создать учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="940c5-132">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Снимок экрана: добавление пользовательского интерфейса учетной записи ресурса](../media/resource-account-add.png)

1. <span data-ttu-id="940c5-134">Откройте центр Microsoft Teams администрирования и войдите с учетной записью глобального администратора (обычно это учетная запись, которую вы использовали для регистрации в Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="940c5-134">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="940c5-135">В области навигации слева перейдите к настройкам учетных записей ресурсов для всей <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **организации.**</a></span><span class="sxs-lookup"><span data-stu-id="940c5-135">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="940c5-136">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="940c5-136">Select **Add**.</span></span>
4. <span data-ttu-id="940c5-137">В области **Добавление учетной записи** ресурса в заполните **отображаемом имени**, а затем **имя пользователя**.</span><span class="sxs-lookup"><span data-stu-id="940c5-137">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="940c5-138">Чтобы описать назначение учетной записи ресурса, выберите описательное имя, например "Автоотслевод основной строки".</span><span class="sxs-lookup"><span data-stu-id="940c5-138">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="940c5-139">В **типе учетной записи ресурса** выберите **Автоотекатарь**.</span><span class="sxs-lookup"><span data-stu-id="940c5-139">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="940c5-140">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="940c5-140">Select **Save**.</span></span>

![Снимок экрана: список учетных записей ресурсов](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="940c5-142">Назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="940c5-142">Assign a license</span></span>

<span data-ttu-id="940c5-143">После создания учетной записи ресурса необходимо назначить лицензию на *Microsoft 365 телефонная система —* виртуальный пользователь или телефонная система *лицензию.*</span><span class="sxs-lookup"><span data-stu-id="940c5-143">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Снимок экрана: пользовательский интерфейс назначения лицензий в центре Microsoft 365 администрирования](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="940c5-145">Откройте Центр Microsoft 365 администрирования и войдите с учетной записью глобального администратора (обычно это учетная запись, которую вы использовали для регистрации в Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="940c5-145">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="940c5-146">В области навигации слева перейдите в меню <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Пользователи**  >  **Активные пользователи**</a>.</span><span class="sxs-lookup"><span data-stu-id="940c5-146">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="940c5-147">Выберите учетную запись ресурса.</span><span class="sxs-lookup"><span data-stu-id="940c5-147">Select your resource account.</span></span>
1. <span data-ttu-id="940c5-148">На **вкладке Лицензии и приложения** в области **Лицензии** выберите Microsoft 365 телефонная система **— виртуальный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="940c5-148">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="940c5-149">Выберите **сохранить изменения и** **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="940c5-149">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="940c5-150">Назначение номера службы</span><span class="sxs-lookup"><span data-stu-id="940c5-150">Assign a service number</span></span>

![Снимок экрана: пользовательский интерфейс назначения номера службы](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="940c5-152">Откройте центр Microsoft Teams администрирования и войдите с учетной записью глобального администратора (обычно это учетная запись, которую вы использовали для регистрации в Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="940c5-152">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="940c5-153">В области навигации слева перейдите к настройкам учетных записей ресурсов для всей <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **организации.**</a></span><span class="sxs-lookup"><span data-stu-id="940c5-153">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="940c5-154">Выберите только что созданную учетную запись ресурса и нажмите кнопку **Назначить/отозначить**.</span><span class="sxs-lookup"><span data-stu-id="940c5-154">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="940c5-155">В Телефон **числовом типе** выберите В **сети**.</span><span class="sxs-lookup"><span data-stu-id="940c5-155">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="940c5-156">В **поле Назначен номер телефона** найдите нужный номер и нажмите кнопку **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="940c5-156">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="940c5-157">Не забудьте включить код страны (например, **+1** 250 555 0012).</span><span class="sxs-lookup"><span data-stu-id="940c5-157">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="940c5-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="940c5-158">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="940c5-159">Следующий шаг: назначение номеров телефонов пользователям</span><span class="sxs-lookup"><span data-stu-id="940c5-159">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)

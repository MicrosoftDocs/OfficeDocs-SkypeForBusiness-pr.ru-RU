---
title: Управление в хранилище приложений Microsoft Private групп
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Руководство по управлению приложений в магазине закрытый приложения группами Майкрософт.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a2a7e4be22878cf0625077b23fad388b38bc9e
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19576984"
---
<a name="manage-the-microsoft-teams-private-app-store"></a><span data-ttu-id="cd0c9-103">Управление в хранилище приложений Microsoft Private групп</span><span class="sxs-lookup"><span data-stu-id="cd0c9-103">Manage the Microsoft Teams Private App Store</span></span>
============================================

> [!IMPORTANT]
> <span data-ttu-id="cd0c9-104">На этой странице описываются функции предварительного выпуска и содержит предварительные контент, который может значительно изменяться перед выпуском.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="cd0c9-105">Добавляемые снимки экрана являются заполнители и может выглядеть иначе, чем вы см.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="cd0c9-106">В хранилище приложений Microsoft Private группы можно использовать для построения и распространения бизнес приложениями для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-106">You can use the Microsoft Teams Private App Store to build and distribute your line-of-business applications to your organization.</span></span> 

<span data-ttu-id="cd0c9-107">В хранилище приложений Microsoft Private групп позволяет распространять бизнес приложениями, созданные специально для вашей организации и используйте на для выполнения важных функций для пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-107">The Microsoft Teams Private App Store lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="cd0c9-108">Существует два метода для управления в хранилище приложений Private групп:</span><span class="sxs-lookup"><span data-stu-id="cd0c9-108">There are two methods to manage the Teams Private App Store:</span></span>
- <span data-ttu-id="cd0c9-109">Непосредственно от команды клиента</span><span class="sxs-lookup"><span data-stu-id="cd0c9-109">Directly from the Teams client</span></span> 
- <span data-ttu-id="cd0c9-110">Командлеты, использующих возможности интерфейсов API Microsoft Graph (этот метод еще не доступен.)</span><span class="sxs-lookup"><span data-stu-id="cd0c9-110">Cmdlets that leverage Microsoft Graph APIs (This method is not yet available.)</span></span>

## <a name="manage-the-teams-private-app-store-from-the-teams-client"></a><span data-ttu-id="cd0c9-111">Управление хранилище приложений Private групп из группы клиента</span><span class="sxs-lookup"><span data-stu-id="cd0c9-111">Manage the Teams Private App Store from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="cd0c9-112">Получение пакета приложения группы</span><span class="sxs-lookup"><span data-stu-id="cd0c9-112">Get a Teams app package</span></span>

<span data-ttu-id="cd0c9-113">Пакет приложения команды создается с помощью [Команды приложения Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="cd0c9-113">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="cd0c9-114">После появления в пакет приложения, его можно добавить в каталоге приложений предприятия.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-114">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="cd0c9-115">Хотя в каталог приложений могут просматривать все пользователи в клиента, только администраторы имеют возможность управлять им.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-115">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-teams-private-app-store"></a><span data-ttu-id="cd0c9-116">Перейдите на хранилище приложений Private групп</span><span class="sxs-lookup"><span data-stu-id="cd0c9-116">Go to the Teams Private App Store</span></span>

<span data-ttu-id="cd0c9-117">Хранилище группами Майкрософт выберите новый раздел с именем для конкретных организации (в данном примере Contoso).</span><span class="sxs-lookup"><span data-stu-id="cd0c9-117">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="cd0c9-118">Пользователи в вашей организации можно просматривать приложения в каталоге и установить их в которых они являются членами группы.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-118">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a><span data-ttu-id="cd0c9-120">Добавление приложения в хранилище приложений Private групп</span><span class="sxs-lookup"><span data-stu-id="cd0c9-120">Add an app to the Teams Private App Store</span></span>

<span data-ttu-id="cd0c9-121">Из хранилища, выберите **Загрузка настраиваемые приложения** > **Отправить для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-121">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image02.png)

<span data-ttu-id="cd0c9-123">(Вы также можете **Отправить для меня или Мои рабочие группы**, которая называется sideloading, с помощью приложения доступны только для выбранных групп и.)</span><span class="sxs-lookup"><span data-stu-id="cd0c9-123">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="cd0c9-124">Перейдите в пакет приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-124">Navigate to the app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="cd0c9-126">При переходе обратно в каталоге приложений нового корпоративного приложения будет существует.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-126">When you go back to your app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="cd0c9-127">Помните, что только вы и сотрудники организации имеют доступ к этой каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-teams-private-app-store"></a><span data-ttu-id="cd0c9-128">Обновление приложения в магазине группами Private приложения</span><span class="sxs-lookup"><span data-stu-id="cd0c9-128">Update an app in the Teams Private App Store</span></span>

1. <span data-ttu-id="cd0c9-129">Из каталога приложения выберите «**...**»</span><span class="sxs-lookup"><span data-stu-id="cd0c9-129">From your app catalog, select “**…**”</span></span> <span data-ttu-id="cd0c9-130">на сверху справа от приложения, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-130">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="cd0c9-131">Перейдите в пакете обновленного приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-131">Navigate to the updated app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="cd0c9-133">Приложение будет обновлена до версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="cd0c9-134">Для всей компании это меню также удалить приложение.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-134">You also delete the app for your entire company from this menu.</span></span>

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a><span data-ttu-id="cd0c9-135">Управление хранилище приложений Private групп с помощью командлетов и интерфейсы API Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="cd0c9-135">Manage the Teams Private App Store by using cmdlets and Microsoft Graph APIs</span></span>

<span data-ttu-id="cd0c9-136">Этот метод не доступен для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-136">This method is not yet available for preview.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a><span data-ttu-id="cd0c9-137">Использование портала администрирования Office 365 для управления Private приложений</span><span class="sxs-lookup"><span data-stu-id="cd0c9-137">Use the Office 365 admin portal to manage Private Apps</span></span>

<span data-ttu-id="cd0c9-138">Если у вас есть приложения, требующие исправления ошибок, можно временно отключить приложения через портал администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-138">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="cd0c9-139">Помимо предыдущих параметров есть группа теперь выделенные приложения вашей компании.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-139">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="cd0c9-140">Можно выбрать, какие приложения, чтобы включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-140">You can choose which apps you want to enable or disable.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image05.png)

<span data-ttu-id="cd0c9-142">Это блокирует пользователям взаимодействовать с приложением, без удаления приложения полностью.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-142">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="cd0c9-143">Эти элементы управления предоставляют дополнительные возможности администраторов и управления управления приложений на предприятии.</span><span class="sxs-lookup"><span data-stu-id="cd0c9-143">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 



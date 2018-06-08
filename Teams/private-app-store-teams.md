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
ms.openlocfilehash: 6aaa763c423d7756808856706375f96f99224b9e
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "19694891"
---
<a name="publish-apps-to-the-microsoft-teams-private-app-store"></a><span data-ttu-id="b5a97-103">Публикация приложений в хранилище приложений Microsoft Private групп</span><span class="sxs-lookup"><span data-stu-id="b5a97-103">Publish Apps to the Microsoft Teams Private App Store</span></span>
============================================

> [!IMPORTANT]
> <span data-ttu-id="b5a97-104">На этой странице описываются функции предварительного выпуска и содержит предварительные контент, который может значительно изменяться перед выпуском.</span><span class="sxs-lookup"><span data-stu-id="b5a97-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="b5a97-105">Добавляемые снимки экрана являются заполнители и может выглядеть иначе, чем вы см.</span><span class="sxs-lookup"><span data-stu-id="b5a97-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="b5a97-106">В хранилище приложений Microsoft Private группы можно использовать для тестирования и распространения бизнес приложений в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b5a97-106">You can use the Microsoft Teams Private App Store to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="b5a97-107">В хранилище приложений Microsoft Private групп позволяет распространять бизнес приложениями, созданные специально для вашей организации и используйте на для выполнения важных функций для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b5a97-107">The Microsoft Teams Private App Store lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="b5a97-108">Существует два метода для публикации приложений в магазине приложение Private групп:</span><span class="sxs-lookup"><span data-stu-id="b5a97-108">There are two methods to publish apps to the Teams Private App Store:</span></span>
- <span data-ttu-id="b5a97-109">Непосредственно от команды клиента</span><span class="sxs-lookup"><span data-stu-id="b5a97-109">Directly from the Teams client</span></span> 
- <span data-ttu-id="b5a97-110">Командлеты, использующих возможности интерфейсов API Microsoft Graph (этот метод еще не доступен для предварительного просмотра.)</span><span class="sxs-lookup"><span data-stu-id="b5a97-110">Cmdlets that leverage Microsoft Graph APIs (This method is not yet available for preview.)</span></span>

## <a name="publish-an-app-to-the-teams-private-app-store-from-the-teams-client"></a><span data-ttu-id="b5a97-111">Публикация приложения в хранилище приложение Private групп из группы клиента</span><span class="sxs-lookup"><span data-stu-id="b5a97-111">Publish an App to the Teams Private App Store from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="b5a97-112">Получение пакета приложения группы</span><span class="sxs-lookup"><span data-stu-id="b5a97-112">Get a Teams app package</span></span>

<span data-ttu-id="b5a97-113">Пакет приложения команды создается с помощью [Команды приложения Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="b5a97-113">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="b5a97-114">После появления в пакет приложения, его можно добавить в каталоге приложений предприятия.</span><span class="sxs-lookup"><span data-stu-id="b5a97-114">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="b5a97-115">Хотя в каталог приложений могут просматривать все пользователи в клиента, только администраторы имеют возможность управлять им.</span><span class="sxs-lookup"><span data-stu-id="b5a97-115">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-teams-private-app-store"></a><span data-ttu-id="b5a97-116">Перейдите на хранилище приложений Private групп</span><span class="sxs-lookup"><span data-stu-id="b5a97-116">Go to the Teams Private App Store</span></span>

<span data-ttu-id="b5a97-117">Хранилище группами Майкрософт выберите новый раздел с именем для конкретных организации (в данном примере Contoso).</span><span class="sxs-lookup"><span data-stu-id="b5a97-117">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="b5a97-118">Пользователи в вашей организации можно просматривать приложения в каталоге и установить их в которых они являются членами группы.</span><span class="sxs-lookup"><span data-stu-id="b5a97-118">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a><span data-ttu-id="b5a97-120">Добавление приложения в хранилище приложений Private групп</span><span class="sxs-lookup"><span data-stu-id="b5a97-120">Add an app to the Teams Private App Store</span></span>

<span data-ttu-id="b5a97-121">Из хранилища, выберите **Загрузка настраиваемые приложения** > **Отправить для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b5a97-121">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image02.png)

<span data-ttu-id="b5a97-123">(Вы также можете **Отправить для меня или Мои рабочие группы**, которая называется sideloading, с помощью приложения доступны только для выбранных групп и.)</span><span class="sxs-lookup"><span data-stu-id="b5a97-123">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="b5a97-124">Перейдите в пакет приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="b5a97-124">Navigate to the app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="b5a97-126">При переходе обратно в каталоге приложений нового корпоративного приложения будет существует.</span><span class="sxs-lookup"><span data-stu-id="b5a97-126">When you go back to your app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="b5a97-127">Помните, что только вы и сотрудники организации имеют доступ к этой каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="b5a97-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-teams-private-app-store"></a><span data-ttu-id="b5a97-128">Обновление приложения в магазине группами Private приложения</span><span class="sxs-lookup"><span data-stu-id="b5a97-128">Update an app in the Teams Private App Store</span></span>

1. <span data-ttu-id="b5a97-129">Из каталога приложения выберите «**...**»</span><span class="sxs-lookup"><span data-stu-id="b5a97-129">From your app catalog, select “**…**”</span></span> <span data-ttu-id="b5a97-130">на сверху справа от приложения, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="b5a97-130">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="b5a97-131">Перейдите в пакете обновленного приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="b5a97-131">Navigate to the updated app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="b5a97-133">Приложение будет обновлена до версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="b5a97-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="b5a97-134">Для всей компании это меню также удалить приложение.</span><span class="sxs-lookup"><span data-stu-id="b5a97-134">You also delete the app for your entire company from this menu.</span></span>

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a><span data-ttu-id="b5a97-135">Управление хранилище приложений Private групп с помощью командлетов и интерфейсы API Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b5a97-135">Manage the Teams Private App Store by using cmdlets and Microsoft Graph APIs</span></span>

<span data-ttu-id="b5a97-136">Этот метод не доступен для предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="b5a97-136">This method is not yet available for preview.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a><span data-ttu-id="b5a97-137">Использование портала администрирования Office 365 для управления Private приложений</span><span class="sxs-lookup"><span data-stu-id="b5a97-137">Use the Office 365 admin portal to manage Private Apps</span></span>

<span data-ttu-id="b5a97-138">Если у вас есть приложения, требующие исправления ошибок, можно временно отключить приложения через портал администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5a97-138">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="b5a97-139">Помимо предыдущих параметров есть группа теперь выделенные приложения вашей компании.</span><span class="sxs-lookup"><span data-stu-id="b5a97-139">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="b5a97-140">Можно выбрать, какие приложения, чтобы включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="b5a97-140">You can choose which apps you want to enable or disable.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image05.png)

<span data-ttu-id="b5a97-142">Это блокирует пользователям взаимодействовать с приложением, без удаления приложения полностью.</span><span class="sxs-lookup"><span data-stu-id="b5a97-142">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="b5a97-143">Эти элементы управления предоставляют дополнительные возможности администраторов и управления управления приложений на предприятии.</span><span class="sxs-lookup"><span data-stu-id="b5a97-143">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 



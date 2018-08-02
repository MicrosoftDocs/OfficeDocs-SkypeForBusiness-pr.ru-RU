---
title: Публикация приложений в каталог приложений клиента группами Майкрософт
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Руководство для публикации приложений в каталоге приложений Microsoft группы клиента.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 655a9da3670a7894e581cd2e6adebd02ef22706b
ms.sourcegitcommit: d619e44d685e2109b995ffd67ff4b98e5647c8ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "21762937"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="2809a-103">Публикация приложений в каталог приложений клиента группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="2809a-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="2809a-104">Каталог приложений клиента группы Microsoft можно использовать для тестирования и распространения бизнес приложений в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2809a-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="2809a-105">Каталога приложения группы клиента позволяет распространять бизнес приложениями, созданные специально для вашей организации и используйте на для выполнения важных функций для пользователей.</span><span class="sxs-lookup"><span data-stu-id="2809a-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="2809a-106">Каталог приложений клиента группы могут публиковать приложения непосредственно от команды клиента.</span><span class="sxs-lookup"><span data-stu-id="2809a-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="2809a-107">Публикация приложения в каталог приложений клиента из группы клиента</span><span class="sxs-lookup"><span data-stu-id="2809a-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="2809a-108">Получение пакета приложения группы</span><span class="sxs-lookup"><span data-stu-id="2809a-108">Get a Teams app package</span></span>

<span data-ttu-id="2809a-109">Пакет приложения команды создается с помощью [Команды приложения Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="2809a-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="2809a-110">После появления в пакет приложения, его можно добавить в каталоге приложений предприятия.</span><span class="sxs-lookup"><span data-stu-id="2809a-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="2809a-111">При всех пользователей в клиентов можно представления каталога приложений, в настоящее время только глобальные администраторы могут получать публикации и управление им.</span><span class="sxs-lookup"><span data-stu-id="2809a-111">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="2809a-112">(В конечном счете, группы "Администраторы" будет иметь возможность выполнять это также.)</span><span class="sxs-lookup"><span data-stu-id="2809a-112">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="2809a-113">Перейдите в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="2809a-113">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="2809a-114">Хранилище группами Майкрософт выберите новый раздел с именем для конкретных организации (в данном примере Contoso).</span><span class="sxs-lookup"><span data-stu-id="2809a-114">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="2809a-115">Пользователи в вашей организации можно просматривать приложения в каталоге и установить их в которых они являются членами группы.</span><span class="sxs-lookup"><span data-stu-id="2809a-115">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="2809a-117">Добавление приложения в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="2809a-117">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="2809a-118">Из хранилища, выберите **Загрузка настраиваемые приложения** > **Отправить для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="2809a-118">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image02.png)

<span data-ttu-id="2809a-120">(Вы также можете **Отправить для меня или Мои рабочие группы**, которая называется sideloading, с помощью приложения доступны только для выбранных групп и.)</span><span class="sxs-lookup"><span data-stu-id="2809a-120">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="2809a-121">Перейдите в пакет приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="2809a-121">Navigate to the app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="2809a-123">При переходе обратно в каталоге приложений клиента нового корпоративного приложения будет существует.</span><span class="sxs-lookup"><span data-stu-id="2809a-123">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="2809a-124">Помните, что только вы и сотрудники организации имеют доступ к этой каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="2809a-124">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="2809a-125">Обновление приложения в каталоге приложений клиента</span><span class="sxs-lookup"><span data-stu-id="2809a-125">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="2809a-126">Из каталога приложений клиента выберите «**...**»</span><span class="sxs-lookup"><span data-stu-id="2809a-126">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="2809a-127">на сверху справа от приложения, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="2809a-127">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="2809a-128">Перейдите в пакете обновленного приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="2809a-128">Navigate to the updated app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="2809a-130">Приложение будет обновлена до версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="2809a-130">The app will be revised to version 2.0.</span></span> <span data-ttu-id="2809a-131">Для всей компании это меню также удалить приложение.</span><span class="sxs-lookup"><span data-stu-id="2809a-131">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="2809a-132">Использование портала администрирования Office 365 для управление каталогом приложений клиента</span><span class="sxs-lookup"><span data-stu-id="2809a-132">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="2809a-133">Если у вас есть приложения, требующие исправления ошибок, можно временно отключить приложения через портал администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="2809a-133">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="2809a-134">Помимо предыдущих параметров есть группа теперь выделенные приложения вашей компании.</span><span class="sxs-lookup"><span data-stu-id="2809a-134">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="2809a-135">Можно выбрать, какие приложения, чтобы включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="2809a-135">You can choose which apps you want to enable or disable.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image05.png)

<span data-ttu-id="2809a-137">Это блокирует пользователям взаимодействовать с приложением, без удаления приложения полностью.</span><span class="sxs-lookup"><span data-stu-id="2809a-137">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="2809a-138">Эти элементы управления предоставляют дополнительные возможности администраторов и управления управления приложений на предприятии.</span><span class="sxs-lookup"><span data-stu-id="2809a-138">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 



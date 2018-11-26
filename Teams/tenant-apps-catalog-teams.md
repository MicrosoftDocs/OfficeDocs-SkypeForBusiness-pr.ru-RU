---
title: Публикация приложений в каталог приложений клиента группами Майкрософт
author: ChuckEdmonson
ms.author: lolaj
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Руководство для публикации приложений в каталоге приложений Microsoft группы клиента.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2454ad195fbecb25b30218ac156e62d396b4a6dd
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674822"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="aae93-103">Публикация приложений в каталог приложений клиента группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="aae93-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="aae93-104">Каталог приложений клиента группы Microsoft можно использовать для тестирования и распространения бизнес приложений в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aae93-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="aae93-105">Каталога приложения группы клиента позволяет распространять бизнес приложениями, созданные специально для вашей организации и используйте на для выполнения важных функций для пользователей.</span><span class="sxs-lookup"><span data-stu-id="aae93-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="aae93-106">Вход на портал клиента команды, используя учетные данные глобального администратора и публикация приложений для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aae93-106">Sign in to your Teams client using your global admin credentials and publish apps for your organization.</span></span> 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="aae93-107">Публикация приложения в каталог приложений клиента из группы клиента</span><span class="sxs-lookup"><span data-stu-id="aae93-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

<span data-ttu-id="aae93-108">Примечание: Необходимо входить в систему клиента группами Майкрософт, используя учетные данные глобального администратора для публикации приложений для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aae93-108">NOTE: You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="aae93-109">Получение пакета приложения группы</span><span class="sxs-lookup"><span data-stu-id="aae93-109">Get a Teams app package</span></span>

<span data-ttu-id="aae93-110">Пакет приложения команды создается с помощью [Команды приложения Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="aae93-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="aae93-111">После появления в пакет приложения, его можно добавить в каталоге приложений предприятия.</span><span class="sxs-lookup"><span data-stu-id="aae93-111">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="aae93-112">При всех пользователей в клиентов можно представления каталога приложений, в настоящее время только глобальные администраторы могут получать публикации и управление им.</span><span class="sxs-lookup"><span data-stu-id="aae93-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="aae93-113">(В конечном счете, группы "Администраторы" будет иметь возможность выполнять это также.)</span><span class="sxs-lookup"><span data-stu-id="aae93-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="aae93-114">Перейдите в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="aae93-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="aae93-115">Запустите клиент группами Майкрософт и вход с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="aae93-115">Launch the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="aae93-116">Хранилище группами Майкрософт выберите новый раздел с именем для конкретных организации (в данном примере Contoso).</span><span class="sxs-lookup"><span data-stu-id="aae93-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="aae93-117">Пользователи в вашей организации можно просматривать приложения в каталоге и установить их в которых они являются членами группы.</span><span class="sxs-lookup"><span data-stu-id="aae93-117">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="aae93-119">Добавление приложения в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="aae93-119">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="aae93-120">Из хранилища, выберите **Загрузка настраиваемые приложения** > **Отправить для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="aae93-120">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image02.png)

<span data-ttu-id="aae93-122">(Вы также можете **Отправить для меня или Мои рабочие группы**, которая называется sideloading, с помощью приложения доступны только для выбранных групп и.)</span><span class="sxs-lookup"><span data-stu-id="aae93-122">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="aae93-123">Перейдите в пакет приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="aae93-123">Navigate to the app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="aae93-125">При переходе обратно в каталоге приложений клиента нового корпоративного приложения будет существует.</span><span class="sxs-lookup"><span data-stu-id="aae93-125">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="aae93-126">Помните, что только вы и сотрудники организации имеют доступ к этой каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="aae93-126">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="aae93-127">Обновление приложения в каталоге приложений клиента</span><span class="sxs-lookup"><span data-stu-id="aae93-127">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="aae93-128">Из каталога приложений клиента выберите «**...**»</span><span class="sxs-lookup"><span data-stu-id="aae93-128">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="aae93-129">на сверху справа от приложения, которую требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="aae93-129">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="aae93-130">Перейдите в пакете обновленного приложения, а затем выберите ее.</span><span class="sxs-lookup"><span data-stu-id="aae93-130">Navigate to the updated app package and select it.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="aae93-132">Приложение будет обновлена до версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="aae93-132">The app will be revised to version 2.0.</span></span> <span data-ttu-id="aae93-133">Для всей компании это меню также удалить приложение.</span><span class="sxs-lookup"><span data-stu-id="aae93-133">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="aae93-134">Использование портала администрирования Office 365 для управление каталогом приложений клиента</span><span class="sxs-lookup"><span data-stu-id="aae93-134">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="aae93-135">Если у вас есть приложения, требующие исправления ошибок, можно временно отключить приложения через портал администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="aae93-135">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="aae93-136">Помимо предыдущих параметров есть группа теперь выделенные приложения вашей компании.</span><span class="sxs-lookup"><span data-stu-id="aae93-136">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="aae93-137">Можно выбрать, какие приложения, чтобы включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="aae93-137">You can choose which apps you want to enable or disable.</span></span>

![Снимок экрана в хранилище приложений групп отображение каталога приложений.](media/private-app-store-teams-image05.png)

<span data-ttu-id="aae93-139">Это блокирует пользователям взаимодействовать с приложением, без удаления приложения полностью.</span><span class="sxs-lookup"><span data-stu-id="aae93-139">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="aae93-140">Эти элементы управления предоставляют дополнительные возможности администраторов и управления управления приложений на предприятии.</span><span class="sxs-lookup"><span data-stu-id="aae93-140">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 



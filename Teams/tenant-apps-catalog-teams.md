---
title: Публикация приложений в каталоге приложений Microsoft Teams для клиентов
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Руководство по публикации приложений в каталоге приложений Microsoft Teams для клиентов.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d016fd1c341774115b9b68edafcc47a63e42b0d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221327"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="517be-103">Публикация приложений в каталоге приложений Microsoft Teams для клиентов</span><span class="sxs-lookup"><span data-stu-id="517be-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="517be-104">Вы можете использовать каталог приложений клиента Microsoft Teams для тестирования и распространения бизнес-приложений в своей организации.</span><span class="sxs-lookup"><span data-stu-id="517be-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="517be-105">Каталог приложений для клиентов Teams позволяет распределять бизнес-приложения, разработанные специально для вашей организации, и что вы используете для выполнения важнейших бизнес-функций.</span><span class="sxs-lookup"><span data-stu-id="517be-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="517be-106">Чтобы опубликовать приложения для Организации, войдите в клиент Teams с помощью учетных данных глобального администратора и следуйте приведенным ниже инструкциям.</span><span class="sxs-lookup"><span data-stu-id="517be-106">To publish apps for your organization, sign in to your Teams client using your global admin credentials and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="517be-107">Публикация приложения в каталоге приложений клиентов из клиента Teams</span><span class="sxs-lookup"><span data-stu-id="517be-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="517be-108">Чтобы опубликовать приложения для Организации, вам необходимо войти в клиент Microsoft Teams с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="517be-108">You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="517be-109">Получение пакета приложения Teams</span><span class="sxs-lookup"><span data-stu-id="517be-109">Get a Teams app package</span></span>

<span data-ttu-id="517be-110">Пакет приложения Teams создается с помощью [приложения Teams Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="517be-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="517be-111">После того как вы получили пакет приложения, вы можете добавить его в корпоративный каталог приложений.</span><span class="sxs-lookup"><span data-stu-id="517be-111">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="517be-112">Несмотря на то, что все пользователи в клиенте могут просматривать каталог приложений, в настоящее время они смогут публиковать и управлять ими только глобальными администраторами.</span><span class="sxs-lookup"><span data-stu-id="517be-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="517be-113">(В конечном итоге администраторы Teams также смогут это сделать.)</span><span class="sxs-lookup"><span data-stu-id="517be-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="517be-114">Переход в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="517be-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="517be-115">Запустите клиент Microsoft Teams и войдите в систему с помощью учетных данных глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="517be-115">Start the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="517be-116">В магазине Microsoft Teams выберите новый раздел с именем для конкретной организации (в этом примере — Contoso).</span><span class="sxs-lookup"><span data-stu-id="517be-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="517be-117">Пользователи в организации могут просматривать приложения в каталоге и устанавливать их для тех, кто является членом группы.</span><span class="sxs-lookup"><span data-stu-id="517be-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="517be-119">Добавление приложения в каталог приложений клиентов</span><span class="sxs-lookup"><span data-stu-id="517be-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="517be-120">В магазине выберите Отправить настраиваемую отправку **приложения** > **для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="517be-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="517be-122">(Вы также можете выбрать команду **Отправить для меня или мои команды**, которая называется \*\*"неопубликованная".</span><span class="sxs-lookup"><span data-stu-id="517be-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="517be-123">При наличии неопубликованных приложений приложение доступно только для ваших команд или только для команд, которые вы выбираете.)</span><span class="sxs-lookup"><span data-stu-id="517be-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="517be-124">Перейдите к пакету приложения и выберите его, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="517be-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="517be-126">После того как вы вернетесь к каталогу приложения клиента, появится новое корпоративное приложение.</span><span class="sxs-lookup"><span data-stu-id="517be-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="517be-127">Помните, что доступ к этому каталогу приложений имеют только ваши пользователи и члены вашей организации.</span><span class="sxs-lookup"><span data-stu-id="517be-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="517be-128">Обновление приложения в каталоге приложений клиентов</span><span class="sxs-lookup"><span data-stu-id="517be-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="517be-129">Из каталога приложений клиентов выберите "**...**"</span><span class="sxs-lookup"><span data-stu-id="517be-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="517be-130">в правом верхнем углу приложения, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="517be-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="517be-131">Перейдите к обновленному пакету приложения и выберите его, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="517be-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="517be-133">Приложение будет пересмотрено до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="517be-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="517be-134">Вы также можете удалить приложение для всей компании из этого меню.</span><span class="sxs-lookup"><span data-stu-id="517be-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="517be-135">Управление каталогом приложений клиентов с помощью портала администрирования Office 365</span><span class="sxs-lookup"><span data-stu-id="517be-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="517be-136">Если у вас есть приложения, для которых требуется исправление ошибок, вы можете временно отключить их с помощью портала администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="517be-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="517be-137">Выберите **Параметры** > **служб &** > надстроек**Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="517be-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="517be-138">В дополнение к предыдущим настройкам теперь есть раздел, предназначенный для приложений вашей компании.</span><span class="sxs-lookup"><span data-stu-id="517be-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="517be-139">Вы можете выбрать приложения, которые вы хотите включить или отключить.</span><span class="sxs-lookup"><span data-stu-id="517be-139">You can choose which apps you want to enable or disable.</span></span>

![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image05.png)

<span data-ttu-id="517be-141">При отключении приложения пользователи будут блокировать взаимодействие с приложением без полного удаления приложения.</span><span class="sxs-lookup"><span data-stu-id="517be-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="517be-142">Эти элементы управления обеспечивают дополнительные гибкие возможности и управление при управлении приложениями на предприятии.</span><span class="sxs-lookup"><span data-stu-id="517be-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>

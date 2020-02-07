---
title: Публикация приложений в каталоге приложений Microsoft Teams для клиентов
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Руководство по публикации приложений в каталоге приложений Microsoft Teams для клиентов.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1b2fb38dcca7142cad82d290b1225e69f035bae
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836919"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="e7978-103">Публикация приложений в каталоге приложений Microsoft Teams для клиентов</span><span class="sxs-lookup"><span data-stu-id="e7978-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="e7978-104">Вы можете использовать каталог приложений клиента Microsoft Teams для тестирования и распространения бизнес-приложений в своей организации.</span><span class="sxs-lookup"><span data-stu-id="e7978-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="e7978-105">Каталог приложений для клиентов Teams позволяет распределять бизнес-приложения, разработанные специально для вашей организации, и что вы используете для выполнения важнейших бизнес-функций.</span><span class="sxs-lookup"><span data-stu-id="e7978-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="e7978-106">Чтобы опубликовать приложения для своей организации, войдите в клиенте Teams с помощью учетной записи с ролями администратора глобального администратора или службы Teams, а затем следуйте инструкциям ниже.</span><span class="sxs-lookup"><span data-stu-id="e7978-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="e7978-107">Публикация приложения в каталоге приложений клиентов из клиента Teams</span><span class="sxs-lookup"><span data-stu-id="e7978-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="e7978-108">Чтобы опубликовать приложения для Организации, вам необходимо войти в клиент Microsoft Teams с помощью учетной записи, для которой включена роль глобального администратора или администратора службы Teams.</span><span class="sxs-lookup"><span data-stu-id="e7978-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="e7978-109">Дополнительные сведения об [использовании ролей администратора для управления группами](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e7978-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="e7978-110">Получение пакета приложения Teams</span><span class="sxs-lookup"><span data-stu-id="e7978-110">Get a Teams app package</span></span>

<span data-ttu-id="e7978-111">Пакет приложения Teams создается с помощью [приложения Teams Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="e7978-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="e7978-112">После того как вы получили пакет приложения, вы можете добавить его в корпоративный каталог приложений.</span><span class="sxs-lookup"><span data-stu-id="e7978-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="e7978-113">Несмотря на то, что все пользователи в клиенте могут просматривать каталог приложений, только глобальные администраторы и администраторы служб Teams смогут публиковать их и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="e7978-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="e7978-114">Переход в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="e7978-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="e7978-115">Запустите клиент Microsoft Teams и войдите в систему с помощью глобальных учетных данных администратора или службы Teams Service.</span><span class="sxs-lookup"><span data-stu-id="e7978-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="e7978-116">Выберите **приложения** в левой части приложения, а затем выберите новый раздел с именем для конкретной организации (в этом примере — Contoso).</span><span class="sxs-lookup"><span data-stu-id="e7978-116">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="e7978-117">Пользователи в организации могут просматривать приложения в каталоге и устанавливать их для тех, кто является членом группы.</span><span class="sxs-lookup"><span data-stu-id="e7978-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="e7978-119">Добавление приложения в каталог приложений клиентов</span><span class="sxs-lookup"><span data-stu-id="e7978-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="e7978-120">На странице **приложения** выберите **Отправить настраиваемое приложение** > **для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="e7978-120">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="e7978-122">(Вы также можете выбрать команду **Отправить для меня или мои команды**, которая называется " *неопубликованная*".</span><span class="sxs-lookup"><span data-stu-id="e7978-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="e7978-123">При наличии неопубликованных приложений приложение доступно только для ваших команд или только для команд, которые вы выбираете.)</span><span class="sxs-lookup"><span data-stu-id="e7978-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="e7978-124">Перейдите к пакету приложения и выберите его, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e7978-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="e7978-126">После того как вы вернетесь к каталогу приложения клиента, появится новое корпоративное приложение.</span><span class="sxs-lookup"><span data-stu-id="e7978-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="e7978-127">Помните, что доступ к этому каталогу приложений имеют только ваши пользователи и члены вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e7978-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="e7978-128">Обновление приложения в каталоге приложений клиентов</span><span class="sxs-lookup"><span data-stu-id="e7978-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="e7978-129">Из каталога приложений клиентов выберите "**...**"</span><span class="sxs-lookup"><span data-stu-id="e7978-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="e7978-130">в правом верхнем углу приложения, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="e7978-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="e7978-131">Перейдите к обновленному пакету приложения и выберите его, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e7978-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="e7978-133">Приложение будет пересмотрено до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e7978-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="e7978-134">Вы также можете удалить приложение для всей компании из этого меню.</span><span class="sxs-lookup"><span data-stu-id="e7978-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="e7978-135">Управление каталогом приложений клиентов с помощью портала администрирования Office 365</span><span class="sxs-lookup"><span data-stu-id="e7978-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="e7978-136">Если у вас есть приложения, для которых требуется исправление ошибок, вы можете временно отключить их с помощью центра администрирования Microsoft 365 >**политики разрешений** для > **приложений** > в **центре администрирования**Teams > <, например "глобальные (параметры по умолчанию для организационной организации) **> >"** .</span><span class="sxs-lookup"><span data-stu-id="e7978-136">If you have apps that need bug fixes, you can temporarily disable apps through the Microsoft 365 admin center > **Teams admin center** > **Teams apps** > **Permission Policies** > <policy name, e.g. "Global (Org-wide default)"> **Tenant apps** > Block specific apps and allow all others and add your app to the list.</span></span>

![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image05.png)

<span data-ttu-id="e7978-138">При отключении приложения пользователи будут блокировать взаимодействие с приложением без полного удаления приложения.</span><span class="sxs-lookup"><span data-stu-id="e7978-138">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="e7978-139">Эти элементы управления обеспечивают дополнительные гибкие возможности и управление при управлении приложениями на предприятии.</span><span class="sxs-lookup"><span data-stu-id="e7978-139">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>

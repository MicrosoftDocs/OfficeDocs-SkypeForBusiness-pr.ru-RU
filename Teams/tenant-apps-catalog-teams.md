---
title: Публикация приложений в каталоге приложений клиента Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Руководство по публикации приложений в каталоге приложений для клиентов Microsoft Teams.
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
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161618"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="86d6f-103">Публикация приложений в каталоге приложений клиента Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86d6f-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="86d6f-104">Вы можете использовать каталог приложений клиента Microsoft Teams для тестирования и распространения бизнес-приложений в своей организации.</span><span class="sxs-lookup"><span data-stu-id="86d6f-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="86d6f-105">Каталог приложений "клиент Teams" позволяет распределять бизнес-приложения, разработанные специально для вашей организации, и что вы используете для выполнения важнейших бизнес-функций.</span><span class="sxs-lookup"><span data-stu-id="86d6f-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="86d6f-106">Чтобы опубликовать приложения для Организации, войдите в клиент Teams с помощью учетной записи глобального администратора или администратора службы Teams, а затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="86d6f-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="86d6f-107">Публикация приложения в каталоге приложений клиента из клиента Teams</span><span class="sxs-lookup"><span data-stu-id="86d6f-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="86d6f-108">Эти шаги описывают, как опубликовать приложение с помощью клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="86d6f-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="86d6f-109">Вы также можете опубликовать приложение на странице **Управление приложениями** в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="86d6f-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="86d6f-110">Дополнительные сведения можно найти [в разделе Управление приложениями в Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="86d6f-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="86d6f-111">Получение пакета приложения Teams</span><span class="sxs-lookup"><span data-stu-id="86d6f-111">Get a Teams app package</span></span>

<span data-ttu-id="86d6f-112">Пакет приложения Teams создается с помощью [приложения Teams Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="86d6f-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="86d6f-113">После того как вы получили пакет приложения, вы можете добавить его в каталог приложений клиента.</span><span class="sxs-lookup"><span data-stu-id="86d6f-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="86d6f-114">Несмотря на то, что все пользователи в организации могут просматривать каталог приложений, только глобальные администраторы и администраторы служб Teams смогут публиковать их и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="86d6f-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="86d6f-115">Переход в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="86d6f-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="86d6f-116">Запустите Teams и войдите в систему с помощью глобальных учетных данных администратора или службы Teams Service.</span><span class="sxs-lookup"><span data-stu-id="86d6f-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="86d6f-117">Выберите **приложения** в левой части приложения, а затем выберите новый раздел с именем для конкретной организации (в этом примере — Contoso).</span><span class="sxs-lookup"><span data-stu-id="86d6f-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="86d6f-118">Пользователи в организации могут просматривать приложения в каталоге и устанавливать их для тех, кто является членом группы.</span><span class="sxs-lookup"><span data-stu-id="86d6f-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="86d6f-120">Добавление приложения в каталог приложений клиента</span><span class="sxs-lookup"><span data-stu-id="86d6f-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="86d6f-121">На странице **приложения** выберите **Отправить настраиваемое приложение** > **для Contoso**.</span><span class="sxs-lookup"><span data-stu-id="86d6f-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="86d6f-123">(Вы также можете выбрать команду **Отправить для меня или мои команды**, которая называется " *неопубликованная*".</span><span class="sxs-lookup"><span data-stu-id="86d6f-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="86d6f-124">При наличии неопубликованных приложений приложение доступно только для ваших команд или только для команд, которые вы выбираете.)</span><span class="sxs-lookup"><span data-stu-id="86d6f-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="86d6f-125">Перейдите к пакету приложения и выберите его, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="86d6f-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image03.png)

<span data-ttu-id="86d6f-127">После того как вы вернетесь к каталогу приложений клиента, появится новое корпоративное приложение.</span><span class="sxs-lookup"><span data-stu-id="86d6f-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="86d6f-128">Помните, что доступ к этому каталогу приложений имеют только ваши пользователи и члены вашей организации.</span><span class="sxs-lookup"><span data-stu-id="86d6f-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="86d6f-129">Обновление приложения в каталоге приложений клиента</span><span class="sxs-lookup"><span data-stu-id="86d6f-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="86d6f-130">Из каталога приложений клиента выберите "**...**"</span><span class="sxs-lookup"><span data-stu-id="86d6f-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="86d6f-131">в правом верхнем углу приложения, которое вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="86d6f-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="86d6f-132">Перейдите к обновленному пакету приложения и выберите его, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="86d6f-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Снимок экрана: магазин приложений Teams, показывающий Каталог приложений.](media/private-app-store-teams-image04.png)

<span data-ttu-id="86d6f-134">Приложение будет пересмотрено до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="86d6f-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="86d6f-135">Вы также можете удалить приложение для всей компании из этого меню.</span><span class="sxs-lookup"><span data-stu-id="86d6f-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="86d6f-136">Управление каталогом приложений клиента с помощью центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86d6f-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="86d6f-137">Если у вас есть приложения, для которых требуется исправление ошибок, вы можете временно отключить приложения для пользователей в политике разрешений приложения.</span><span class="sxs-lookup"><span data-stu-id="86d6f-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="86d6f-138">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел > **политики разрешений**для **приложений Teams**.</span><span class="sxs-lookup"><span data-stu-id="86d6f-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="86d6f-139">Выберите политику разрешений приложения, которую вы хотите изменить, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="86d6f-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="86d6f-140">В разделе **приложения клиента**щелкните **блокировать определенные приложения и разрешите все другие**, а затем добавьте приложения, которые вы хотите заблокировать.</span><span class="sxs-lookup"><span data-stu-id="86d6f-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="86d6f-141">Отключение приложения блокирует взаимодействие пользователей с приложением без полного удаления приложения.</span><span class="sxs-lookup"><span data-stu-id="86d6f-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="86d6f-142">Эти элементы управления обеспечивают дополнительные гибкие возможности и управление при управлении приложениями в Организации.</span><span class="sxs-lookup"><span data-stu-id="86d6f-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="86d6f-143">Дополнительные сведения можно найти [в разделе Управление политиками разрешений приложений в Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="86d6f-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>
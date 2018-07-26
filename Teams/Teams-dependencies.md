---
title: Авторизация гостевого доступа в Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: Управление функциями и возможностями гостевого доступа Microsoft Teams ведется с помощью четырех разных уровней авторизации.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d31bb8eafdaa6a04fe34f8433e8484ec447e7c1
ms.sourcegitcommit: 2ce680aba13d1d781019b766a04e4e7d46d4f72c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "21136309"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="c6c14-103">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6c14-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="c6c14-104">Чтобы выполнить требования организации, можно управлять функциями и возможностями гостевого доступа Microsoft Teams с помощью четырех разных уровней авторизации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="c6c14-105">К клиенту Office 365 применяются все уровни авторизации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="c6c14-106">Каждый уровень авторизации управляет взаимодействием с гостями, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="c6c14-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="c6c14-107">**Azure Active Directory**: Гостевой доступ в Microsoft Teams опирается на платформу Azure AD B2B.</span><span class="sxs-lookup"><span data-stu-id="c6c14-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="c6c14-108">Управляет взаимодействием с гостями на уровне каталога, клиента и приложения.</span><span class="sxs-lookup"><span data-stu-id="c6c14-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="c6c14-109">**Microsoft Teams**: Управляет только Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="c6c14-110">**Группы Office 365**: Управляет взаимодействием с гостями в группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="c6c14-111">**SharePoint Online и OneDrive для бизнеса**: Управляет взаимодействием с гостями в SharePoint Online, OneDrive для бизнеса, группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="c6c14-112">Все эти уровни авторизации дают вам гибкость в настройке гостевого доступа для организации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="c6c14-113">Например, если вы хотите запретить гостей в организации с Microsoft Teams, просто отключите гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="c6c14-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="c6c14-114">Другой пример. Вы можете включить гостевой доступ на уровнях AAD, Microsoft Teams и групп, но затем отключить добавление гостей в выбранных группах, соответствующих одному критерию или нескольким, например, если данные классифицируются как конфиденциальная информация.</span><span class="sxs-lookup"><span data-stu-id="c6c14-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="c6c14-115">Возможно, вы не используете группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c14-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="c6c14-116">SharePoint Online и OneDrive для бизнеса имеют собственные параметры гостевого доступа, которые не связаны с группами Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c14-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="c6c14-117">На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="c6c14-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="c6c14-118">На следующей схеме показано, как зависимость авторизации гостевого доступа предоставляется и встраивается в связке с Azure Active Directory, Microsoft Teams и Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c14-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Схема зависимостей авторизации для гостевого доступа](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="c6c14-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c6c14-120">Azure Active Directory</span></span>

<span data-ttu-id="c6c14-121">Благодаря взаимодействию с Azure AD B2B отправлять приглашения возможным гостям могут не только администраторы клиента.</span><span class="sxs-lookup"><span data-stu-id="c6c14-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="c6c14-122">Вместо этого вы можете использовать политики, чтобы делегировать отправку приглашений пользователям, чьи роли позволяют им отправлять приглашения.</span><span class="sxs-lookup"><span data-stu-id="c6c14-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="c6c14-123">Параметры для приглашений применяются на уровне клиента и управляют взаимодействием с гостем на уровне каталога, клиента и приложения.</span><span class="sxs-lookup"><span data-stu-id="c6c14-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="c6c14-124">Как минимум для поддержки гости **можно пригласить участников** должен иметь значение **Да**.</span><span class="sxs-lookup"><span data-stu-id="c6c14-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Снимок экрана параметров пользователя на портале Azure Active Directory.](media/teams_dependencies_image2.png)

<span data-ttu-id="c6c14-126">Azure AD имеются следующие параметры для настройки внешних пользователей:</span><span class="sxs-lookup"><span data-stu-id="c6c14-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="c6c14-127">**Разрешения пользователя не более**: **Да** означает, что Гости не иметь разрешение для определенных каталогов задач, таких как перечисление пользователей, групп и другие ресурсы, каталог.</span><span class="sxs-lookup"><span data-stu-id="c6c14-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="c6c14-128">Кроме того Гости не может быть назначен административных ролей в каталоге.</span><span class="sxs-lookup"><span data-stu-id="c6c14-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="c6c14-129">**Нет** означает, что на компьютерах с гостевым имеют такой же доступ к данным каталога, для которого обычных пользователей в каталоге.</span><span class="sxs-lookup"><span data-stu-id="c6c14-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="c6c14-130">**Можно пригласить администраторов и пользователей в роль приглашающему гостя**: **Да** означает, что администраторов и пользователей в роль «Гость приглашающему» возможность приглашать Гости к клиенту.</span><span class="sxs-lookup"><span data-stu-id="c6c14-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="c6c14-131">**Нет** означает, что администраторы и пользователи не могут приглашать Гости к клиенту.</span><span class="sxs-lookup"><span data-stu-id="c6c14-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="c6c14-132">**Можно пригласить участников**: **Да** означает, что члены без прав администратора каталога можно пригласить Гости также совместно работать с ресурсами, защищенным с Azure AD, таких как сайты SharePoint или Azure ресурсы.</span><span class="sxs-lookup"><span data-stu-id="c6c14-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="c6c14-133">**Нет** означает, что только администраторы могут пригласить гости в каталог.</span><span class="sxs-lookup"><span data-stu-id="c6c14-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="c6c14-134">**Можно пригласить Гости**: **Да** означает, что гости в каталоге могут сами пригласить других гостевых также совместно работать с ресурсами, защищенным с Azure AD, таких как сайты SharePoint или Azure ресурсы.</span><span class="sxs-lookup"><span data-stu-id="c6c14-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="c6c14-135">**Нет** означает, что Гости не удается пригласить других виртуальных машин для совместной работы с вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="c6c14-136">Также можно управлять, какие домены можно пригласить на вашего клиента как гости.</span><span class="sxs-lookup"><span data-stu-id="c6c14-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="c6c14-137">Просмотрите [разрешенных и запрещенных гостевой доступ к группам Office 365](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da).</span><span class="sxs-lookup"><span data-stu-id="c6c14-137">See [Allow/Block guest access to Office 365 groups](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="c6c14-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6c14-138">Microsoft Teams</span></span>
<span data-ttu-id="c6c14-139">В Microsoft Teams вы можете управлять включением поддержки гостевых функций в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="c6c14-140">Параметр отключен по умолчанию и применяется на уровне клиента только для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="c6c14-141">Вы можете управлять параметрами гостевого доступа Microsoft Teams в Центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c14-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="c6c14-142">Дополнительные сведения см. в разделе [Включение и отключение гостевого доступа для Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="c6c14-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="c6c14-143">Группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6c14-143">Office 365 Groups</span></span>

<span data-ttu-id="c6c14-144">В группах Office 365 вы можете управлять добавлением гостевых пользователей и гостевым доступом ко всем группам Office 365 и Microsoft Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="c6c14-145">Вход с помощью учетной записи глобального администратора Office 365 в [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="c6c14-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="c6c14-146">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="c6c14-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="c6c14-147">Выберите **Группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="c6c14-147">Select **Office 365 Groups**.</span></span>
    
     ![Группы Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="c6c14-149">На странице "Группы Office 365" установите переключатель в положение **Включить** или **Отключить**, в зависимости от того, хотите ли вы разрешить владельцам групп доступ к группам Office 365 извне организации.</span><span class="sxs-lookup"><span data-stu-id="c6c14-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="c6c14-150">Выберите значение **Включить** рядом с параметром **Let group owners add people outside the organization to groups** (Разрешить владельцам добавлять в группы людей извне организации).</span><span class="sxs-lookup"><span data-stu-id="c6c14-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="c6c14-151">Если вы включите этот параметр, то сможете выбрать, разрешать ли владельцам групп добавлять пользователей извне организации в группы Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="c6c14-152">Включите его, если хотите разрешить владельцам групп добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="c6c14-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="c6c14-153">![Снимок экрана, показывающий панель групп Office 365 с включенными параметрами "Let group members outside the organization access group content" (Предоставить участникам групп доступ к контенту групп извне организации) и "Let group owners add people outside the organization to groups" (Разрешить владельцам добавлять в группы людей извне организации).](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="c6c14-153">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="c6c14-154">Параметры ниже применяются на уровне клиента и управляют взаимодействием с гостями в группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="c6c14-155">SharePoint Online и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c6c14-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="c6c14-156">Система Teams использует SharePoint Online и OneDrive для бизнеса, чтобы хранить файлы и документы для бесед в каналах и чате.</span><span class="sxs-lookup"><span data-stu-id="c6c14-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="c6c14-157">Чтобы обеспечить полноценный гостевой доступ в Teams, администраторам Office 365 следует выбрать значение **Включить** для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c6c14-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="c6c14-158">В SharePoint Online: **Only allow sharing with external users already in the directory (Разрешить общий доступ только с внешними пользователями, уже присутствующими в каталоге)**</span><span class="sxs-lookup"><span data-stu-id="c6c14-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="c6c14-159">Дополнительные сведения см. в статье [Управление внешним общим доступом для среды SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="c6c14-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="c6c14-160">В Группах Office 365: **Let group owners add people outside the organization to groups (Разрешить владельцам добавлять в группы людей извне организации)**</span><span class="sxs-lookup"><span data-stu-id="c6c14-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="c6c14-161">Дополнительные сведения см. в статье [Контроль гостевого доступа в Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="c6c14-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="c6c14-162">Параметры выше применяются на уровне клиента и управляют взаимодействием с гостями в SharePoint Online, OneDrive для бизнеса, группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c6c14-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="c6c14-163">Вы можете управлять параметрами внешних пользователей SharePoint Online для подключенного к Teams сайта группы.</span><span class="sxs-lookup"><span data-stu-id="c6c14-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="c6c14-164">Дополнительные сведения см. в статье [Управление параметрами для сайта группы SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="c6c14-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

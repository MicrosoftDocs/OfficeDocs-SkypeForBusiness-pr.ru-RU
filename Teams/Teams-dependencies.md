---
title: "Авторизация гостевого доступа в Microsoft Teams"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviwer: laal
description: "Управление функциями и возможностями гостевого доступа Microsoft Teams ведется с помощью четырех разных уровней авторизации."
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1ceee3b884b62680353eac11c94198024b927e
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2018
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="de7af-103">Авторизация гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de7af-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="de7af-104">Чтобы выполнить требования организации, можно управлять функциями и возможностями гостевого доступа Microsoft Teams с помощью четырех разных уровней авторизации.</span><span class="sxs-lookup"><span data-stu-id="de7af-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="de7af-105">К клиенту Office 365 применяются все уровни авторизации.</span><span class="sxs-lookup"><span data-stu-id="de7af-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="de7af-106">Каждый уровень авторизации управляет взаимодействием с гостями, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="de7af-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="de7af-107">**Azure Active Directory**: Гостевой доступ в Microsoft Teams опирается на платформу Azure AD B2B.</span><span class="sxs-lookup"><span data-stu-id="de7af-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="de7af-108">Управляет взаимодействием с гостями на уровне каталога, клиента и приложения.</span><span class="sxs-lookup"><span data-stu-id="de7af-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="de7af-109">**Microsoft Teams**: Управляет только Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="de7af-110">**Группы Office 365**: Управляет взаимодействием с гостями в группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="de7af-111">**SharePoint Online и OneDrive для бизнеса**: Управляет взаимодействием с гостями в SharePoint Online, OneDrive для бизнеса, группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="de7af-112">Все эти уровни авторизации дают вам гибкость в настройке гостевого доступа для организации.</span><span class="sxs-lookup"><span data-stu-id="de7af-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="de7af-113">Например, если вы хотите запретить гостей в организации с Microsoft Teams, просто отключите гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="de7af-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="de7af-114">Другой пример. Вы можете включить гостевой доступ на уровнях AAD, Microsoft Teams и групп, но затем отключить добавление гостей в выбранных группах, соответствующих одному критерию или нескольким, например, если данные классифицируются как конфиденциальная информация.</span><span class="sxs-lookup"><span data-stu-id="de7af-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="de7af-115">Возможно, вы не используете группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="de7af-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="de7af-116">SharePoint Online и OneDrive для бизнеса имеют собственные параметры гостевого доступа, которые не связаны с группами Office 365.</span><span class="sxs-lookup"><span data-stu-id="de7af-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="de7af-117">На гостей распространяются ограничения служб [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) и [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="de7af-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="de7af-118">На следующей схеме показано, как зависимость авторизации гостевого доступа предоставляется и встраивается в связке с Azure Active Directory, Microsoft Teams и Office 365.</span><span class="sxs-lookup"><span data-stu-id="de7af-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Схема зависимостей авторизации для гостевого доступа](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a><span data-ttu-id="de7af-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="de7af-120">Azure Active Directory</span></span>

<span data-ttu-id="de7af-121">Благодаря взаимодействию с Azure AD B2B отправлять приглашения возможным гостям могут не только администраторы клиента.</span><span class="sxs-lookup"><span data-stu-id="de7af-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="de7af-122">Вместо этого вы можете использовать политики, чтобы делегировать отправку приглашений пользователям, чьи роли позволяют им отправлять приглашения.</span><span class="sxs-lookup"><span data-stu-id="de7af-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="de7af-123">Параметры для приглашений применяются на уровне клиента и управляют взаимодействием с гостем на уровне каталога, клиента и приложения.</span><span class="sxs-lookup"><span data-stu-id="de7af-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span>


![Снимок экрана параметров пользователя на портале Azure Active Directory.](media/teams_dependencies_image2.png)


<span data-ttu-id="de7af-125">Можно задать следующие политики приглашений.</span><span class="sxs-lookup"><span data-stu-id="de7af-125">You can set the following invitation policies:</span></span>
- <span data-ttu-id="de7af-126">Отключение приглашений.</span><span class="sxs-lookup"><span data-stu-id="de7af-126">Turn off invitations.</span></span>
- <span data-ttu-id="de7af-127">Только администраторы и пользователи, роль которых позволяет приглашать гостей, могут отправлять приглашения.</span><span class="sxs-lookup"><span data-stu-id="de7af-127">Only admins and users in the guest inviter role can invite.</span></span>
- <span data-ttu-id="de7af-128">Администраторы, приглашающие гостей, и участники могут отправлять приглашения.</span><span class="sxs-lookup"><span data-stu-id="de7af-128">Admins, the guest inviter role, and members can invite.</span></span>
- <span data-ttu-id="de7af-129">Все пользователи, включая гостей, могут отправлять приглашения.</span><span class="sxs-lookup"><span data-stu-id="de7af-129">All users, including guests, can invite.</span></span> <span data-ttu-id="de7af-130">(Это политика по умолчанию для клиентов.)</span><span class="sxs-lookup"><span data-stu-id="de7af-130">(This is the default policy for tenants.)</span></span>


##<a name="microsoft-teams"></a><span data-ttu-id="de7af-131">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de7af-131">Microsoft Teams</span></span>

<span data-ttu-id="de7af-132">В Microsoft Teams вы можете управлять включением поддержки гостевых функций в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="de7af-132">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="de7af-133">Параметр отключен по умолчанию и применяется на уровне клиента только для Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-133">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="de7af-134">Вы можете управлять параметрами гостевого доступа Microsoft Teams в Центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="de7af-134">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="de7af-135">Дополнительные сведения см. в разделе [Включение и отключение гостевого доступа для Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="de7af-135">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


##<a name="office-365-groups"></a><span data-ttu-id="de7af-136">Группы Office 365.</span><span class="sxs-lookup"><span data-stu-id="de7af-136">Office 365 Groups</span></span>

<span data-ttu-id="de7af-137">В группах Office 365 вы можете управлять добавлением гостевых пользователей и гостевым доступом ко всем группам Office 365 и Microsoft Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="de7af-137">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="de7af-138">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="de7af-138">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="de7af-139">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="de7af-139">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="de7af-140">Выберите **Группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="de7af-140">Select **Office 365 Groups**.</span></span>
    
     ![Группы Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="de7af-142">На странице "Группы Office 365" установите переключатель в положение **Включить** или **Отключить**, в зависимости от того, хотите ли вы разрешить владельцам групп доступ к группам Office 365 извне организации.</span><span class="sxs-lookup"><span data-stu-id="de7af-142">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="de7af-143">Выберите значение **Включить** рядом с параметром **Let group owners add people outside the organization to groups** (Разрешить владельцам добавлять в группы людей извне организации).</span><span class="sxs-lookup"><span data-stu-id="de7af-143">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="de7af-144">Если вы включите этот параметр, то сможете выбрать, разрешать ли владельцам групп добавлять пользователей извне организации в группы Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-144">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="de7af-145">Включите его, если хотите разрешить владельцам групп добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="de7af-145">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="de7af-146">![Снимок экрана, показывающий панель групп Office 365 с включенными параметрами "Let group members outside the organization access group content" (Предоставить участникам групп доступ к контенту групп извне организации) и "Let group owners add people outside the organization to groups" (Разрешить владельцам добавлять в группы людей извне организации).](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="de7af-146">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="de7af-147">Параметры ниже применяются на уровне клиента и управляют взаимодействием с гостями в группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-147">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


##<a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="de7af-148">SharePoint Online и OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="de7af-148">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="de7af-149">Система Teams использует SharePoint Online и OneDrive для бизнеса, чтобы хранить файлы и документы для бесед в каналах и чате.</span><span class="sxs-lookup"><span data-stu-id="de7af-149">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="de7af-150">Чтобы обеспечить полноценный гостевой доступ в Teams, администраторам Office 365 следует выбрать значение **Включить** для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="de7af-150">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="de7af-151">В SharePoint Online: **Only allow sharing with external users already in the directory (Разрешить общий доступ только с внешними пользователями, уже присутствующими в каталоге)**</span><span class="sxs-lookup"><span data-stu-id="de7af-151">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="de7af-152">Дополнительные сведения см. в статье [Управление внешним общим доступом для среды SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="de7af-152">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="de7af-153">В Группах Office 365: **Let group owners add people outside the organization to groups (Разрешить владельцам добавлять в группы людей извне организации)**</span><span class="sxs-lookup"><span data-stu-id="de7af-153">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="de7af-154">Дополнительные сведения см. в статье [Контроль гостевого доступа в Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="de7af-154">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="de7af-155">Параметры выше применяются на уровне клиента и управляют взаимодействием с гостями в SharePoint Online, OneDrive для бизнеса, группах Office 365 и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de7af-155">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="de7af-156">Вы можете управлять параметрами внешних пользователей SharePoint Online для подключенного к Teams сайта группы.</span><span class="sxs-lookup"><span data-stu-id="de7af-156">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="de7af-157">Дополнительные сведения см. в статье [Управление параметрами для сайта группы SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="de7af-157">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
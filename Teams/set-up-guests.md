---
title: "Настройка гостевого доступа в Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Включите функцию управления гостевым доступом в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a><span data-ttu-id="b3543-103">Настройка гостевого доступа в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3543-103">Set up guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="b3543-104">Работа Microsoft Teams основана на Группах Office 365, а также SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b3543-104">Microsoft Teams is built upon Office 365 Groups, and it also relies on SharePoint Online.</span></span> <span data-ttu-id="b3543-105">Поэтому для использования гостевого доступа в Teams нужно также включить определенные параметры в Группах Office 365 и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b3543-105">That’s why specific settings must be enabled in Office 365 Groups and SharePoint Online in addition to turning on the guest access feature in Teams.</span></span>


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a><span data-ttu-id="b3543-106">Разрешение добавления гостей в Группах Office 365</span><span class="sxs-lookup"><span data-stu-id="b3543-106">Allow the addition of guests in Office 365 Groups</span></span>
<span data-ttu-id="b3543-107"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="b3543-107"></span></span>


1. <span data-ttu-id="b3543-108">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="b3543-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="b3543-109">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="b3543-109">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="b3543-110">Выберите **Группы Office 365**.</span><span class="sxs-lookup"><span data-stu-id="b3543-110">Select **Office 365 Groups**.</span></span>
    
     ![Группы Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="b3543-112">На странице "Группы Office 365" установите переключатель в положение **Включить** или **Отключить**, в зависимости от того, хотите ли вы разрешить владельцам групп доступ к группам Office 365 извне организации.</span><span class="sxs-lookup"><span data-stu-id="b3543-112">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="b3543-113">Выберите значение **Включить** рядом с параметром **Let group owners add people outside the organization to groups** (Разрешить владельцам добавлять в группы людей извне организации).</span><span class="sxs-lookup"><span data-stu-id="b3543-113">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>


![Снимок экрана, показывающий панель групп Office 365 с включенными параметрами "Let group members outside the organization access group content" (Предоставить участникам групп доступ к контенту групп извне организации) и "Let group owners add people outside the organization to groups" (Разрешить владельцам добавлять в группы людей извне организации).](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a><span data-ttu-id="b3543-115">Включение общего доступа в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b3543-115">Enable sharing in SharePoint Online</span></span>

<span data-ttu-id="b3543-116">Параметр "Общий доступ" в SharePoint Online позволяет добавлять гостей в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="b3543-116">The Sharing option in SharePoint Online allows guests to be added to your organization.</span></span> <span data-ttu-id="b3543-117">По умолчанию он включен.</span><span class="sxs-lookup"><span data-stu-id="b3543-117">By default, neither option is enabled.</span></span> <span data-ttu-id="b3543-118">Сведения об отключении этого параметра см. в разделе [Включение и отключение параметра общего доступа](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span><span class="sxs-lookup"><span data-stu-id="b3543-118">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
   <span data-ttu-id="b3543-119">Администраторы могут создать гостевые учетные записи в Azure Active Directory независимо от параметров внешнего общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b3543-119">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="b3543-120">Если внешний общий доступ отключен, гостевые учетные записи может создавать только администратор.</span><span class="sxs-lookup"><span data-stu-id="b3543-120">If external sharing is off, only an admin can create guest accounts.</span></span> 
    

> [!IMPORTANT]
> <span data-ttu-id="b3543-121">При отключенном параметре "Общий доступ" функция гостевого доступа не работает.</span><span class="sxs-lookup"><span data-stu-id="b3543-121">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="b3543-122">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3543-122">Turn on or off guest access to Microsoft Teams</span></span>
<span data-ttu-id="b3543-123"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="b3543-123"></span></span>

<span data-ttu-id="b3543-124">Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="b3543-124">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="b3543-125">Параметры гостей задаются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3543-125">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="b3543-126">Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="b3543-126">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="b3543-127">Если пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду, вероятнее всего, что гостевой доступ еще не включен либо соответствующие параметры еще не вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="b3543-127">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>



1. <span data-ttu-id="b3543-128">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="b3543-128">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="b3543-129">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="b3543-129">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Войдите в Office 365, перейдите в Центр администрирования Office 365, выберите "Параметры" и затем "Services &amp; add-ins" (Службы и надстройки).](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="b3543-131">Выберите **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b3543-131">Select **Microsoft Teams**.</span></span>
    
     ![Снимок экрана, показывающий параметр для надстройки Microsoft Teams, выбранный в Центре администрирования Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="b3543-133">В поле **Select the user/license type you want to configure** (Выберите тип пользователя или лицензии для настройки) укажите параметр **Гость**.</span><span class="sxs-lookup"><span data-stu-id="b3543-133">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Снимок экрана надстройки Microsoft Teams, показывающий выбранную лицензию "Гость" и значение "Включить" для параметра Microsoft Teams.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="b3543-135">Выберите значение **Включить** для параметра **Turn Microsoft Teams on or off for all users of this type** (Включить или отключить Microsoft Teams для всех пользователей этого типа), чтобы включить Teams и гостевой доступ в организации, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b3543-135">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  


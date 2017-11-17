---
title: "Включение и отключение гостевого доступа для Microsoft Teams"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Включение и отключение гостевого доступа в Microsoft Teams"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a996f7cc9154d04870e4dea00da950d340de16e2
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="ab908-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab908-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================





  



<span data-ttu-id="ab908-104">Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="ab908-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="ab908-105">Параметры гостей задаются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ab908-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="ab908-106">Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="ab908-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="ab908-107">Если пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду, вероятнее всего, что гостевой доступ еще не включен либо соответствующие параметры еще не вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="ab908-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ab908-108">Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab908-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="ab908-109">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="ab908-109">For more information, see [Control guest access to Microsoft Teams](Teams-dependencies.md).</span></span>

1. <span data-ttu-id="ab908-110">Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="ab908-110">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="ab908-111">В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).</span><span class="sxs-lookup"><span data-stu-id="ab908-111">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Войдите в Office 365, перейдите в Центр администрирования Office 365, выберите "Параметры" и затем "Services &amp; add-ins" (Службы и надстройки).](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="ab908-113">Выберите **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="ab908-113">Select **Microsoft Teams**.</span></span>
    
     ![Снимок экрана, показывающий параметр для надстройки Microsoft Teams, выбранный в Центре администрирования Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="ab908-115">В поле **Select the user/license type you want to configure** (Выберите тип пользователя или лицензии для настройки) укажите параметр **Гость**.</span><span class="sxs-lookup"><span data-stu-id="ab908-115">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Снимок экрана надстройки Microsoft Teams, показывающий выбранную лицензию "Гость" и значение "Включить" для параметра Microsoft Teams.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="ab908-117">Выберите значение **Включить** для параметра **Turn Microsoft Teams on or off for all users of this type** (Включить или отключить Microsoft Teams для всех пользователей этого типа), чтобы включить Teams и гостевой доступ в организации, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab908-117">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  


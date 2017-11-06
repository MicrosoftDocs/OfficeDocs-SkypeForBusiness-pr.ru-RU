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
<a name="set-up-guest-access-to-microsoft-teams"></a>Настройка гостевого доступа в Microsoft Teams
======================================

Работа Microsoft Teams основана на Группах Office 365, а также SharePoint Online. Поэтому для использования гостевого доступа в Teams нужно также включить определенные параметры в Группах Office 365 и SharePoint Online.


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>Разрешение добавления гостей в Группах Office 365
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).
    
  
3. Выберите **Группы Office 365**.
    
     ![Группы Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. На странице "Группы Office 365" установите переключатель в положение **Включить** или **Отключить**, в зависимости от того, хотите ли вы разрешить владельцам групп доступ к группам Office 365 извне организации. Выберите значение **Включить** рядом с параметром **Let group owners add people outside the organization to groups** (Разрешить владельцам добавлять в группы людей извне организации).


![Снимок экрана, показывающий панель групп Office 365 с включенными параметрами "Let group members outside the organization access group content" (Предоставить участникам групп доступ к контенту групп извне организации) и "Let group owners add people outside the organization to groups" (Разрешить владельцам добавлять в группы людей извне организации).](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>Включение общего доступа в SharePoint Online

Параметр "Общий доступ" в SharePoint Online позволяет добавлять гостей в вашу организацию. По умолчанию он включен. Сведения об отключении этого параметра см. в разделе [Включение и отключение параметра общего доступа](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).
  
   Администраторы могут создать гостевые учетные записи в Azure Active Directory независимо от параметров внешнего общего доступа. Если внешний общий доступ отключен, гостевые учетные записи может создавать только администратор. 
    

> [!IMPORTANT]
> При отключенном параметре "Общий доступ" функция гостевого доступа не работает. 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Включение и отключение гостевого доступа для Microsoft Teams
<a name="bkmk_TurnonOrTurnOff"> </a>

Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей. 

Параметры гостей задаются в Azure Active Directory. Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов. Если пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду, вероятнее всего, что гостевой доступ еще не включен либо соответствующие параметры еще не вступили в силу.



1. Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. В меню навигации выберите **Параметры** и затем **Services &amp; add-ins** (Службы и надстройки).
    
     ![Войдите в Office 365, перейдите в Центр администрирования Office 365, выберите "Параметры" и затем "Services &amp; add-ins" (Службы и надстройки).](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. Выберите **Microsoft Teams**.
    
     ![Снимок экрана, показывающий параметр для надстройки Microsoft Teams, выбранный в Центре администрирования Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. В поле **Select the user/license type you want to configure** (Выберите тип пользователя или лицензии для настройки) укажите параметр **Гость**.
   
    ![Снимок экрана надстройки Microsoft Teams, показывающий выбранную лицензию "Гость" и значение "Включить" для параметра Microsoft Teams.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. Выберите значение **Включить** для параметра **Turn Microsoft Teams on or off for all users of this type** (Включить или отключить Microsoft Teams для всех пользователей этого типа), чтобы включить Teams и гостевой доступ в организации, а затем выберите **Сохранить**. 
    
  


---
title: Перемещение локальных пользователей в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Сводка: Узнайте, как перенос параметров пользователя и перемещение пользователей в Скайп для бизнеса в Интернет.'
ms.openlocfilehash: 352798c217cb7495134cb32996db783f7e498ded
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="ee565-103">Перемещение локальных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ee565-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="ee565-104">**Сводка:** Узнайте, как перенос параметров пользователя и перемещение пользователей в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="ee565-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="ee565-p101">Перед переносом пользователей в Office 365 необходимо убедиться, что учетные записи пользователей синхронизированы с облачной средой, и назначить им лицензию. Для этого используется Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee565-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="ee565-107">Чтобы убедиться, что локальная учетная запись пользователя синхронизирована с Office 365, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ee565-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="ee565-108">Используя учетную запись администратора клиента, откройте [Центр администрирования Office 365](https://portal.office.com/) для клиента.</span><span class="sxs-lookup"><span data-stu-id="ee565-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>  <span data-ttu-id="ee565-109">Учетные записи администратора клиента следует предоставить Скайп для бизнес-роли администратора и роль управления пользователя (или роль глобального администратора) для выполнения этой функции в Office 365</span><span class="sxs-lookup"><span data-stu-id="ee565-109">Tenant admin accounts should be granted both the Skype for Business Admin Role and the User Management Role (or the Global Admin role) to perform this function in Office 365</span></span>
    
2. <span data-ttu-id="ee565-110">На панели навигации слева щелкните элемент **Пользователи**, а затем **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ee565-110">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="ee565-111">Нажмите **Поиск пользователя** и введите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee565-111">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="ee565-112">Убедитесь, что пользователь отображается со статусом **Синхронизировано с Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ee565-112">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="ee565-113">Если пользователь еще не синхронизирован, следующая автоматическая синхронизация произойдет через три часа.</span><span class="sxs-lookup"><span data-stu-id="ee565-113">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="ee565-114">Можно также принудительно синхронизацию быстрее.</span><span class="sxs-lookup"><span data-stu-id="ee565-114">You can also force a synchronization sooner.</span></span> <span data-ttu-id="ee565-115">Для получения дополнительных сведений см [Принудительная синхронизация службы каталогов](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span><span class="sxs-lookup"><span data-stu-id="ee565-115">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="ee565-116">Назначение лицензии в Office 365, видеть [Назначение лицензий для Office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="ee565-116">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="ee565-117">Перенос параметров пользователя в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="ee565-117">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="ee565-118">Прежде чем начать, миграция пользователей в Скайп для бизнеса в Интернет, следует создать резервную копию данных пользователя, связанных с учетных записей для перемещения.</span><span class="sxs-lookup"><span data-stu-id="ee565-118">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="ee565-119">Вместе с учетной записью перемещаются не все данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee565-119">Not all user data is moved with the user account.</span></span> <span data-ttu-id="ee565-120">Сведения, можно [резервного копирования и восстановления требования: данные](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span><span class="sxs-lookup"><span data-stu-id="ee565-120">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="ee565-p105">Параметры пользователя перемещаются вместе с учетной записью пользователя. Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee565-p105">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="ee565-123">Перемещение пользователей в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="ee565-123">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="ee565-124">Перед началом переноса данных пользователей в Скайп для бизнеса в Интернет, можно переместить несколько пилотных пользователей, чтобы убедиться в том, что ваша среда настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="ee565-124">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="ee565-125">Это также позволяет предварительно проверить правильность работы служб и компонентов.</span><span class="sxs-lookup"><span data-stu-id="ee565-125">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="ee565-126">Чтобы переместить локального пользователя вашего Скайп для бизнеса интерактивного клиента, выполните следующие командлеты в Скайп оболочки управления Business Server, используя учетные данные администратора для клиента Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee565-126">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="ee565-127">Замените "username@contoso.com" на информацию о перемещаемом пользователе.</span><span class="sxs-lookup"><span data-stu-id="ee565-127">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="ee565-128">Перемещение пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ee565-128">Move users to Skype for Business Online</span></span>

<span data-ttu-id="ee565-129">Можно переместить несколько пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) с параметром - фильтра для выбора пользователей, с помощью определенное свойство, назначенные учетные записи пользователей, такие как RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="ee565-129">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="ee565-130">Затем можно передать возвращенные пользователям командлета [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ee565-130">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="ee565-131">Можно также использовать параметр - OU для получения всех пользователей в указанном Подразделении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ee565-131">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="ee565-132">Проверка пользовательских параметров и функций</span><span class="sxs-lookup"><span data-stu-id="ee565-132">Verify online user settings and features</span></span>

<span data-ttu-id="ee565-133">Можно проверить успешность перемещения пользователя следующими способами:</span><span class="sxs-lookup"><span data-stu-id="ee565-133">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="ee565-p109">Просмотреть состояние пользователя в панели управления Skype для бизнеса: визуальные индикаторы для локальных и сетевых пользователей различаются.</span><span class="sxs-lookup"><span data-stu-id="ee565-p109">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="ee565-136">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ee565-136">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```



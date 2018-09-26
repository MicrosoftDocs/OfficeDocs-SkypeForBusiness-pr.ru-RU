---
title: Перемещение локальных пользователей в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Сводка: Узнайте, как перенос параметров пользователя и перемещение пользователей в Скайп для бизнеса в Интернет.'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030751"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="52fcd-103">Перемещение локальных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="52fcd-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="52fcd-104">**Сводка:** Узнайте, как перенос параметров пользователя и перемещение пользователей в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="52fcd-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>

<span data-ttu-id="52fcd-105">Прежде чем фактически миграции пользователя в Office 365, следует убедиться, что учетные записи пользователей синхронизироваться с облаком и назначить ему лицензию.</span><span class="sxs-lookup"><span data-stu-id="52fcd-105">Before actually moving a user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license.</span></span> <span data-ttu-id="52fcd-106">Для этого используется Центр администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="52fcd-106">To do this, you use the Office 365 Admin Center.</span></span>

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="52fcd-107">Чтобы убедиться, что локальная учетная запись пользователя синхронизирована с Office 365, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="52fcd-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="52fcd-108">С помощью учетной записи администратора клиента, откройте Центр администрирования Office 365 для клиента.</span><span class="sxs-lookup"><span data-stu-id="52fcd-108">Using a tenant admin account, open the Office 365 admin center for your tenant.</span></span>  <span data-ttu-id="52fcd-109">Учетные записи администратора клиента следует предоставить Скайп для бизнес-роли администратора и роль управления пользователя (или роль глобального администратора) для выполнения этой функции в Office 365.</span><span class="sxs-lookup"><span data-stu-id="52fcd-109">Tenant admin accounts should be granted both the Skype for Business Admin Role and the User Management Role (or the Global Admin role) to perform this function in Office 365.</span></span>

2. <span data-ttu-id="52fcd-110">На панели навигации слева щелкните **Пользователи**и нажмите кнопку **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="52fcd-110">On the left navigation pane, click **Users**, and then click **Active Users**.</span></span>

3. <span data-ttu-id="52fcd-111">Нажмите **Поиск пользователя** и введите имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="52fcd-111">Click **Search for a User**, and type the name of the user.</span></span>

4. <span data-ttu-id="52fcd-112">Убедитесь, что появится пользователя и, что их состояние является **Synched с Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="52fcd-112">Confirm that you see the user and that their status is **Synched with Active Directory**.</span></span>

    <span data-ttu-id="52fcd-113">Если пользователь еще не синхронизирован, следующая автоматическая синхронизация произойдет через три часа.</span><span class="sxs-lookup"><span data-stu-id="52fcd-113">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="52fcd-114">Можно также принудительно синхронизацию быстрее.</span><span class="sxs-lookup"><span data-stu-id="52fcd-114">You can also force a synchronization sooner.</span></span> <span data-ttu-id="52fcd-115">Для получения дополнительных сведений см [Принудительная синхронизация службы каталогов](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span><span class="sxs-lookup"><span data-stu-id="52fcd-115">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>

<span data-ttu-id="52fcd-116">Назначение лицензии в Office 365, видеть [Назначение лицензий для пользователей в Office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="52fcd-116">To assign the license in Office 365, see [Assign licenses to users in Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="52fcd-117">Перенос параметров пользователя в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52fcd-117">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="52fcd-118">Перед миграции пользователей в Скайп для бизнеса в Интернет, необходимо выполнить резервное копирование пользователя данные, связанные с учетными записями, чтобы переместить.</span><span class="sxs-lookup"><span data-stu-id="52fcd-118">Before you migrate users to Skype for Business Online, you should back up the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="52fcd-119">Вместе с учетной записью перемещаются не все данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="52fcd-119">Not all user data is moved with the user account.</span></span> <span data-ttu-id="52fcd-120">Сведения, можно [резервного копирования и восстановления требования: данные](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span><span class="sxs-lookup"><span data-stu-id="52fcd-120">For information, see [Backup and Restoration Requirements: Data](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>

<span data-ttu-id="52fcd-p105">Параметры пользователя перемещаются вместе с учетной записью пользователя. Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="52fcd-p105">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>

## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="52fcd-123">Перемещение пользователей в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="52fcd-123">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="52fcd-124">Перед перемещением пользователей в Скайп для бизнеса в Интернет, можно переместить несколько пилотных пользователей, чтобы убедиться в том, что ваша среда настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="52fcd-124">Before you move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="52fcd-125">Это также позволяет предварительно проверить правильность работы служб и компонентов.</span><span class="sxs-lookup"><span data-stu-id="52fcd-125">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="52fcd-126">Чтобы переместить локального пользователя вашего Скайп для бизнеса интерактивного клиента, выполните следующие командлеты в Скайп оболочки управления Business Server, используя учетные данные администратора для клиента Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="52fcd-126">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="52fcd-127">Замените «username@contoso.com» данные для пользователя, который требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="52fcd-127">Replace "username@contoso.com" with the information for the user you want to move.</span></span>

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="52fcd-128">Перемещение пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="52fcd-128">Move users to Skype for Business Online</span></span>

<span data-ttu-id="52fcd-129">Можно переместить несколько пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) с параметром - фильтра для выбора пользователей, с помощью определенное свойство, назначенные учетные записи пользователей, такие как RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="52fcd-129">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="52fcd-130">Затем можно передать возвращенные пользователям командлета [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="52fcd-130">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example:</span></span>

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

<span data-ttu-id="52fcd-131">Можно также использовать параметр - OU для получения всех пользователей в указанном Подразделении, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="52fcd-131">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example:</span></span>

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="52fcd-132">Проверка пользовательских параметров и функций</span><span class="sxs-lookup"><span data-stu-id="52fcd-132">Verify online user settings and features</span></span>

<span data-ttu-id="52fcd-133">Можно проверить успешность перемещения пользователя следующими способами:</span><span class="sxs-lookup"><span data-stu-id="52fcd-133">You can verify that the user was moved successfully in the following ways:</span></span>

- <span data-ttu-id="52fcd-p109">Просмотреть состояние пользователя в панели управления Skype для бизнеса: визуальные индикаторы для локальных и сетевых пользователей различаются.</span><span class="sxs-lookup"><span data-stu-id="52fcd-p109">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

- <span data-ttu-id="52fcd-136">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="52fcd-136">Run the following cmdlet:</span></span>

  ```
  Get-CsUser -Identity
  ```



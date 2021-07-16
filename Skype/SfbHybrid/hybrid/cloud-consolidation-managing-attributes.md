---
title: Решение об управлении атрибутами после вывода из эксплуатации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этой статье описывается управление атрибутами после вывода из эксплуатации локальной среды.
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53459007"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="f0e02-103">Решение об управлении атрибутами после вывода из эксплуатации</span><span class="sxs-lookup"><span data-stu-id="f0e02-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="f0e02-104">По умолчанию все пользователи, которые ранее были включены для Skype для бизнеса Server и впоследствии перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальном Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0e02-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="f0e02-105">Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и потенциально номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e02-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="f0e02-106">Если требуется изменить любой из атрибутов msRTCSIP, эти изменения необходимо внести в локальном Active Directory, а затем синхронизировать его с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e02-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="f0e02-107">Однако после удаления Skype для бизнеса Server, Skype для бизнеса Server средства управления этими атрибутами будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="f0e02-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="f0e02-108">Существует два варианта обработки этой ситуации:</span><span class="sxs-lookup"><span data-stu-id="f0e02-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="f0e02-109">Оставьте пользователей, включенных для Skype для бизнеса серверных учетных записей, как есть, и управляйте атрибутами msRTCSIP с помощью средств Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0e02-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="f0e02-110">Это обеспечивает отсутствие потери службы для перенесенных пользователей и позволяет легко удалить развертывание Skype для бизнеса Server путем удаления (например, удаления) серверов без полного вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="f0e02-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="f0e02-111">Однако новые лицензированные пользователи не будут иметь эти атрибуты, заполняемые в локальном каталоге Active Directory, и им необходимо управлять в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f0e02-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="f0e02-112">Очистить все атрибуты msRTCSIP от перенесенных пользователей в локальном Каталоге Active Directory и управлять этими атрибутами с помощью сетевых средств.</span><span class="sxs-lookup"><span data-stu-id="f0e02-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="f0e02-113">Этот метод позволяет использовать последовательный подход к управлению для существующих и новых пользователей, однако он потенциально может привести к временной потере службы во время локального процесса вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="f0e02-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="f0e02-114">Метод 1 . Управление SIP-адресами и номерами телефонов для пользователей Active Directory</span><span class="sxs-lookup"><span data-stu-id="f0e02-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="f0e02-115">Администраторы могут управлять пользователями, которые ранее были перемещены из локального Skype для бизнеса Server в облако, даже после вывода из эксплуатации локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="f0e02-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="f0e02-116">Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sip-адрес или номер телефона уже имеет значение в локальном Active Directory), необходимо сделать это в локальном Active Directory и позволить значению (s) перетекать в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e02-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="f0e02-117">Для этого не требуется локальное Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f0e02-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="f0e02-118">Скорее, эти атрибуты можно изменить непосредственно в локальном Active Directory, используя либо оснастку MMC пользователей Active Directory и компьютеров (как показано ниже), либо с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0e02-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="f0e02-119">Если вы используете оснастку MMC, откройте страницу свойств пользователя, нажмите кнопку Редактор атрибута и найдите соответствующие атрибуты для изменения:</span><span class="sxs-lookup"><span data-stu-id="f0e02-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="f0e02-120">Чтобы изменить SIP-адрес пользователя, измените `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="f0e02-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f0e02-121">Если атрибут `ProxyAddresses` содержит SIP-адрес, также обнови это значение в качестве наилучшей практики.</span><span class="sxs-lookup"><span data-stu-id="f0e02-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="f0e02-122">Несмотря на то, что адрес SIP в случае заполнения игнорируется O365, он может использоваться другими компонентами `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` локального использования.</span><span class="sxs-lookup"><span data-stu-id="f0e02-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="f0e02-123">Чтобы изменить телефонный номер пользователя, `msRTCSIP-Line` *измените, если он уже имеет значение*.</span><span class="sxs-lookup"><span data-stu-id="f0e02-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Средство для пользователей и компьютеров Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="f0e02-125">Если у пользователя изначально не было значения для локального перед перемещением, можно изменить номер телефона с помощью параметра `msRTCSIP-Line` в командлете `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) в модуле Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0e02-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="f0e02-126">Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибрида, и управлять этими пользователями можно непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="f0e02-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="f0e02-127">Если вам удобно использовать сочетание этих методов, а также оставить атрибуты msRTCSIP на месте в локальном Active Directory, вы можете просто повторно образ локального Skype для бизнеса серверов.</span><span class="sxs-lookup"><span data-stu-id="f0e02-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="f0e02-128">Однако если вы предпочитаете очистить все атрибуты msRTCSIP и сделать традиционный Skype для бизнеса Server, используйте Метод 2.</span><span class="sxs-lookup"><span data-stu-id="f0e02-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="f0e02-129">Метод 2 . Skype для бизнеса для всех локального пользователя в Active Directory</span><span class="sxs-lookup"><span data-stu-id="f0e02-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="f0e02-130">Этот параметр требует дополнительных усилий и надлежащего планирования, так как пользователи, которые ранее были перемещены из локального Skype для бизнеса Server в облако, должны быть повторно продвинуты.</span><span class="sxs-lookup"><span data-stu-id="f0e02-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="f0e02-131">Эти пользователи могут быть классифицированы на две разные категории: пользователи без телефонная система и пользователи с телефонная система.</span><span class="sxs-lookup"><span data-stu-id="f0e02-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="f0e02-132">Пользователи с телефонная система будут испытывать временную потерю телефонной службы в рамках перехода номера телефона от управления в локальном Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="f0e02-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="f0e02-133">**Перед началом массовых операций рекомендуется выполнить пилотную работу с небольшим числом пользователей с телефонная система пользователями.**</span><span class="sxs-lookup"><span data-stu-id="f0e02-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="f0e02-134">Для больших развертывания пользователи могут обрабатываться в небольших группах в разных окнах времени.</span><span class="sxs-lookup"><span data-stu-id="f0e02-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="f0e02-135">Этот процесс прост для пользователей, у которых есть совпадающий sip-адрес и UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="f0e02-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="f0e02-136">Для организаций, у пользователей с не совпадающих значений между этими двумя атрибутами, необходимо принять дополнительные меры, как отмечено ниже, для плавного перехода.</span><span class="sxs-lookup"><span data-stu-id="f0e02-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="f0e02-137">Если вы настроили конечные точки гибридного приложения для автоспутников или очередей вызовов, не забудьте переместить эти конечные точки в Microsoft 365 до вывода из эксплуатации Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f0e02-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="f0e02-138">Подтверждение следующего локального Skype для бизнеса PowerShell возвращает пустой результат.</span><span class="sxs-lookup"><span data-stu-id="f0e02-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="f0e02-139">Пустой результат означает, что пользователи не находятся в локальном помещении и не были перемещены в Microsoft 365 или отключены:</span><span class="sxs-lookup"><span data-stu-id="f0e02-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="f0e02-140">Запись текущего номера телефонов пользователей (LineUri), UserPrincipalName и связанных с ними данных, путем выполнения следующего локального Skype для бизнеса Server PowerShell для экспорта пользовательских данных:</span><span class="sxs-lookup"><span data-stu-id="f0e02-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="f0e02-141">Перед открытием SfbUserSettings.csv файл и подтверждение успешного экспорта всех пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="f0e02-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="f0e02-142">Рекомендуется хранить копию этого файла.</span><span class="sxs-lookup"><span data-stu-id="f0e02-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="f0e02-143">Не используйте этот файл в следующих действиях для обработки пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e02-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="f0e02-144">Создайте файл с группой пользователей, который будет использоваться в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="f0e02-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="f0e02-145">После успешного завершения работы первой группы пользователей приступим к следующей группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e02-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="f0e02-146">В приведенном ниже примере группы пользователей выбираются в алфавитном порядке, но можно фильтровать пользователей на основе критериев, которые соответствуют тому, как вы хотите обрабатывать пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e02-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="f0e02-147">Перед открытием SfbUsers.csv файл и подтверждение успешного экспорта пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="f0e02-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="f0e02-148">На более позднем этапе вам потребуется LineUri (номер телефона), UserPrincipalName, SamAccountName и SipAddress из этого файла.</span><span class="sxs-lookup"><span data-stu-id="f0e02-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="f0e02-149">Удаление сведений о атрибутах, связанных Skype для бизнеса Server из active Directory для набора пользователей, которые вы готовы обновить.</span><span class="sxs-lookup"><span data-stu-id="f0e02-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="f0e02-150">Существует 2 шага к этому процессу, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f0e02-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="f0e02-151">После следующего цикла AAD Sync после запуска этого шага пользователи с телефонная система, которые ранее были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность выполнять и принимать вызовы до тех пор, пока шаг 8 не будет успешно завершен и подтвержден на шаге 9.</span><span class="sxs-lookup"><span data-stu-id="f0e02-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="f0e02-152">Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эта информация необходима для этого шага.</span><span class="sxs-lookup"><span data-stu-id="f0e02-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="f0e02-153">Далее, для того же набора пользователей, очистить значение msRTCSIP-DeploymentLocator с помощью локального Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0e02-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="f0e02-154">Запустите следующий локальном модуле Active Directory для командлета Windows PowerShell, чтобы добавить значение SIP-адреса обратно в локальное прокси-серверы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0e02-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="f0e02-155">Это позволит предотвратить проблемы с интероперабельностью, которые зависят от этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="f0e02-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="f0e02-156">Запуск Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="f0e02-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="f0e02-157">Подождите, пока подготовка пользователей завершится.</span><span class="sxs-lookup"><span data-stu-id="f0e02-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="f0e02-158">Вы можете отслеживать ход подготовка пользователей, запуская следующую команду Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0e02-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="f0e02-159">Следующая команда Skype для бизнеса PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="f0e02-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="f0e02-160">Выполните следующую команду Skype для бизнеса PowerShell, чтобы назначить номера телефонов и включить пользователей для телефонная система:</span><span class="sxs-lookup"><span data-stu-id="f0e02-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="f0e02-161">Если у вас Skype для бизнеса конечные точки (Skype клиенты или 3-й телефон участника), вам также необходимо установить -HostedVoiceMail для $true.</span><span class="sxs-lookup"><span data-stu-id="f0e02-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="f0e02-162">Если ваша организация использует только Teams конечные точки для пользователей с включенной голосовой поддержкой, этот параметр не применим к пользователям.</span><span class="sxs-lookup"><span data-stu-id="f0e02-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="f0e02-163">Подтвердит правильность телефонная система пользователей с функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="f0e02-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="f0e02-164">Следующая команда Skype для бизнеса PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="f0e02-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="f0e02-165">Повторите действия от 3 до 9 до тех пор, пока все пользователи не будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="f0e02-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="f0e02-166">Подтверди, что все пользователи успешно обработаны, запуская следующие две команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0e02-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="f0e02-167">Локальное Skype для бизнеса Server powerShell:</span><span class="sxs-lookup"><span data-stu-id="f0e02-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="f0e02-168">Skype для бизнеса Команда Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0e02-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="f0e02-169">После завершения всех действий в методе 2 см. в рубке Перемещение [](decommission-remove-on-prem.md) конечных точек гибридного приложения из локального в интернет и удаление локального Skype для бизнеса Server дополнительных действий по удалению Skype для бизнеса Server локального развертывания. [](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="f0e02-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="f0e02-170">См. также</span><span class="sxs-lookup"><span data-stu-id="f0e02-170">See also</span></span>

- [<span data-ttu-id="f0e02-171">Консолидация облаков для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f0e02-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="f0e02-172">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f0e02-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)


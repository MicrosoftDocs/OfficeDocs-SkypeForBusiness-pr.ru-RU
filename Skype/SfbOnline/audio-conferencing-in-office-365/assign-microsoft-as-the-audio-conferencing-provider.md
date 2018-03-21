---
title: "Назначение Майкрософт в качестве поставщика услуг аудиоконференций"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/23/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: 0193743f9dd2ed6486d93d55c881f3e582e4eb04
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="e925d-104">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e925d-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="e925d-105">Поставщика аудиоконференций предоставляет *bridge конференции*.</span><span class="sxs-lookup"><span data-stu-id="e925d-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="e925d-106">Мост конференции предоставляет телефонные номера телефонов, контакты и конференции идентификаторы для собрания, которые создаются.</span><span class="sxs-lookup"><span data-stu-id="e925d-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="e925d-107">Вам потребуется только назначить поставщика аудиоконференций для пользователей, планирующих или проводящих собрания Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e925d-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="e925d-108">Если вы хотите могут видеть **Microsoft** , перечисленных в качестве звукового поставщика, необходимо назначить лицензию на **Аудиоконференций** пользователя.</span><span class="sxs-lookup"><span data-stu-id="e925d-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e925d-109">При назначении лицензии **Аудиоконференций** человека, который не имеет поставщика аудиоконференций сторонних производителей Microsoft автоматически назначается в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e925d-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="e925d-110">Можно [назначить независимых производителей в качестве поставщика аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md) при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e925d-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="e925d-111">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e925d-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="e925d-112">Использование Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e925d-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="e925d-113">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e925d-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e925d-p104">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="e925d-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="e925d-116">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e925d-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="e925d-117">На панели действий нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e925d-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="e925d-118">На странице "Свойства" для пользователя, в разделе **имя поставщика**выберите **Microsoft** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e925d-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e925d-119">Так как вы используете Microsoft в качестве поставщика аудиоконференций и существует несколько телефонных номеров, можно использовать раскрывающегося списка **номер счета по умолчанию** для выбора звукового номер по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e925d-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="e925d-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e925d-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="e925d-121">Применение сценария Windows PowerShell для небольшого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="e925d-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="e925d-122">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e925d-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="e925d-p105">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="e925d-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="e925d-125">Один или несколько из представленных ниже сценариев можно сохранить как файл сценария PowerShell, а затем выполнить.</span><span class="sxs-lookup"><span data-stu-id="e925d-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="e925d-126">Чтобы изменить поставщик в корпорацию Майкрософт для небольшого числа пользователей, можно использовать [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span><span class="sxs-lookup"><span data-stu-id="e925d-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="e925d-127">**Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="e925d-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="e925d-128">**Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="e925d-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="e925d-129">Применение сценария Windows PowerShell для большого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="e925d-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="e925d-130">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e925d-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="e925d-p106">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="e925d-p106">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="e925d-133">Один или несколько из представленных ниже сценариев можно сохранить как файл сценария PowerShell, а затем выполнить.</span><span class="sxs-lookup"><span data-stu-id="e925d-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="e925d-134">**Пример 1.** В этом примере указанный сценарий позволяет сменить поставщика услуг аудиоконференций с Intercall (или другого поставщика) на **Майкрософт** для большого количества пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e925d-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="e925d-135">Здесь приведен сценарий.</span><span class="sxs-lookup"><span data-stu-id="e925d-135">Here is the script:</span></span>

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="e925d-136">Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="e925d-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="e925d-137">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e925d-137">What else should I know?</span></span>

- <span data-ttu-id="e925d-138">Для пользователя можно назначить только одного поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e925d-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="e925d-p107">Сменить поставщика аудиоконференций можно в любой момент. Дополнительные сведения см. в статье [Назначение стороннего поставщика услуг аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e925d-p107">You can change the audio conferencing provider from Microsoft to a third-party provider at any time. To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="e925d-p108">В организации разные пользователи могут использовать разных поставщиков аудиоконференций. Однако в этом случае настройка и управление усложняются.</span><span class="sxs-lookup"><span data-stu-id="e925d-p108">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider. But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e925d-143">See also</span><span class="sxs-lookup"><span data-stu-id="e925d-143">Related topics</span></span>

[<span data-ttu-id="e925d-144">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e925d-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="e925d-145">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e925d-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


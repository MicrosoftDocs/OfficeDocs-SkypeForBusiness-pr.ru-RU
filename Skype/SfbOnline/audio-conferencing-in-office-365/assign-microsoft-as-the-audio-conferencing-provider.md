---
title: Назначение Майкрософт в качестве поставщика услуг аудиоконференций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237765"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="577cd-103">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="577cd-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="577cd-104">Чтобы использовать аудиоконференцию Microsoft 365 или Office 365 с Skype для бизнеса и Microsoft Teams, пользователям в организации должна быть назначена лицензия на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="577cd-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="577cd-105">Дополнительные [сведения о лицензировании](try-or-purchase-audio-conferencing-in-office-365.md) и их стоимости см. в Microsoft 365 или Office 365 аудиоконференцию в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="577cd-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="577cd-106">Аудиоконференция Microsoft предоставляет телефонные номера для подключения, ПИН-коды и идентификаторы конференции, которые могут использовать участники собрания для подсоединения к собраниям организации.</span><span class="sxs-lookup"><span data-stu-id="577cd-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="577cd-107">Назначить Майкрософт в качестве поставщика аудиоконференций нужно только для тех, кто будет планировать или Skype для бизнеса или Microsoft Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="577cd-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="577cd-108">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="577cd-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Значок с логотипом Skype для бизнеса логотипом](../images/sfb-logo-30x30.png) <span data-ttu-id="577cd-110">Использование Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="577cd-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="577cd-111">Перейдите на **устаревший Microsoft Teams Центре**  >  **администрирования**.</span><span class="sxs-lookup"><span data-stu-id="577cd-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="577cd-112">В центре **Skype для бизнеса** администрирования на левой навигации перейдите в аудиоконференцию . </span><span class="sxs-lookup"><span data-stu-id="577cd-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="577cd-113">Если отображается баннер с уведомлением о том, что имеются пользователи с назначенной лицензией **Аудиоконференции**, однако поставщиком услуг аудиоконференций не является Майкрософт, нажмите **Щелкните здесь, чтобы переместить их**.</span><span class="sxs-lookup"><span data-stu-id="577cd-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="577cd-114">Если этот баннер не отображается, в **центре администрирования Skype для бизнеса** нажмите **Пользователи**, затем выберите фильтр **Пользователи, которые готовы для перемещения в аудиоконференцию**.</span><span class="sxs-lookup"><span data-stu-id="577cd-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="577cd-115">На странице свойств пользователя в списке **Имя** поставщика выберите **Microsoft** в списке.</span><span class="sxs-lookup"><span data-stu-id="577cd-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="577cd-116">Так как в качестве поставщика аудиоконференций используется Майкрософт и существует  несколько номеров телефонов, в списке Платный номер по умолчанию можно выбрать номер аудио по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="577cd-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="577cd-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="577cd-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="577cd-118">Применение сценария Windows PowerShell для небольшого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="577cd-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="577cd-119">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="577cd-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="577cd-p104">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="577cd-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="577cd-122">Чтобы сменить поставщика на Майкрософт для небольшого количества пользователей, используйте для этого [cmdlet Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="577cd-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="577cd-123">Применение сценария Windows PowerShell для большого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="577cd-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="577cd-124">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="577cd-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="577cd-p105">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="577cd-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="577cd-127">Можно сохранить следующий сценарий в качестве файла сценария PowerShell и затем запустить его с помощью любого из параметров ввода.</span><span class="sxs-lookup"><span data-stu-id="577cd-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="577cd-128">**Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="577cd-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="577cd-129">**Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="577cd-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="577cd-130">**Пример 3.** В этом примере с помощью этого сценария можно изменить поставщика аудиоконференций с Intercall (или другого поставщика) на **Майкрософт** для большого количества пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="577cd-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="577cd-131">Здесь приведен сценарий.</span><span class="sxs-lookup"><span data-stu-id="577cd-131">Here is the script:</span></span>

  ```PowerShell
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
<span data-ttu-id="577cd-132">Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="577cd-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="577cd-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="577cd-133">Related topics</span></span>
<span data-ttu-id="577cd-134">[Попробуйте или приобретйте](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) аудиоконференцию в Microsoft 365 или Office 365 
 [Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="577cd-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

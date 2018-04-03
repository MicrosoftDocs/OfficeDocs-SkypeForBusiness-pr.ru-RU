---
title: Назначение Майкрософт в качестве поставщика услуг аудиоконференций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
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
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="9ef1a-104">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="9ef1a-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="9ef1a-105">Для использования конференц-связи звук в Office 365 с помощью Скайп для бизнеса и группами Майкрософт, пользователи в вашей организации должны иметь лицензию звук конференц-связи, назначенные им.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-105">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="9ef1a-106">Для получения дополнительных сведений о лицензировании и также сколько это стоит видеть [Попробуйте или Покупка Audio конференция в Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="9ef1a-106">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="9ef1a-107">Аудиоконференции Майкрософт предоставляет телефонные номера телефонов, контакты и конференции идентификаторы, которые могут использоваться с участников собрания на присоединение к собраниям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-107">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="9ef1a-108">Только необходимо назначить Microsoft в качестве поставщика аудиоконференций для тех, кто собирается расписание или привести Скайп для бизнеса или группами Майкрософт собраний.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-108">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

<span data-ttu-id="9ef1a-109">Если лицензия **Microsoft аудиоконференций** назначается пользователь, который не имеет поставщика аудиоконференций, в **корпорацию Майкрософт** автоматически устанавливается пользователя поставщика и у вас нет необходимости выполнять дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-109">If a **Microsoft Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to **Microsoft** and you don't have to do anything else.</span></span> <span data-ttu-id="9ef1a-110">Если пользователь уже есть поставщика аудиоконференций, необходимо изменить поставщика пользователя в корпорацию Майкрософт после назначения их лицензии аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-110">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an Audio Conferencing license.</span></span>

<span data-ttu-id="9ef1a-111">Если необходимо иметь возможность видеть Microsoft указано, что поставщик услуг аудиоконференций, необходимо назначить лицензию на аудиоконференций для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-111">If you want to be able to see Microsoft listed as the audio conferencing provider, you must assign an Audio Conferencing license to the user.</span></span>


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="9ef1a-112">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="9ef1a-112">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="9ef1a-113">Использование Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9ef1a-113">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="9ef1a-114">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ef1a-p105">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="9ef1a-117">В **Скайп по центру администрирования бизнеса**, в левой панели навигации перейдите к **аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="9ef1a-118">Если вы видите заголовка о том, что существуют пользователи, имеющие **Аудиоконференций** лицензия назначена, но не имеют Microsoft задаются в виде их поставщика аудиоконференций, но при этом, нажмите кнопку **щелкните здесь, чтобы переместить их**.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-118">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="9ef1a-119">Если нужная баннера в **Скайп по центру администрирования Business** щелкните **Пользователи**и выберите фильтр **пользователей готово для перемещения к аудиоконференции** .</span><span class="sxs-lookup"><span data-stu-id="9ef1a-119">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="9ef1a-120">На странице "Свойства" для пользователя, в разделе **имя поставщика**выберите **Microsoft** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-120">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ef1a-121">Так как вы используете Microsoft в качестве поставщика аудиоконференций и существует несколько телефонных номеров, можно использовать раскрывающегося списка **номер счета по умолчанию** для выбора звукового номер по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-121">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="9ef1a-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-122">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="9ef1a-123">Применение сценария Windows PowerShell для небольшого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="9ef1a-123">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="9ef1a-124">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="9ef1a-p107">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-p107">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="9ef1a-127">Чтобы изменить поставщик в корпорацию Майкрософт для небольшого числа пользователей, можно использовать командлет [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9ef1a-127">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="9ef1a-128">Применение сценария Windows PowerShell для большого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="9ef1a-128">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="9ef1a-129">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-129">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="9ef1a-p108">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-p108">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="9ef1a-132">Можно сохранить приведенный ниже сценарий как файл сценария PowerShell и запустите его с помощью любого из его входные параметры.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-132">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="9ef1a-133">**Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-133">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="9ef1a-134">**Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-134">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="9ef1a-135">**В примере 3:** В этом примере использовании этот сценарий для поставщика аудиоконференций из Intercall (или другого поставщика) в **корпорацию Майкрософт** для большое число пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-135">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="9ef1a-136">Здесь приведен сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ef1a-136">Here is the script:</span></span>

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
<span data-ttu-id="9ef1a-137">Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="9ef1a-137">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="9ef1a-138">See also</span><span class="sxs-lookup"><span data-stu-id="9ef1a-138">Related topics</span></span>

[<span data-ttu-id="9ef1a-139">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="9ef1a-139">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[<span data-ttu-id="9ef1a-140">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9ef1a-140">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


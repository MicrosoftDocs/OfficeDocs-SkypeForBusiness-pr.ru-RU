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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 934513c3f119044f05835e49fe73f8aba74de753
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703731"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="2dd1f-103">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="2dd1f-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="2dd1f-104">Для использования конференц-связи звук в Office 365 с помощью Скайп для бизнеса и группами Майкрософт, пользователи в вашей организации должны иметь лицензию звук конференц-связи, назначенные им.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="2dd1f-105">Для получения дополнительных сведений о лицензировании и также сколько это стоит видеть [Попробуйте или Покупка Audio конференция в Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="2dd1f-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="2dd1f-106">Аудиоконференции Майкрософт предоставляет телефонные номера телефонов, контакты и конференции идентификаторы, которые могут использоваться с участников собрания на присоединение к собраниям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="2dd1f-107">Только необходимо назначить Microsoft в качестве поставщика аудиоконференций для тех, кто собирается расписание или привести Скайп для бизнеса или группами Майкрософт собраний.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="2dd1f-108">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="2dd1f-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="2dd1f-110">Использование Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2dd1f-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="2dd1f-111">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="2dd1f-112">В **Скайп по центру администрирования бизнеса**, в левой панели навигации перейдите к **аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="2dd1f-113">Если вы видите заголовка о том, что существуют пользователи, имеющие **Аудиоконференций** лицензия назначена, но не имеют Microsoft задаются в виде их поставщика аудиоконференций, но при этом, нажмите кнопку **щелкните здесь, чтобы переместить их**.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="2dd1f-114">Если нужная баннера в **Скайп по центру администрирования Business** щелкните **Пользователи**и выберите фильтр **пользователей готово для перемещения к аудиоконференции** .</span><span class="sxs-lookup"><span data-stu-id="2dd1f-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="2dd1f-115">На странице "Свойства" для пользователя, в разделе **имя поставщика**выберите **Microsoft** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2dd1f-116">Так как вы используете Microsoft в качестве поставщика аудиоконференций и существует несколько телефонных номеров, можно использовать раскрывающегося списка **номер счета по умолчанию** для выбора звукового номер по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="2dd1f-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="2dd1f-118">Применение сценария Windows PowerShell для небольшого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="2dd1f-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="2dd1f-119">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="2dd1f-p104">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="2dd1f-122">Чтобы изменить поставщик в корпорацию Майкрософт для небольшого числа пользователей, можно использовать командлет [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2dd1f-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="2dd1f-123">Применение сценария Windows PowerShell для большого количества пользователей</span><span class="sxs-lookup"><span data-stu-id="2dd1f-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="2dd1f-124">Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="2dd1f-p105">При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="2dd1f-127">Можно сохранить приведенный ниже сценарий как файл сценария PowerShell и запустите его с помощью любого из его входные параметры.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="2dd1f-128">**Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="2dd1f-129">**Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="2dd1f-130">**В примере 3:** В этом примере использовании этот сценарий для поставщика аудиоконференций из Intercall (или другого поставщика) в **корпорацию Майкрософт** для большое число пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="2dd1f-131">Здесь приведен сценарий.</span><span class="sxs-lookup"><span data-stu-id="2dd1f-131">Here is the script:</span></span>

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
<span data-ttu-id="2dd1f-132">Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="2dd1f-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2dd1f-133">See also</span><span class="sxs-lookup"><span data-stu-id="2dd1f-133">Related topics</span></span>
<span data-ttu-id="2dd1f-134">[Попробуйте или Покупка Audio конференция в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Настройка Скайп для бизнеса в Интернет](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="2dd1f-134">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>


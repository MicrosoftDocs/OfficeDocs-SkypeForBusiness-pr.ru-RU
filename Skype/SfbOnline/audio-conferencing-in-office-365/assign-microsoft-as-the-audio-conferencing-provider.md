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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 982d0515468109d1adf8ac2d7f00cce36732faf7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620305"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Назначение Майкрософт в качестве поставщика услуг аудиоконференций

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Чтобы использовать аудиоконференцию в Microsoft 365 или Office 365 с Skype для бизнеса и Microsoft Teams, пользователям в организации должна быть назначена лицензия на аудиоконференцию. Дополнительные [сведения о лицензировании](try-or-purchase-audio-conferencing-in-office-365.md) и их стоимости см. в Microsoft 365 или Office 365 аудиоконференцию в Office 365.

Аудиоконференция Microsoft предоставляет телефонные номера для подключения, ПИН-коды и идентификаторы конференции, которые могут использовать участники собрания для подсоединения к собраниям организации. Назначить Майкрософт в качестве поставщика аудиоконференций нужно только для тех, кто будет планировать или Skype для бизнеса или Microsoft Teams собрания.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Назначение Майкрософт в качестве поставщика услуг аудиоконференций

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Значок с логотипом Skype для бизнеса логотипом](../images/sfb-logo-30x30.png) Использование Центра администрирования Skype для бизнеса

1. Перейдите на **устаревший Microsoft Teams Центре**  >  **администрирования**.
    
2. В центре **Skype для бизнеса** администрирования на левой навигации перейдите в аудиоконференцию . 
    
3. Если отображается баннер с уведомлением о том, что имеются пользователи с назначенной лицензией **Аудиоконференции**, однако поставщиком услуг аудиоконференций не является Майкрософт, нажмите **Щелкните здесь, чтобы переместить их**. Если этот баннер не отображается, в **центре администрирования Skype для бизнеса** нажмите **Пользователи**, затем выберите фильтр **Пользователи, которые готовы для перемещения в аудиоконференцию**.
    
4. На странице свойств пользователя в списке **Имя поставщика** выберите **Microsoft** в списке.
    
    > [!NOTE]
    > Так как в качестве поставщика аудиоконференций используется Майкрософт и существует  несколько номеров телефонов, в списке Платный номер по умолчанию можно выбрать номер звука по умолчанию для пользователя.
  
5. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Применение сценария Windows PowerShell для небольшого количества пользователей

Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.

> [!NOTE]
> При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика. 

  
Чтобы сменить поставщика на Майкрософт для небольшого количества пользователей, используйте для этого [cmdlet Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Применение сценария Windows PowerShell для большого количества пользователей
Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.

При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика. 
  
Можно сохранить следующий сценарий в качестве файла сценария PowerShell и затем запустить его с помощью любого из параметров ввода.

**Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Пример 3.** В этом примере с помощью этого сценария можно изменить поставщика аудиоконференций с Intercall (или другого поставщика) на **Майкрософт** для большого количества пользователей в организации.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Здесь приведен сценарий.

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
Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Статьи по теме
[Попробуйте или приобретйте](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) аудиоконференцию в Microsoft 365 или Office 365 
 [Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

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
ms.collection: Adm_Skype4B_Online
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
ms.openlocfilehash: d6c0f4f3a8f903ff180785214d3a4e987321a5b3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Назначение Майкрософт в качестве поставщика услуг аудиоконференций

Поставщика аудиоконференций предоставляет *bridge конференции*. Мост конференции предоставляет телефонные номера телефонов, контакты и конференции идентификаторы для собрания, которые создаются. Вам потребуется только назначить поставщика аудиоконференций для пользователей, планирующих или проводящих собрания Skype для бизнеса или Microsoft Teams.
  
Если вы хотите могут видеть **Microsoft** , перечисленных в качестве звукового поставщика, необходимо назначить лицензию на **Аудиоконференций** пользователя.
  
> [!NOTE]
> При назначении лицензии **Аудиоконференций** человека, который не имеет поставщика аудиоконференций сторонних производителей Microsoft автоматически назначается в качестве поставщика аудиоконференций. Можно [назначить независимых производителей в качестве поставщика аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md) при необходимости.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Назначение Майкрософт в качестве поставщика услуг аудиоконференций

### <a name="using-the-skype-for-business-admin-center"></a>Использование Центра администрирования Skype для бизнеса

1. Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.
    
    > [!NOTE]
    > При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика. 
  
2. В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.
    
3. На панели действий нажмите **Изменить**.
    
4. На странице "Свойства" для пользователя, в разделе **имя поставщика**выберите **Microsoft** в раскрывающемся списке.
    
    > [!NOTE]
    > Так как вы используете Microsoft в качестве поставщика аудиоконференций и существует несколько телефонных номеров, можно использовать раскрывающегося списка **номер счета по умолчанию** для выбора звукового номер по умолчанию для пользователя.
  
5. Нажмите кнопку **Сохранить**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Применение сценария Windows PowerShell для небольшого количества пользователей

Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.

> [!NOTE]
> При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика. 
  
Один или несколько из представленных ниже сценариев можно сохранить как файл сценария PowerShell, а затем выполнить.
  
Чтобы изменить поставщик в корпорацию Майкрософт для небольшого числа пользователей, можно использовать [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
**Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Применение сценария Windows PowerShell для большого количества пользователей
Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.

При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика. 
  
Один или несколько из представленных ниже сценариев можно сохранить как файл сценария PowerShell, а затем выполнить.

**Пример 1.** В этом примере указанный сценарий позволяет сменить поставщика услуг аудиоконференций с Intercall (или другого поставщика) на **Майкрософт** для большого количества пользователей в вашей организации.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Здесь приведен сценарий.

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
Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="what-else-should-i-know"></a>Дополнительные сведения

- Для пользователя можно назначить только одного поставщика аудиоконференций.
    
- Сменить поставщика аудиоконференций можно в любой момент. Дополнительные сведения см. в статье [Назначение стороннего поставщика услуг аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- В организации разные пользователи могут использовать разных поставщиков аудиоконференций. Однако в этом случае настройка и управление усложняются.
    
## <a name="related-topics"></a>See also

[Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](set-up-audio-conferencing.md)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
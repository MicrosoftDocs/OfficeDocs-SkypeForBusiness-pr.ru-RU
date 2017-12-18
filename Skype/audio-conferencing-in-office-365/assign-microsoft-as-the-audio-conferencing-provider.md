---
title: "Назначение Майкрософт в качестве поставщика услуг аудиоконференций"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# Назначение Майкрософт в качестве поставщика услуг аудиоконференций

> [!IMPORTANT]
> Данная статья переведена с помощью машинного перевода, см. Отказ от ответственности.  
  
К поставщику услуг аудиоконференций предоставляет  *моста конференции*  . Мост конференц предлагает конференц связи телефонные номера, контакты и идентификаторы конференций для собраний, созданные. Необходимо назначить людей, открыв планирование и проведение собраний группами Майкрософт или Skype для бизнеса к поставщику услуг аудиоконференций.
  
Если вы хотите могут видеть, что в списке **Microsoft** поставщиком аудио, необходимо назначить лицензии ** Аудиоконференций** для пользователя.
  
> [!NOTE]
> При назначении пользователю, у которого нет аудиоконференций стороннего поставщика услуг **Аудиоконференций** лицензии, автоматически назначается Microsoft в качестве поставщика услуг аудиоконференций. Вы можете при необходимости[Назначение стороннего поставщика услуг аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md) .
  
## Назначение Майкрософт в качестве поставщика услуг аудиоконференций

### Использование Центра администрирования Skype для бизнеса

1. Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.
    
    > [!NOTE]
    > При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.
  
2. В **Центр администрирования Skype для бизнеса**, на панели навигации слева перейдите по адресу **аудиоконференций** > **Пользователи**, а затем выберите пользователя из списка доступных пользователей.
    
3. На панели действий нажмите **Изменить**. 
    
4. На странице свойств пользователя в поле **имя поставщика** выберите в раскрывающемся списке **Microsoft**.
    
    > [!NOTE]
    > Так как вы используете Microsoft как поставщик услуг аудиоконференций и существует несколько номеров телефонов, можно использовать список **платный номер по умолчанию** для выбора звукового номера по умолчанию для пользователя.
  
5. Нажмите кнопку **Сохранить**.
    
### С помощью сценариев Windows PowerShell для нескольких пользователей

Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.
  
> [!NOTE]
> При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.
  
Один или несколько из представленных ниже сценариев можно сохранить как файл сценария PowerShell, а затем выполнить.
  
Сменить поставщика услуг на Майкрософт для небольшого количества пользователей позволяет сценарий [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
> **Пример 1.** Чтобы выполнить этот сценарий, сформируйте список пользователей, которых нужно обновить.
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **Пример 2.** Чтобы выполнить этот сценарий, сформируйте CSV-файл, содержащий адреса электронной почты (псевдонимы) всех пользователей, которых нужно обновить.
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### Применение сценария Windows PowerShell для большого количества пользователей

Чтобы сэкономить время или автоматизировать процесс, задать Майкрософт как поставщика аудиоконференций для небольшого количества пользователей можно с помощью следующего сценария PowerShell.
  
> [!NOTE]
> При смене поставщика на **Майкрософт** сведения об аудиоконференции (идентификатор конференции, платные и бесплатные телефонные номера) будут изменены. Сохраните эти данные перед сменой поставщика.
  
Один или несколько из представленных ниже сценариев можно сохранить как файл сценария PowerShell, а затем выполнить.
  
> **Пример 1.** В этом примере указанный сценарий позволяет сменить поставщика услуг аудиоконференций с Intercall (или другого поставщика) на **Майкрософт** для большого количества пользователей в вашей организации.
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **Сценарий выглядит следующим образом:**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

Дополнительные сведения об использовании Windows PowerShell см. в статье [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## Дополнительные сведения

- Для пользователя можно назначить только одного поставщика аудиоконференций.
    
- Сменить поставщика аудиоконференций можно в любой момент. Дополнительные сведения см. в статье [Назначение стороннего поставщика услуг аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- В организации разные пользователи могут использовать разных поставщиков аудиоконференций. Однако в этом случае настройка и управление усложняются.
    
## См. также:

[Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Отказ от ответственности относительно машинного перевода**. Данная статья была переведена с помощью компьютерной системы без участия человека. Microsoft предлагает эти машинные переводы, чтобы помочь пользователям, которые не знают английского языка, ознакомиться с материалами о продуктах, услугах и технологиях Microsoft. Поскольку статья была переведена с использованием машинного перевода, она может содержать лексические,синтаксические и грамматические ошибки. 
  


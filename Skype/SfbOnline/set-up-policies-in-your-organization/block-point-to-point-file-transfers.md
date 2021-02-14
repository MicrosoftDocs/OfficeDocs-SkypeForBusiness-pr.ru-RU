---
title: Блокировка передачи файлов точка-точка
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: В Skype для бизнеса Online вы можете управлять передачей файлов точка-точка (P2P) в рамках существующих параметров политики веб-услуг. Однако при этом для пользователей разрешается или блокируется передача файлов независимо от того, передаются ли они пользователям, которые находятся в той же организации или федератном пользователе из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам, вы предприняв действия ниже.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814638"
---
# <a name="block-point-to-point-file-transfers"></a>Блокировка передачи файлов точка-точка

В Skype для бизнеса Online вы можете управлять передачей файлов точка-точка (P2P) в рамках существующих параметров политики веб-услуг. Однако при этом для пользователей разрешается или блокируется передача файлов независимо от того, передаются ли они пользователям, которые находятся в той же организации или федератном пользователе из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам, вы предприняв действия ниже.
  
 Очень распространенный сценарий — разрешить внутренним пользователям использовать передачу файлов P2P, но заблокировать передачу файлов федератным партнерам. В этом сценарии вам потребуется сделать:
  
- Назначьте политику для conferencing с включенной передачей файлов P2P _(EnableP2PFileTransfer_ set to _True)_ пользователям в вашей организации.
    
- Создайте глобальный набор внешней политики связи пользователей, задав для блокировки передачи внешних P2P-файлов _(EnableP2PFileTransfer_ задайте для этого _false)_ и назначьте ее пользователю в вашей организации. 
    
Дополнительные информацию об этих параметрах можно [найти](https://technet.microsoft.com/library/mt228132.aspx)здесь.
  
Если федераированный пользователь за пределами вашей организации попытается отправить файл пользователю, к котором применена политика, он получит сообщение об ошибке с ошибкой **передачи.** Если пользователь попытается отправить файл, он получит сообщение об ошибке "Передача **файла отключена".**
  
Для этого пользователь должен использовать поддерживаемую версию приложения Skype для бизнеса версии 2016 "нажми и работай", которая ее поддерживает. Необходима следующая минимальная версия клиента Skype для бизнеса 2016 "нажми и работы":
  
|**Тип**|**Дата выпуска**|**Версия**|**Сборка**|
|:-----|:-----|:-----|:-----|
|First Release for Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Версия 1611 (сборка 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Версия 1611 (сборка 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Версия 1609 (сборка 7369.2118)  <br/> |
   
> [!CAUTION]
> Пользователи, которые используют более старые версии приложений Skype для бизнеса для Windows или клиентов Mac, по-прежнему смогут передавать файлы. 
  
## <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. Проверьте версию, введя _get-Host_ в **Windows PowerShell** окне.
        
    3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0. При появлении запроса перезагрузите компьютер.
        
    4. Вам также потребуется установить модуль Windows PowerShell для Teams, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online. 
    
    Если вам нужно узнать больше, см. подключение к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx)в одном окне Windows PowerShell окна.
    
- **Запуск сеанса Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:
    
        > [!NOTE]
        > Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.
        >
        > Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Если вам нужна дополнительные сведения о запуске Windows PowerShell, см. сведения о подключении к всем службам [Microsoft 365 или Office 365](https://technet.microsoft.com/library/dn568015.aspx) в одном окне Windows PowerShell или настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Отключение передач файлов P2P для организации

По умолчанию _enableP2PFileTransfer_ включена в глобальной политике организации. После создания пользователю была назначена политика _BposSAllModality._
  
Чтобы разрешить передачу P2P-файлов внутри организации, но заблокировать передачу внешних файлов в другую организацию, достаточно изменить ее на глобальном уровне. Для этого запустите 3
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Отключение передачи файлов P2P для пользователя

Вы можете применить эту политику к пользователю, создав новую политику и надав ее этому пользователю. Для этого запустите 3 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик для организации](set-up-conferencing-policies-for-your-organization.md)

  
 

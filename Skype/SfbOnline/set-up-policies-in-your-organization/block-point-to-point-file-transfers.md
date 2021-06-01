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
description: В Skype для бизнеса Online вы можете управлять передачей файлов "точка-точка" (P2P) в рамках существующих параметров политики веб-услуг. Однако это позволяет или блокирует передачу файлов для пользователей независимо от того, передают ли они файлы пользователю, который находится в той же организации, или федераированному пользователю из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам.
ms.openlocfilehash: e20cf0d5ff7a884e81fe2ee5de57ed026c53552e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240178"
---
# <a name="block-point-to-point-file-transfers"></a>Блокировка передачи файлов точка-точка

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

В Skype для бизнеса Online вы можете управлять передачей файлов "точка-точка" (P2P) в рамках существующих параметров политики веб-услуг. Однако это позволяет или блокирует передачу файлов для пользователей независимо от того, передают ли они файлы пользователю, который находится в той же организации, или федераированному пользователю из другой организации. Вы можете заблокировать передачу файлов P2P федера организации или партнерам.
  
 Очень распространенный сценарий — разрешить внутренним пользователям использовать передачу P2P-файлов, но заблокировать передачу файлов федератов. Для этого сценария вам потребуется сделать:
  
- Назначьте политику conferencing, включив передачу P2P-файлов _(EnableP2PFileTransfer_ для _true)_ для пользователей в организации.
    
- Создайте глобальный набор политики связи с внешними пользователями, чтобы заблокировать передачу внешних P2P-файлов _(EnableP2PFileTransfer_ с инициативой _False)_ и назначьте ее пользователю в вашей организации. 
    
Дополнительные информацию об этих параметрах можно [найти](/previous-versions//mt228132(v=technet.10))здесь.
  
Если федераированный пользователь за пределами организации попытается отправить файл пользователю, в котором была применена политика, он получит сообщение об ошибке Перенос **с ошибкой.** А если пользователь попытается отправить файл, он получит сообщение об ошибке Передачу **файла.**
  
Для этого пользователю необходимо использовать поддерживаемую версию приложения "нажми и работай" версии 2016 Skype для бизнеса, которое ее поддерживает. Требуется следующая минимальная версия Skype для бизнеса версии 2016 "нажми и работы":
  
|**Тип**|**Дата выпуска**|**Версия**|**Построить**|
|:-----|:-----|:-----|:-----|
|First Release for Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Версия 1611 (сборка 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Версия 1611 (сборка 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Версия 1609 (сборка 7369.2118)  <br/> |
   
> [!CAUTION]
> Пользователи, использующие более старые версии Skype для бизнеса Windows приложений или клиентов Mac, по-прежнему смогут передавать файлы. 
  
## <a name="start-windows-powershell"></a>Начните Windows PowerShell

> [!NOTE]
> Skype для бизнеса Online Connector в настоящее время является частью последней версии Teams PowerShell. Если вы используете последний общедоступный Teams PowerShell, вам не нужно устанавливать Skype для бизнеса Online Connector.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) в одном окне Windows PowerShell или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Отключение передач P2P-файлов для организации

По умолчанию _enableP2PFileTransfer_ включен в глобальной политике организации. При ее создания пользователям была назначена политика _BposSAllModality._
  
Чтобы разрешить передачу P2P внутри организации, но заблокировать передачу внешних файлов в другую организацию, достаточно изменить ее на глобальном уровне. Для этого запустите:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Отключение передачи P2P-файлов для пользователя

Вы можете применить эту политику к пользователю, создав новую политику и надав ее этому пользователю. Для этого запустите: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик conferencing в организации](set-up-conferencing-policies-for-your-organization.md)

  

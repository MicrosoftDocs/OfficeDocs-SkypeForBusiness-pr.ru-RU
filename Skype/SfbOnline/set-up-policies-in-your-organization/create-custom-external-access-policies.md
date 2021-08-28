---
title: Создание настраиваемых политик внешнего доступа
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype для бизнеса В Интернете можно создавать дополнительные политики внешнего доступа. В отличие от политик клиента или conferencing, где можно использовать несколько комбинаций, существует три предопределенной политики внешнего доступа, которые могут охватывать большинство сценариев.
ms.openlocfilehash: d0ecf5051de17f923983e16f35eb22b66c41571e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619275"
---
# <a name="create-custom-external-access-policies"></a>Создание настраиваемых политик внешнего доступа

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype для бизнеса В Интернете можно создавать дополнительные политики внешнего доступа. В отличие от политик клиента или conferencing, где можно использовать несколько комбинаций, существует три предопределенной политики внешнего доступа, которые могут охватывать большинство сценариев. Это:
  
- Нет федераций и Skype доступа для потребителей (_Tag:NoFederationAndpIC_ )
    
- Только федераированный доступ (_Tag:FederationOnly_ )
    
- Federated and Consumer Access _(FederationAndPICDefault_)
    
Настраиваемые внешние политики позволяют создавать дополнительные политики, которые не охватывают параметры выше. После создания политики вам потребуется настроить все необходимые параметры, и вы не сможете изменить их позже. Создание новых настраиваемых политик позволяет управлять такими функциями, как доступ Skype или политика для отключения общедоступных облачных аудио- и видеофайлов , которые не были заранее озвучиты. Настраиваемые политики внешнего доступа имеют тот же синтаксис, что и политики клиентского, мобильного доступа иконок. Дополнительные информацию об этих параметрах можно [найти](/previous-versions//mt228132(v=technet.10))здесь.
  
Для этого пользователю необходимо использовать поддерживаемую версию версии 2016 Skype для бизнеса "нажми и работай". Требуется следующая минимальная версия клиента Skype для бизнеса версии 2016 "нажми и работы":
  
|**Тип**|**Дата выпуска**|**Версия**|**Построить**|
|:-----|:-----|:-----|:-----|
|First Release for Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Версия 1611 (сборка 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Версия 1611 (сборка 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Версия 1609 (сборка 7369.2118)  <br/> |
   
> [!CAUTION]
> Пользователи, использующие более старые версии Skype для бизнеса Windows приложений или клиентов Mac, по-прежнему смогут передавать файлы. 
  
## <a name="start-windows-powershell"></a>Начать Windows PowerShell

> [!NOTE]
> Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online.
1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Дополнительные сведения о запуске Windows PowerShell см. в Подключение всех службах Microsoft 365 или Office 365 в одном окне [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) или Настройка компьютера [для](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell.
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Создание настраиваемой политики внешнего доступа для пользователя

Для этого выполните команду:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме
[Блокировка передачи файлов по точкам](block-point-to-point-file-transfers.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик conferencing в организации](set-up-conferencing-policies-for-your-organization.md)

  

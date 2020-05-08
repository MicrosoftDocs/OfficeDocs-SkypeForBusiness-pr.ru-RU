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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа. В отличие от политик клиентов и конференций, где вы можете использовать несколько сочетаний, есть три стандартные политики внешнего доступа, которые могут охватывать большинство сценариев.
ms.openlocfilehash: 02fba48a6b8acf2a2b66078624ab36eb7453df0c
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164648"
---
# <a name="create-custom-external-access-policies"></a>Создание настраиваемых политик внешнего доступа

Skype для бизнеса Online позволяет создавать дополнительные политики внешнего доступа. В отличие от политик клиентов и конференций, где вы можете использовать несколько сочетаний, есть три стандартные политики внешнего доступа, которые могут охватывать большинство сценариев. Ниже указаны указанные ниже.
  
- Нет доступа к Федеративной или Skype для потребителей (_тег: NoFederationAndPIC_ )
    
- Только для федеративного доступа (_Tag: FederationOnly_ )
    
- Федеративные и доступ к потребителям (_FederationAndPICDefault_)
    
Пользовательские внешние политики позволяют создавать дополнительные политики, не охваченные приведенными выше параметрами. После создания политики вам потребуется настроить все необходимые параметры, и вы не сможете изменить их позже. Создание настраиваемых политик позволяет управлять такими функциями, как доступ к потребителю Skype или политика для отключения общедоступного облака аудио-и видеофайлов, что не было охвачено предопределенными параметрами. Пользовательские политики внешнего доступа следуют тем же синтаксису, что и политики клиента, мобильных устройств и конференц-связи. Дополнительные сведения об этих параметрах можно найти [здесь](https://technet.microsoft.com/library/mt228132.aspx).
  
Для выполнения этой задачи пользователю необходима поддерживаемая версия 2016 "нажми и работай" приложения Skype для бизнеса, поддерживающего это приложение. Требуется следующая минимальная версия клиента "нажми и работай" Skype для бизнеса 2016:
  
|**Тип**|**Дата выпуска**|**Версия**|**Разработки**|
|:-----|:-----|:-----|:-----|
|Первый выпуск для текущего канала  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Версия 1611 (сборка 7571,2006)  <br/> |
|Текущий канал  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Версия 1611 (сборка 7571,2072)  <br/> |
|Отложенный канал  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Версия 1609 (сборка 7369,2118)  <br/> |
   
> [!CAUTION]
> Пользователи, использующие более ранние версии приложений Skype для бизнеса для Windows или Mac, по-прежнему смогут передавать файлы. 
  
## <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://www.microsoft.com/download/details.aspx?id=40855) . При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Создание настраиваемой политики внешнего доступа для пользователя

Для этого выполните команду:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Зачем использовать Microsoft 365 или Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>См. также
[Блокировка передачи файлов между точками](block-point-to-point-file-transfers.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик конференц-связи в Организации](set-up-conferencing-policies-for-your-organization.md)

  
 

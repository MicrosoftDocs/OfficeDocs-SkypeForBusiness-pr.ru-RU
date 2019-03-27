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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: В Скайп для бизнеса в Интернет у вас есть возможность управления передачу файлов между узлами (P2P) как часть существующие параметры политики конференц-связи. Тем не менее это позволяет или передача для пользователей, ли они передачу файлов, пользователь, который находится в пределах той же организации или федеративного пользователя из другой организации файлов блоки. Следующие шаги можно заблокировать P2P передачи файлов с федеративными организациями или партнеров.
ms.openlocfilehash: 9b7d229c7f0ea0565dc3174286b4117984a2b606
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883246"
---
# <a name="block-point-to-point-file-transfers"></a>Блокировка передачи файлов точка-точка

В Скайп для бизнеса в Интернет у вас есть возможность управления передачу файлов между узлами (P2P) как часть существующие параметры политики конференц-связи. Тем не менее это позволяет или передача для пользователей, ли они передачу файлов, пользователь, который находится в пределах той же организации или федеративного пользователя из другой организации файлов блоки. Следующие шаги можно заблокировать P2P передачи файлов с федеративными организациями или партнеров.
  
 Весьма распространенного сценария — Если вы хотите разрешить внутренние пользователи могли использовать P2P передачи файлов, но блока передачи файлов с помощью федеративных партнеров. Для этого сценария необходимо выполнить:
  
- Назначение политики конференц-связи с поддержкой передачи файлов P2P (_EnableP2PFileTransfer_ присвоено _значение True_) для пользователей в вашей организации.
    
- Создайте политики связи глобальной внешних пользователей, задайте для блокировки передачи файлов внешних P2P (_EnableP2PFileTransfer_ значение _False_) и назначить пользователю в вашей организации. 
    
Дополнительную информацию по эти параметры можно найти [здесь](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Если федеративных пользователей за пределами организации пытается отправить файл пользователю, где была ли применена политика, они получат ошибка **Передачи произошел сбой** . И при попытке отправить файл появляется ошибка **передачи файлов отключена** .
  
Чтобы выполнить эту операцию, пользователя необходимо включить поддерживаемая версия Скайп Click-to-Run 2016 для бизнес-приложение, которое поддерживает его. Следующие Минимальная версия Скайп для клиента Business 2016 Click-to-Run является обязательным:
  
|**Тип**|**Дата выпуска**|**Версия**|**Построение**|
|:-----|:-----|:-----|:-----|
|Первый выпуск для текущего канала  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Версия 1611 (сборка 7571.2006)  <br/> |
|Текущая платформа канала  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Версия 1611 (сборка 7571.2072)  <br/> |
|Отложенная канала  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Версия 1609 (сборка 7369.2118)  <br/> |
   
> [!CAUTION]
> Пользователи, работающие с более ранними версиями Скайп для приложения для бизнеса Windows или Mac клиентов по-прежнему будут иметь возможность передавать файлы. 
  
## <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Проверка версии с помощью следующей команды _Get-узел_ в окне **Windows PowerShell** .
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [настроить компьютер для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Отключение P2P передачу файлов для вашей организации

По умолчанию _EnableP2PFileTransfer_ включена на глобальную политику в организации. При его создании, пользователи были назначена политика _BposSAllModality_ .
  
Только что, чтобы разрешить передачу P2P для внутри вашей организации, но блока передачи внешнего файла на другой организации, необходимо изменить на глобальном уровне. Для этого выполните следующую команду:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Отключение P2P передачи файлов для пользователя

Можно применить это пользователь, создав новую политику и предоставление данному пользователю. Для этого выполните следующую команду: 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Связанные разделы
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик конференц-связи в вашей организации](set-up-conferencing-policies-for-your-organization.md)

  
 

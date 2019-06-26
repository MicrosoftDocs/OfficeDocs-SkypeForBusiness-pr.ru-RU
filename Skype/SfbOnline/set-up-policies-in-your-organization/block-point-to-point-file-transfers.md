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
f1keywords: None
ms.custom:
- Setup
description: В Skype для бизнеса Online вы можете управлять передачей файлов с точки зрения (P2P) в составе существующих параметров политики конференц-связи. Тем не менее, это позволяет или блокирует передачу файлов для пользователей вне зависимости от того, передается ли они пользователям, которые находятся в той же организации или на федеративных пользователей из другой организации. Следуя приведенным ниже инструкциям, вы можете заблокировать передачу файлов P2P с федеративными организациями или партнерами.
ms.openlocfilehash: 248b541a4d57c3b51a48694d3194432cc207db06
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221192"
---
# <a name="block-point-to-point-file-transfers"></a>Блокировка передачи файлов точка-точка

В Skype для бизнеса Online вы можете управлять передачей файлов с точки зрения (P2P) в составе существующих параметров политики конференц-связи. Тем не менее, это позволяет или блокирует передачу файлов для пользователей вне зависимости от того, передается ли они пользователям, которые находятся в той же организации или на федеративных пользователей из другой организации. Следуя приведенным ниже инструкциям, вы можете заблокировать передачу файлов P2P с федеративными организациями или партнерами.
  
 Очень распространенный сценарий, который позволяет внутренним пользователям использовать передачу файлов P2P, но блокировать передачу файлов с помощью федеративных партнеров. Для этого сценария необходимо выполнить указанные ниже действия.
  
- Назначьте политику конференций с включенной поддержкой передачи файлов P2P (для_EnableP2PFileTransfer_ установлено значение _true_) для пользователей в вашей организации.
    
- Создайте глобальную политику связи внешних пользователей, которая блокирует передачу внешних файлов P2P (для_EnableP2PFileTransfer_ установлено значение _false_), и назначьте ее пользователю в вашей организации. 
    
Дополнительные сведения об этих параметрах можно найти [здесь](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Если федеративный пользователь за пределами вашей организации пытается отправить файл пользователю, на котором она была применена, она получит сообщение об ошибке " **не удалось передать** ". Если пользователь попытается отправить файл, он получит сообщение об ошибке " **Передача файлов** отключена".
  
Для выполнения этой задачи пользователь должен использовать поддерживаемую версию 2016 "нажми и работай" приложения Skype для бизнеса, поддерживающего это приложение. Требуется следующая минимальная версия клиента "нажми и работай" Skype для бизнеса 2016:
  
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
    
2. Проверьте версию, введя _Get-Host_ в окне **Windows PowerShell** .
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . При появлении запроса перезагрузите компьютер.
    
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

   Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Отключение передачи файлов P2P для Организации

По умолчанию _EnableP2PFileTransfer_ включена в глобальной политике Организации. После создания пользователи назначили политику _бпоссаллмодалити_ .
  
Чтобы разрешить передачу P2P в рамках вашей организации, но заблокировать передачу внешних файлов в другую организацию, вам нужно просто изменить ее на глобальном уровне. Для этого выполните указанные ниже действия.
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Отключение передачи файлов P2P для пользователя

Вы можете применить это к пользователю, создав новую политику и предоставив ее для этого пользователя. Для этого выполните указанные ниже действия. 
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
    
## <a name="related-topics"></a>Статьи по теме
[Создание настраиваемых политик внешнего доступа](create-custom-external-access-policies.md)

[Настройка политик клиента в организации](set-up-client-policies-for-your-organization.md)

[Настройка политик конференц-связи в Организации](set-up-conferencing-policies-for-your-organization.md)

  
 

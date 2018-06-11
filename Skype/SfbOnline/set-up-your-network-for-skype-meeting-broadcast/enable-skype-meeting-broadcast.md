---
title: Включение трансляции собраний Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Чтобы обеспечить доступ пользователей к Широковещательный показ собраний в Skype, ее необходимо включить. Для этого требуются навыки работы с Windows PowerShell. Если вы не имеете опыта работы с Windows PowerShell, мы рекомендуем обратиться для выполнения этих действий к партнеру Майкрософт.
ms.openlocfilehash: 2564cf8acc809cb3b3973519bfea3518c851eb34
ms.sourcegitcommit: 0fa147c33b1d7b5790af8d93339700ab62939430
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "19744264"
---
# <a name="enable-skype-meeting-broadcast"></a>Включение трансляции собраний Skype

[] Чтобы обеспечить доступ пользователей к Широковещательный показ собраний в Skype, ее необходимо включить. Для этого требуются навыки работы с Windows PowerShell. Если вы не имеете опыта работы с Windows PowerShell, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Включение Трансляции собраний Skype с помощью центра администрирования Skype для бизнеса

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**

1. Вход с помощью учетной записи глобального администратора Office 365 в [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. В центре администрирования Office 365 перейдите в раздел **Центры администрирования** > **Skype для бизнеса**.
    
3. В **Скайп по центру администрирования бизнеса**, перейдите на **собрания по сети** > **распространения собраний**и выберите команду **Включить Скайп вещания собрания**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Включение трансляции собраний Skype с помощью PowerShell

1. Проверьте, что у вас установлен Windows PowerShell 3.0 или более поздней версии.
    
1. Чтобы узнать, какая у вас версия, перейдите в меню **Пуск** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
2. Из меню **Пуск** перейдите к **Windows PowerShell**.
    
3. В окне **Windows PowerShell** подключитесь к своей организации Office 365, введя следующее:
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Подтвердите текущую конфигурацию Широковещательный показ собраний в Skype, выполнив следующее:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Убедитесь, что для параметра  _EnableBroadcastMeeting_ указано значение `False`.
    
     ![Командлет для включения трансляции собраний Skype в организации.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Подключите функцию Широковещательный показ собраний в Skype, выполнив следующую команду:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Для подтверждения того, что настройка включена, повторно выполните команду  `Get-CsBroadcastMeetingConfiguration`.
    
     ![Командлет для включения трансляции собраний Skype в организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Чтобы внесенные изменения вступили в силу на портале Широковещательный показ собраний в Skype, может потребоваться до часа. 
  
6. Теперь пользователи могут транслировать собрания для других пользователей вашей организации. Полезные сведения о начале работы пользователи могут найти в разделе [Что такое трансляция собрания Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Настройка сети для трансляции собраний с внешними участниками

Если в вашей среде применяется брандмауэр, для проведения трансляций с участниками, не работающими в вашей организации (не являющимися членами федерации), вам необходимо настроить сеть, следуя приведенным ниже инструкциям: [Настройка сети для трансляции собрания Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Если у вас нет опыта в настройке брандмауэра, мы рекомендуем обратиться для выполнения этих действий к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089).
  
Чтобы пропустить этот шаг и добавить другую организацию в вашу федерацию, выполните инструкции в разделе [Разрешите пользователям связываться с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>See also

[Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
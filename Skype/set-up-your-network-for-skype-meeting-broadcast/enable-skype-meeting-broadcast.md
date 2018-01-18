---
title: "Включение Скайп собрания вещания"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Перед людей в организации можно использовать Скайп вещания собрания, необходимо включить его. Для этого необходимо знать, как с помощью Windows PowerShell. Если вы не знаете Windows PowerShell, рассмотрите возможность найма партнера корпорации Майкрософт, чтобы выполнить это действие для вас."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a>Включение Скайп собрания вещания

Перед людей в организации можно использовать Скайп вещания собрания, необходимо включить его. Для этого необходимо знать, как с помощью Windows PowerShell. Если вы не знаете Windows PowerShell, рассмотрите возможность найма [партнера корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) для выполнения этого шага для вас.
  
> [!CAUTION]
> Скайп собрания вещания отключена по умолчанию из-за распределения контента мультимедиа вещания собрания использует Microsoft Azure сети доставки содержимого (CDN) для достижения очень высокий масштаба для поддержки тысячи людей, просмотра вещания. Частям мультимедийного содержимого, проходящих через CDN шифруются и кэш CDN имеет ограничения времени жизни. Кроме того компонент Azure CDN, могут не еще не отвечать все элементы типовыми статьями ЕС, возникающих из-за директивы защиты данных ЕС. Эта функция включена, подтвердить это Примечание. 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Включение Скайп собрания вещания с помощью Скайп по центру администрирования бизнеса

1. Войдите с использованием учетной записи глобального администратора Office 365 по адресу [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. В центре администрирования Office 365 перейдите на **центры администрирования** > **Скайп для бизнеса**.
    
3. В **Скайп по центру администрирования бизнеса**, перейдите на **собрания по сети** > **распространения собраний**и выберите команду **Включить Скайп вещания собрания**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Включение Скайп собрания вещания с помощью PowerShell

1. Убедитесь, что запущена версия 3.0 или более поздней версии для Windows PowerShell.
    
1. Чтобы убедиться, что выполняется версия 3.0 или более поздней версии: **Меню "Пуск"** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне **Windows PowerShell** команду _Get-Host_.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
2. В **Меню "Пуск"**выберите команду **Windows PowerShell**.
    
3. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Подтверждение текущей конфигурации Скайп собрания вещания с помощью:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Убедитесь, что параметр _EnableBroadcastMeeting_ `False`.
    
     ![Командлет Скайп вещания Включение организации собраний.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Включение Скайп собрания вещания для вашей организации, выполнив:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Убедитесь, что этот параметр включен, выполнив `Get-CsBroadcastMeetingConfiguration` еще раз.
    
     ![Скайп собрания вещания включите командлет организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > После внесения изменений, он может занять час вступили в силу на портале Скайп собрания вещания. 
  
6. Пользователи теперь могут содержать вещания встречи с другими пользователями в бизнесе. По началу работы, укажите их [возможности собраний Скайп, вещание?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Настройка сети для вещания собрания с внешних пользователей

Брандмауэр, и требуется для хранения вещании с людьми за ее пределами бизнеса (пользователей, которые не являются федеративными бизнеса), требуется ли настройка сети с использованием эти инструкции: [Настройка сети для Скайп собрания вещания](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Если вы опытный с Настройка брандмауэра, рассмотрите возможность найма [партнера корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) для выполнения этого шага для вас.
  
Пропустите этот шаг и вместо этого добавьте другой компании вашей федерации см [Разрешить пользователям включать поддержку для связи внешних Скайп для коммерческих пользователей](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>См. также:

[Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


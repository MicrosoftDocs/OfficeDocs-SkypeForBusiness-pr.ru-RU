---
title: Включение трансляции собрания Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
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
- SMB
description: Прежде чем сотрудники вашей организации смогут использовать трансляцию собраний Skype, необходимо включить ее. Для этого вам нужно знать, как использовать Windows PowerShell. Если вы не знаете Windows PowerShell, вы можете сделать это с помощью партнера Майкрософт.
ms.openlocfilehash: f1a672bc8d3b0ce957a32691270293551e1a1409
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494038"
---
# <a name="enable-skype-meeting-broadcast"></a>Включение трансляции собрания Skype

Прежде чем сотрудники вашей организации смогут использовать трансляцию собраний Skype, необходимо включить ее. Для этого вам нужно знать, как использовать Windows PowerShell. Если вы не знаете Windows PowerShell, вы можете сделать это с помощью [партнера Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) .

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Включение трансляции собраний Skype с помощью центра администрирования Skype для бизнеса

![Значок, показывающий логотип](../images/sfb-logo-30x30.png) Skype для бизнеса **, с помощью центра администрирования Skype для бизнеса**

1. Войдите в систему с помощью учетной записи глобального администратора [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)Office 365 по адресу.
    
2. В центре администрирования Office 365 перейдите в раздел **"центры** > администрирования**Skype для бизнеса**".
    
3. В **центре администрирования Skype для бизнеса**перейдите в раздел **собрания** > по сети, чтобы**транслировать**собрания, а затем выберите **Включить трансляцию собраний Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Включение трансляции собраний Skype с помощью PowerShell

1. Убедитесь в том, что вы используете версию 3,0 или более позднюю версию Windows PowerShell.
    
2. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
3. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
4. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
5. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
6. В **меню Пуск**выберите пункт **Windows PowerShell**.
    
7. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Подтвердите текущую конфигурацию трансляции собраний Skype, выполнив следующие действия:
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    Убедитесь, что для __ `False`параметра енаблеброадкастмитинг задано значение.
    
     ![Трансляция собраний Skype с помощью командлета Organization.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Включите трансляцию собраний Skype для своей организации, выполнив следующие действия:
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Вы можете подтвердить, что параметр включен, запустив `Get-CsBroadcastMeetingConfiguration` его еще раз.
    
     ![Трансляция собраний Skype с помощью командлета Organization.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > После внесения изменений может вступить в силу на портале трансляции собраний Skype в течение часа. 
  
10. Теперь ваши пользователи могут проводить широковещательные собрания с другими пользователями вашего бизнеса. Чтобы начать работу, наведите их на то, [что такое трансляция собрания Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Настройка сети для трансляции собраний с внешними участниками

Если у вас есть брандмауэр и вы хотите хранить широковещательные показы с людьми за пределами вашей организации (которые не являются федеративными организациями), вам нужно настроить сеть, выполнив следующие инструкции: [Настройка сети для трансляции собраний Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Если вы не сталкивались с настройкой межсетевого экрана, рассматривайте для этого действия [партнера Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) .
  
Чтобы пропустить этот шаг и добавить еще один бизнес в Федерацию, ознакомьтесь с разделом [Разрешить пользователям связываться с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Статьи по теме

[Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
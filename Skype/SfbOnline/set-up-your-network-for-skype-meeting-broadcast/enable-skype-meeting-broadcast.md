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
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее. Для этого нужно уметь пользоваться Windows PowerShell. Если вы не знаете, Windows PowerShell можете нанять партнера Майкрософт, чтобы сделать это за вас.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865143"
---
# <a name="enable-skype-meeting-broadcast"></a>Включение трансляции собрания Skype

> [!IMPORTANT]
> Skype для бизнеса Online больше не будет работать 31 июля 2021 г., после чего доступ к службе закончится. Мы рекомендуем клиентам начать обновление до Microsoft Teams, основного клиента для связи и командной работы в Microsoft 365.

Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее. Для этого необходимо знать, как использовать Windows PowerShell. Если вы не знаете, Windows PowerShell можете нанять партнера [Майкрософт,](https://go.microsoft.com/fwlink/?linkid=391089) чтобы сделать это за вас.



> [!NOTE]
> Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал). Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams. Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса. Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Включить трансляцию собраний Skype с помощью Центра администрирования Skype для бизнеса

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

1. Во sign in with your global admin account or Skype for Business admin account [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) at.
    
2. В Центре администрирования перейдите в **Центры администрирования**  >  **Teams.**
    
3. В Центре **администрирования Teams перейдите** на устаревший **портал** портала Online, на который транслируются собрания, а затем выберите "Включить  >    >   **трансляцию собраний Skype".**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Включить трансляцию собраний Skype с помощью PowerShell

1. Убедитесь, что у вас версия 3.0 или более Windows PowerShell.
    
2. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
3. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
4. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0. При появлении запроса перезагрузите компьютер.
    
5. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
6. В меню **"Пуск"** выберите пункт **Windows PowerShell.**
    
7. В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работающим с помощью:
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Подтвердите текущую конфигурацию трансляции собраний Skype, выверив данная программа:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Убедитесь, что для _параметра EnableBroadcastMeeting_ задано такое же. `False`
    
     ![Cmdlet Enable Organization (Включить трансляцию собраний Skype для организации).](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Чтобы включить трансляцию собраний Skype для вашей организации, с помощью:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Чтобы подтвердить, что параметр включен, повторно за  `Get-CsBroadcastMeetingConfiguration` работы.
    
     ![Cmdlet Enable Organization (Включить трансляцию собраний Skype для организации).](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > После внести изменения на портал трансляции собраний Skype может потребоваться до часа. 
  
10. Теперь пользователи могут проводить широковещательные собрания с другими пользователями в вашей компании. Чтобы начать, указать им на что [ведется трансляция собраний Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Настройка сети для трансляции собраний с внешними участниками

Если у вас есть брандмауэр и вы хотите проводить трансляции с людьми за пределами вашей компании (которые не являются федератными), необходимо настроить сеть с помощью указанных здесь инструкций: настройка сети для трансляции собраний [Skype.](set-up-your-network-for-skype-meeting-broadcast.md) 
  
Если у вас нет опыта в настройке брандмауэра, вы можете нанять партнера Майкрософт, который сделает это за вас. [](https://go.microsoft.com/fwlink/?linkid=391089)
  
Если вы пропустили этот шаг и вместо этого добавили в вашу федерацию еще одну бизнес-часть, см. вопрос "Разрешить пользователям связываться с внешними пользователями [Skype для бизнеса".](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>Статьи по теме

[Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 

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
description: Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее. Для этого необходимо знать, как использовать Windows PowerShell. Если вы не знаете, Windows PowerShell можете нанять партнера Майкрософт, чтобы сделать это за вас.
ms.openlocfilehash: ab59348d32ef130df6b0de6e1eb65c92d0222e04
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097115"
---
# <a name="enable-skype-meeting-broadcast"></a>Включение трансляции собрания Skype

> [!IMPORTANT]
> Skype для бизнеса Online больше не будет работать 31 июля 2021 г., после чего доступ к службе закончится. Мы рекомендуем клиентам начать обновление до Microsoft Teams, основного клиента для связи и командной работы в Microsoft 365.

Чтобы пользователи в вашей организации могли использовать трансляцию собраний Skype, необходимо включить ее. Для этого нужно уметь пользоваться Windows PowerShell. Если вы не знаете, Windows PowerShell можете нанять партнера [Майкрософт,](https://go.microsoft.com/fwlink/?linkid=391089) чтобы сделать это за вас.



> [!NOTE]
> Центр администрирования Microsoft Teams заменил Центр администрирования Skype для бизнеса (устаревший портал). Все параметры управления Skype для бизнеса теперь находятся в Центре администрирования Teams. Чтобы управлять функциями Skype для бизнеса в Центре администрирования Teams, вам должна быть назначена роль администратора [Azure AD](/azure/active-directory/roles/permissions-reference) глобального администратора или администратор Skype для бизнеса. Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Включить трансляцию собраний Skype с помощью Центра администрирования Skype для бизнеса

![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

1. Во sign in with your global admin account or Skype for Business admin account [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) at.
    
2. В Центре администрирования перейдите в **Центры администрирования**  >  **Teams.**
    
3. В Центре **администрирования Teams перейдите** на устаревший **портал** портала Online, на который можно транслировать собрания, а затем выберите "Включить  >    >   **трансляцию собраний Skype".**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Включить трансляцию собраний Skype с помощью PowerShell

1. Установите модуль [Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Откройте Windows PowerShell и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Подтвердите текущую конфигурацию трансляции собраний Skype, выверив:
    
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
  
10. Теперь пользователи могут проводить широковещательные собрания с другими пользователями в вашей компании. Чтобы начать, на можете указать им, что [такое трансляция собрания Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Настройка сети для трансляции собраний с внешними участниками

Если у вас есть брандмауэр и вы хотите проводить трансляции с людьми за пределами вашей компании (которые не являются федератными), необходимо настроить сеть с помощью указанных здесь инструкций: настройка сети для трансляции собраний [Skype.](set-up-your-network-for-skype-meeting-broadcast.md) 
  
Если у вас нет опыта в настройке брандмауэра, вы можете нанять партнера Майкрософт, который сделает это за вас. [](https://go.microsoft.com/fwlink/?linkid=391089)
  
Чтобы пропустить этот шаг и добавить в вашу федерацию еще один бизнес, см. вопрос "Разрешить пользователям связываться с внешними пользователями [Skype для бизнеса".](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>Статьи по теме

[Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  

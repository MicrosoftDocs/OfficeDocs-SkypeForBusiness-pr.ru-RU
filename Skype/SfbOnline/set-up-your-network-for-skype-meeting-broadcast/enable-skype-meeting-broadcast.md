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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Чтобы люди в вашей организации могли Skype трансляцию собраний, необходимо включить ее. Для этого необходимо знать, как использовать Windows PowerShell. Если вы не знаете, Windows PowerShell, вы можете нанять партнера Майкрософт, который сделает это за вас.
ms.openlocfilehash: ec42de04b139537f05cadabbdffb84f645edcf2a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731268"
---
# <a name="enable-skype-meeting-broadcast"></a>Включение трансляции собрания Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype для бизнеса 31 июля 2021 г. заканчивается доступ к службе Online. Мы рекомендуем клиентам начать обновление до Microsoft Teams , основного клиента для связи и командной работы в Microsoft 365.

Чтобы люди в вашей организации могли Skype трансляцию собраний, необходимо включить ее. Для этого необходимо знать, как использовать Windows PowerShell. Если вы не знаете, как Windows PowerShell, вы можете нанять партнера [Майкрософт,](https://go.microsoft.com/fwlink/?linkid=391089) который сделает это за вас.



> [!NOTE]
> Центр Microsoft Teams администрирования заменил центр администрирования Skype для бизнеса (устаревший портал). Все параметры управления Skype для бизнеса теперь находятся в Teams администрирования. Для управления функциями Skype для бизнеса Teams в Центре администрирования azure [AD](/azure/active-directory/roles/permissions-reference) вам должна быть назначена роль глобального администратора или администратора Skype для бизнеса администратора. Дополнительные сведения см. в статье [Управление параметрами Skype для бизнеса в Центре администрирования Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Включить Skype собрания с помощью Skype для бизнеса администрирования

![Значок с логотипом Skype для бизнеса логотипом.](../images/sfb-logo-30x30.png) **Использование центра Skype для бизнеса администрирования**

1. Во sign in with your global admin account or Skype для бизнеса admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. В Центре администрирования перейдите **в** центр администрирования Teams  >  .
    
3. В Центре **Teams администрирования** перейдите на устаревший портал Онлайн-собрания Трансляция собраний , а затем выберите Включить Skype  >    >   **трансляцию собраний**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Включить Skype собрания с помощью PowerShell

1. Установите модуль [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Откройте Windows PowerShell командную команду и запустите следующие команды: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Подтвердите текущую конфигурацию Skype трансляции собрания с помощью:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Убедитесь, что для  _параметра EnableBroadcastMeeting_ задан параметр `False` .
    
     ![Skype "Включить трансляцию собраний для организации".](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. В Skype трансляцию собраний для организации можно включить:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Вы можете подтвердить, что этот параметр включен, повторно  `Get-CsBroadcastMeetingConfiguration` заверив его.
    
     ![Skype "Включить трансляцию собраний" для организации.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > После внести изменения на портале широковещательного Skype может потребоваться до часа. 
  
10. Теперь ваши пользователи могут проводить широковещательные собрания с другими пользователями в вашей компании. Чтобы начать, наведя на них указатель на пункт Что такое [Skype трансляции собрания?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Настройка сети для трансляции собраний с внешними участниками

Если у вас есть брандмауэр и вы хотите проводить трансляции с людьми за пределами вашей компании (которые не являются федератными), необходимо настроить сеть с помощью указанных здесь инструкций: Настройка сети для [Skype](set-up-your-network-for-skype-meeting-broadcast.md)трансляции собраний . 
  
Если у вас нет опыта настройки брандмауэра, [](https://go.microsoft.com/fwlink/?linkid=391089) вы можете нанять партнера Майкрософт, который сделает это за вас.
  
Чтобы пропустить этот шаг и вместо этого добавить в вашу федерацию другую бизнес-федерацию, см. разрешение пользователям связываться с внешними Skype для бизнеса [пользователями.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>Статьи по теме

[Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  

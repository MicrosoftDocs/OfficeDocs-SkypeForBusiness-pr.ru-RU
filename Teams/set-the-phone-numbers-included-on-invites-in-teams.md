---
title: Настройка телефонных номеров, включаемых в приглашения в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Описание шагов по созданию телефонного номера по умолчанию для вызывающих абонентов на присоединение к собранию Microsoft Teams. '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882962"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Настройка телефонных номеров, включаемых в приглашения в Microsoft Teams

Функция аудиоконференций в Office 365 позволяет пользователям вашей организации создавать собрания Microsoft Teams для подключения к ним пользователей по телефону. В Office 365 есть возможность использования моста аудиоконференций Майкрософт или моста аудиоконференций сторонних разработчиков, размещенного у утвержденного поставщика услуг аудиоконференций.
  
Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.
  
> [!NOTE]
> Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Задание или изменение телефонного номера аудиоконференций по умолчанию для организатора собрания или пользователя

1. В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.

    ![Показан выбор пользователей в Microsoft Teams и Центре администрирования Skype для бизнеса](media/teamsselectusers.png)

2. В верхней части страницы щелкните на элементе **Изменить**.

    ![Щелчок на элементе «Изменить» в Microsoft Teams и Центре администрирования Skype для бизнеса](media/teamsedituser.png)

3. Щелкните **Изменить** рядом с элементом **Аудиоконференции**. 
    
    ![Щелчок на элементе «Изменить» рядом с элементом «Аудиоконференции»](media/teamseditaudioconf.png)

4. Используйте поля **Платный номер** и **Бесплатный номер** для ввода номеров для этого пользователя.


> [!IMPORTANT]
> При изменении настроек аудиоконференции нужно обновить и отправить участникам повторяющиеся и будущие собрания Microsoft Teams. 

## <a name="want-to-use-windows-powershell"></a>Хотите использовать Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Связанные разделы

[Оцените или приобретите аудиоконференции в Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

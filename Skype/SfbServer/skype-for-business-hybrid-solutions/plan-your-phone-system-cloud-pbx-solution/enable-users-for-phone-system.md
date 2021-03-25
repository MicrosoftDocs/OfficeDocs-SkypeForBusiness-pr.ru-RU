---
title: Активация пользователей телефонной системы с соединением по локальной ТСОП в Skype для бизнеса Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'В этом разделе описывается, как включить пользователей для телефонной системы с локальной подключением PSTN. Прежде чем следовать шагам в этом разделе, необходимо прочитать следующее: .'
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120871"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Активация пользователей телефонной системы с соединением по локальной ТСОП в Skype для бизнеса Server

В этом разделе описывается, как включить пользователей для телефонной системы с локальной подключением PSTN. Прежде чем следовать шагам в этом разделе, необходимо прочитать следующее: .
  
- Чтобы узнать, как настроить гибридное подключение, см. в сайте Plan hybrid [connectivity between Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) и Skype for Business Online и Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online.](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
    
- Подробнее о планировании развертывания см. в сайте Plan Phone System с локальной связью [PSTN](plan-phone-system-with-on-premises-pstn-connectivity.md)в Skype для бизнеса Server.
    
- Дополнительные информацию о телефонной системе, включая лицензирование и планы, см. в приложениях [PSTN Calling plans for Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба будет больше недоступна.  Кроме того, подключение PSTN между локальной средой, будь то Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online, больше не будет поддерживаться.  Узнайте, как подключить сеть локальной телефонии к Teams с помощью [прямого маршрутного маршрутинга.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Перемещение пользователей в телефонную систему с локальной подключением PSTN

Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить пользователей на локальной основе в Skype для бизнеса Server или Lync Server 2013, а затем переместить их в Интернете. Дополнительные сведения см. в разделе Планирование гибридного подключения [между Skype для](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) бизнеса Server и Skype для бизнеса Online и раздел специальных соображений Включить пользователей для Корпоративная голосовая связь на месте (выполняется, пока пользователи находятся в локальном помещении). [](enable-the-users-for-enterprise-voice-on-premises.md) 
  
Все пользователи должны создаваться в Active Directory на локальной основе и синхронизироваться с Microsoft 365 или Office 365 с помощью поддерживаемой версии разъема Azure AD. Нельзя включить пользователей для телефонной системы в Office 365, созданных непосредственно в Azure AD. Если вы хотите включить телефонную систему с локальной подключением PSTN для пользователя, созданного в Azure AD, вам потребуется создать новую учетную запись для этого пользователя в локальной AD, настроить учетную запись на месте, а затем синхронизировать учетную запись с помощью поддерживаемой версии средства подключения Azure AD. 
  
Включение пользователя для телефонной системы с локальной возможностью подключения к PSTN, а затем их перемещение в Skype для бизнеса Online требует следующих действий:
  
- [Включить пользователей для Корпоративная голосовая связь](enable-the-users-for-enterprise-voice-on-premises.md) на месте (выполняется, пока пользователи находятся в локальном помещении).
    
- [Назначьте политику маршрутинга голосовой](assign-a-voice-routing-policy.md) связи (выполняемую в то время, когда пользователи находятся в локальном помещении).
    
- [Синхронизировать пользователей с облаком и назначить лицензии](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (выполняемые с помощью Office 365).
    
- [Перемещение локального](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) пользователя в Skype для бизнеса Online (выполняется с Windows PowerShell локально, но с помощью учетных данных администратора Office 365).
    
- [Включить пользователей для Корпоративная голосовая связь голосовой почты](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) и телефонной системы (выполняется с помощью удаленной powerShell.

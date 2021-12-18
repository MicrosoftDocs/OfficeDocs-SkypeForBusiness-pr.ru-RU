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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'В этом разделе описывается, как включить пользователей для телефонная система с локальной подключением PSTN. Прежде чем следовать шагам в этом разделе, необходимо прочитать следующее: .'
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563666"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Активация пользователей телефонной системы с соединением по локальной ТСОП в Skype для бизнеса Server

В этом разделе описывается, как включить пользователей для телефонная система с локальной подключением PSTN. Прежде чем следовать шагам в этом разделе, необходимо прочитать следующее: .
  
- Чтобы узнать, как настроить гибридную связь, см. в этой Skype для бизнеса Server и [Skype для бизнеса Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) и развертывание гибридного подключения между Skype для бизнеса Server [и Skype для бизнеса Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
    
- Подробнее о планировании развертывания см. в телефонная система plan [Skype для бизнеса Server.](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- Дополнительные дополнительные телефонная система, включая лицензирование и планы, см. в [Skype для бизнеса.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> Skype для бизнеса Online была отменена 31 июля 2021 г. И подключение КПС между локальной средой, будь то Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online, больше не поддерживается. Узнайте, как подключить сеть локальной телефонии к Teams с помощью [прямого маршрутного маршрутинга.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Перемещение пользователей в телефонная система с локальной подключением PSTN

Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить пользователей в локальной Skype для бизнеса Server или Lync Server 2013, а затем переместить их в Интернет. Дополнительные сведения см. в разделе [Планирование гибридного](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) подключения между Skype для бизнеса Server и Skype для бизнеса Online и разделом особых соображений Enable the users for Корпоративная голосовая связь on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется в то время как пользователи находятся в локальном помещении). 
  
Все пользователи должны создаваться в Active Directory на локальной основе и синхронизироваться с Microsoft 365 или Office 365 с помощью поддерживаемой версии разъема Azure AD. Нельзя включить пользователей для телефонная система в Office 365, созданных непосредственно в Azure AD. Если вы хотите включить телефонная система с локальной подключением PSTN для пользователя, созданного в Azure AD, вам потребуется создать новую учетную запись для этого пользователя в локальной AD, настроить учетную запись на месте, а затем синхронизировать учетную запись с помощью поддерживаемой версии средства подключения Azure AD. 
  
Включение пользователя для телефонная система локального подключения к PSTN, а затем перемещение его в Skype для бизнеса Online требует следующих действий:
  
- [Включить пользователей для Корпоративная голосовая связь](enable-the-users-for-enterprise-voice-on-premises.md) на месте (выполняется, пока пользователи находятся в локальном помещении).
    
- [Назначьте политику маршрутинга голосовой](assign-a-voice-routing-policy.md) связи (выполняемую в то время, когда пользователи находятся в локальном помещении).
    
- [Синхронизировать пользователей с облаком и назначить лицензии](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (выполняемые с Office 365).
    
- [Перемещение локального](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) пользователя в Skype для бизнеса Online (выполняется с Windows PowerShell локально, но с Office 365 учетными данными администратора).
    
- [Включить пользователей для Корпоративная голосовая связь и телефонная система](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) голосовой почты (выполняется с помощью удаленной powerShell.

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
description: 'В этом разделе описывается, как включить для пользователей телефонную систему с локальной связью через STN. Прежде чем следовать шагам в этом разделе, ознакомьтесь со следующими разделами:'
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359145"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Активация пользователей телефонной системы с соединением по локальной ТСОП в Skype для бизнеса Server

В этом разделе описывается, как включить для пользователей телефонную систему с локальной связью через STN. Прежде чем следовать шагам в этом разделе, ознакомьтесь со следующими разделами:
  
- To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
    
- Чтобы узнать о планировании развертывания, см. план телефонной системы с локальной связью по [STN в Skype для бизнеса Server.](plan-phone-system-with-on-premises-pstn-connectivity.md)
    
- Дополнительные информацию о телефонной системе, в том числе о лицензировании и планах, см. в планах звонков по [STN для Skype для бизнеса.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.  Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.  Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Перемещение пользователей в телефонную систему с локальной связью через STN

Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить пользователей локально в Skype для бизнеса Server или Lync Server 2013, а затем переместить их в Интернет. Дополнительные сведения см. в разделе "Планирование гибридного подключения между Skype для бизнеса Server и Skype для бизнеса [Online",](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) а также в разделе "Enable the users for Корпоративная голосовая связь on premises (performed while the users are homed on-premises)." [](enable-the-users-for-enterprise-voice-on-premises.md) 
  
Все пользователи должны быть созданы локально в Active Directory и синхронизированы с Microsoft 365 или Office 365 с помощью поддерживаемой версии Azure AD Connector. Нельзя включить для пользователей телефонной системы в Office 365, созданных непосредственно в Azure AD. Если вы хотите включить телефонную систему с локальной связью через STN для пользователя, созданного в Azure AD, необходимо создать новую учетную запись для этого пользователя в локальной службе AD, настроить учетную запись локально, а затем синхронизировать учетную запись с помощью поддерживаемой версии средства Azure AD Connector. 
  
Для включения для пользователя телефонной системы с локальной связью через STN и их перемещения в Skype для бизнеса Online необходимо сделать следующее:
  
- [Включить для пользователей локальное Корпоративная голосовая связь](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется, когда пользователи находятся в локальной сети).
    
- [Назначьте политику маршрутной связи голосовой](assign-a-voice-routing-policy.md) связи (которая выполняется, когда пользователи находятся в локальной сети).
    
- [Синхронизация пользователей с облаком](synchronize-users-to-the-cloud-and-assign-licenses.md) и назначение лицензий (выполняется с помощью Office 365).
    
- [Перемещение пользователей локальной](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) сети в Skype для бизнеса Online (выполняется с помощью Windows PowerShell локальной службы, но с использованием учетных данных администратора Office 365).
    
- [В этом Корпоративная голосовая связь голосовой почты в](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) Интернете и телефонной системе (выполняется с помощью удаленной powerShell).
    


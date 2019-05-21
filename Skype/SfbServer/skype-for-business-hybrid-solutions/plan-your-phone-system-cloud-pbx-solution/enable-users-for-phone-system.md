---
title: Включение пользователей для телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: В этой статье описано, как включить пользователей для телефонной системы в Office 365 с помощью локальной сети PSTN. Перед выполнением действий, описанных в этом разделе, ознакомьтесь со статьей ниже.
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287463"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Включение пользователей для телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server
 
В этой статье описано, как включить пользователей для телефонной системы в Office 365 с помощью локальной сети PSTN. Перед выполнением действий, описанных в этом разделе, ознакомьтесь со статьей ниже.
  
- Сведения о настройке гибридного подключения можно найти в статье [планирование гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и [развертывание гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Сведения о планировании развертывания можно найти в статье [планирование телефонной системы в Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Дополнительные сведения о телефонной системе в Office 365, в том числе о лицензировании и планах, приведены в статье [планы звонков по PSTN для Skype для бизнеса](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Перемещение пользователей в телефонную систему в Office 365 с помощью локальной сети PSTN

Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить пользователей в Skype для бизнеса Server или Lync Server 2013 и переместить их в сети. Дополнительные сведения можно найти в статье [планирование гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) , а также в разделе вопросы и сведения о том, как [включить локальную связь пользователей с корпоративными организациями](enable-the-users-for-enterprise-voice-on-premises.md) (выполняются при подключении пользователей). локально). 
  
Все пользователи должны быть созданы в службе каталогов Active Directory локально и синхронизированы с Office 365 с помощью поддерживаемой версии Azure AD Connector. Вы не можете включить пользователей для телефонной системы в Office 365, которые были созданы непосредственно в Azure AD. Если вы хотите включить телефонную систему в Office 365 с локальной связью по протоколу КТСОП для пользователя, который был создан в Azure AD, вам потребуется создать новую учетную запись для этого пользователя в локальной службе AD, настроить ее локальную учетную запись, а затем синхронизировать ее с помощью Поддерживаемая версия средства Azure AD Connector. 
  
Включение пользователя для телефонной системы в Office 365 со встроенным подключением PSTN и последующим переносом в Skype для бизнеса Online необходимо выполнить следующие действия:
  
- [Включение локальных пользователей для корпоративного голосовой связи](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется, когда пользователи размещаются в локальной сети).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (выполняется, пока пользователи размещены в локальной среде).
    
- [Синхронизация пользователей с облаком и назначение лицензий](synchronize-users-to-the-cloud-and-assign-licenses.md) (выполняется с помощью Office 365).
    
- [Перемещение локальных пользователей в Skype для бизнеса Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (выполняется локально с помощью Windows PowerShell, но с помощью учетных данных администратора Office 365).
    
- [Предоставление пользователям корпоративной сети голосовой и телефонной системы в Office 365 голосовой почты](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (выполняется с помощью удаленной оболочки PowerShell.
    


---
title: Активация пользователей телефонной системы с возможностью подключения к локальной ТСОП в Skype для бизнеса Server
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
description: В этом разделе описывается, как включить для пользователей телефонную систему с локальной связью PSTN. Перед выполнением действий, описанных в этом разделе, необходимо прочесть следующее:.
ms.openlocfilehash: 9cd5fe66b6092b0ac21af4c425f662d18d96ab49
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221099"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Активация пользователей телефонной системы с возможностью подключения к локальной ТСОП в Skype для бизнеса Server
 
В этом разделе описывается, как включить для пользователей телефонную систему с локальной связью PSTN. Перед выполнением действий, описанных в этом разделе, необходимо прочесть следующее:.
  
- Чтобы узнать, как настроить гибридное подключение, ознакомьтесь со статьей [планирование гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и [развертывание гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Чтобы узнать о планировании развертывания, ознакомьтесь [со статьей Планирование телефонной системы с локальной связью PSTN в Skype для бизнеса Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Дополнительные сведения о телефонной системе, в том числе о лицензировании и планах, приведены в статье [планы звонков PSTN для Skype для бизнеса](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Перемещение пользователей в телефонную систему с использованием локальной сети PSTN

Перед перемещением пользователей в Skype для бизнеса Online рекомендуется включить локальные пользователи в Skype для бизнеса Server или Lync Server 2013, а затем переместить их в оперативный режим. Для получения дополнительных сведений ознакомьтесь с разделом [планирование гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) , а также разделом вопросы, связанными с разделом вопросы и предложения по [включению локальных пользователей](enable-the-users-for-enterprise-voice-on-premises.md) (выполняются, когда пользователи размещены в локальной среде). 
  
Все пользователи должны быть созданы в локальной службе Active Directory и синхронизированы с Microsoft 365 или Office 365 с помощью поддерживаемой версии соединителя Azure AD. Вы не можете включить пользователей для телефонной системы в Office 365, которые были созданы непосредственно в Azure AD. Если вы хотите включить телефонную систему с локальной связью PSTN для пользователя, созданного в Azure AD, вам потребуется создать новую учетную запись для этого пользователя в локальной службе Active Directory, настроить локальную учетную запись, а затем синхронизировать учетную запись с помощью поддерживаемой версии средства Azure AD Connector. 
  
Чтобы включить пользователя для телефонной системы с локальной сетью PSTN, а затем перенести их в Skype для бизнеса Online, необходимо выполнить следующие действия:
  
- [Разрешите пользователям локальное подключение к корпоративной голосовой связи](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется, пока пользователи размещены в локальной среде).
    
- [Назначение политики маршрутизации голосовой связи](assign-a-voice-routing-policy.md) (выполняется, когда пользователи размещены в локальной среде).
    
- [Синхронизация пользователей с облаком и назначение лицензий](synchronize-users-to-the-cloud-and-assign-licenses.md) (выполняется с помощью Office 365).
    
- [Перемещение локальных пользователей в Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (выполняется с помощью Windows PowerShell в локальной среде, но с использованием учетных данных администратора Office 365).
    
- [Разрешить пользователям для корпоративной голосовой связи и голосовой почты телефонной системы](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (выполняется с помощью удаленной оболочки PowerShell).
    


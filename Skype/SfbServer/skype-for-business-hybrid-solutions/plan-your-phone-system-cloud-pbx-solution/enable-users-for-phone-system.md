---
title: Включение пользователей для телефонной системой в Office 365 с помощью локального подключения к ТСОП в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
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
description: В этом разделе описываются предоставлению пользователям разрешения для телефонной системой в Office 365 с помощью локального подключения к ТСОП. Прежде чем выполнять действия, описанные в этом разделе, прочитайте следующие:.
ms.openlocfilehash: 7427bf33c275d55b99c240aaf192d180c2d63945
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "30642210"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Включение пользователей для телефонной системой в Office 365 с помощью локального подключения к ТСОП в Скайп для Business Server
 
В этом разделе описываются предоставлению пользователям разрешения для телефонной системой в Office 365 с помощью локального подключения к ТСОП. Прежде чем выполнять действия, описанные в этом разделе, прочитайте следующие:.
  
- Узнайте, как настроить гибридного подключения, приведены в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и [развертывания гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Дополнительные сведения о планировании развертывания, содержатся [Планирование телефонной системы в Office 365 с помощью локального подключения к ТСОП в Скайп для Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Чтобы узнать больше о телефонной системой в Office 365, включая лицензирования и планы, видеть [вызов ТСОП планов для Скайп для бизнеса](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Переход на телефонной системой в Office 365 с помощью локального подключения к ТСОП

Перед перемещением пользователей на Скайп для бизнеса в Интернет, рекомендуется включить пользователей локально в Скайп для Business Server или Lync Server 2013 и переместите их в Интернете. Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) и в разделе необходимо учитывать для [предоставления пользователям корпоративной голосовой связи на локальном](enable-the-users-for-enterprise-voice-on-premises.md). 
  
Все пользователи должен быть создан в Active Directory при локальном и синхронизируются с Office 365 с помощью поддерживаемая версия соединителя Azure AD. Пользователи не могут включить для телефонной системой в Office 365, которые были созданы непосредственно в Azure AD. Если вы хотите включить телефонной системой в Office 365 с помощью подключения к ТСОП локального пользователя, который был создан в Azure AD, необходимо создать новую учетную запись для этого пользователя в своей локальной AD, настройте учетную запись локальной и затем синхронизировать с помощью учетной записи поддерживаемая версия соединительной Azure AD. 
  
Включение пользователю телефонной системой в Office 365 с помощью подключения к ТСОП в локальной и перемещая их в Скайп для бизнеса Online необходимо выполнить следующие действия:
  
- [Включение пользователей для корпоративной голосовой связи локально](enable-the-users-for-enterprise-voice-on-premises.md) (выполняется в то время как пользователи, размещенные локально).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (выполняется, пока пользователи размещены в локальной среде).
    
- [Синхронизация пользователей в облаке и назначение лицензий](synchronize-users-to-the-cloud-and-assign-licenses.md) (выполняется с помощью Office 365).
    
- [Переместите пользователей в локальной Скайп для бизнеса в Интернет](move-on-premises-users-to-skype-for-business-online.md) (выполняется с помощью Windows PowerShell в локальной, но с помощью учетных данных администратора Office 365).
    
- [Включить пользователей для корпоративной голосовой связи через Интернет и телефонной системой в голосовой почты Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (выполняется с помощью удаленной оболочки PowerShell).
    


---
title: Лицензия на программное обеспечение skype room System Skype для бизнеса
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе вы узнаете, как проверить, есть ли у вас лицензия на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833929"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Система комнат Skype: лицензия на программное обеспечение Skype для бизнеса
 
В этом разделе вы узнаете, как проверить, есть ли у вас лицензия на программное обеспечение Skype для бизнеса. 
  
Система комнат Skype использует установленный клиент Skype для бизнеса, для которого требуется лицензия на программное обеспечение. Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).
  
## <a name="key-management-servers-kms"></a>Серверы управления ключами (KMS)

Если kmS на месте и будет распространять активации с много лицензиями skype для бизнеса, система комнат Skype автоматически активирует клиент Skype для бизнеса. Чтобы узнать, есть ли KMS:
  
В командной командной области запустите 3:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Дополнительные сведения см. в сведениях о том, как обнаружить точки KMS Office и Windows через DNS и удалить [несанкционированные экземпляры.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Чтобы настроить KMS, см. [kms activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Универсальный ключ volume License Key для Lync в Office 2013: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ заставляет систему комнат Skype искать KMS в сети).)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Ключи многократной активации (MAK) из Volume License Service Center (VLSC)

Если клиент использует любое другое программное обеспечение с много лицензиями, ИТ-отдел будет управлять активацией программного обеспечения и соглашением о программе volume License Agreement (VLA) с помощью VLSC. Это также позволит компании приобрести VL-активации Skype для бизнеса, после чего компания может получить mak для ввода в консоли администрирования системы комнат Skype.
  
Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK. Если это не так, финансовый отдел клиента должен иметь возможность подтвердить, что клиент оплатил VLA.
  
Чтобы получить mak, получите доступ к Центру обслуживания корпоративного лицензирования, чтобы просмотреть соглашения и скачать ключи продукта (MAK). Дополнительные сведения можно найти в [Центре обслуживания корпоративного лицензирования.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK для Microsoft 365 или Office 365 без доступа к VLSC

Если у клиента нет соглашения о много лицензии, управлять активацией Skype для бизнеса будет намного сложнее. Однако пользователи Microsoft 365 и Office 365 без доступа по VLSC могут получить рекламный MAK, предоставив следующие сведения OEM, продающий систему комнат Skype:
  
- Имя компании
    
- Имя контакта развертывания, электронная почта и номер телефона
    
- Количество развернутых систем
    
- Дата развертывания
    
- Если у клиента есть диспетчер технических учетных записей Майкрософт, имя и контактные данные менеджера
    


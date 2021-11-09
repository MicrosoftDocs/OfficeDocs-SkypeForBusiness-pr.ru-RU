---
title: Skype Лицензия Skype для бизнеса системы номеров
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Ознакомьтесь с этой темой, чтобы узнать, есть ли у Skype для бизнеса лицензия на программное обеспечение.
ms.openlocfilehash: 805a9abb6d4d49e653e779edc1d9e1cfb8d2a6ca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845972"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Система номеров: Skype для бизнеса лицензия на программное обеспечение
 
Ознакомьтесь с этой темой, чтобы узнать, есть ли у Skype для бизнеса лицензия на программное обеспечение. 
  
Skype Room System использует установленный Skype для бизнеса клиент, для которого требуется лицензия на объем программного обеспечения. Перед развертыванием Skype системы номеров узнайте состояние лицензии на объем развертывания с помощью серверов управления ключами (KMS) или нескольких ключей активации (MAK).
  
## <a name="key-management-servers-kms"></a>Серверы управления ключами (KMS)

Если KMS на месте и будет распространять Skype для бизнеса том лицензии, Skype система номеров автоматически активирует Skype для бизнеса клиента. Чтобы узнать, KMS ли они на месте:
  
Из командной подсказки запустите:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Чтобы настроить KMS, KMS активации [Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) г. и GVLKs для KMS и active [Directory активации Office 2013](/DeployOffice/vlactivation/gvlks) г.
  
Office 2013 общий ключ лицензии на объем для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Этот ключ заставляет систему Skype комнаты искать KMS в сети.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Несколько ключей активации (MAK) из Центра обслуживания лицензий на объем (VLSC)

Если клиент использует любое другое программное обеспечение лицензии на объем, ИТ-отдел будет управлять активациями программного обеспечения и соглашением о лицензиях на объем (VLA) с помощью VLSC. Это также позволит компании приобрести Skype для бизнеса VL-активаций, после чего компания может получить MAK для ввода в консоли администратора Skype системы номеров.
  
Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK. В случае неопределенности финансовый отдел клиента должен иметь возможность подтвердить, оплатил ли клиент VLA.
  
Чтобы получить MAK, вы можете получить доступ к Центру службы лицензирования томов для просмотра соглашений и скачивания ключей продукта (MAK). Дополнительные сведения перейдите в [Центр обслуживания лицензирования томов.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK для Microsoft 365 или Office 365 без доступа к VLSC

Если у клиента нет соглашения о лицензии на объем, Skype для бизнеса активации будет гораздо сложнее управлять. Однако Microsoft 365 и Office 365 клиенты без доступа к VLSC могут получить рекламный MAK, предоставив OEM-службе, продав Skype систему номеров:
  
- Имя компании
    
- Имя контакта развертывания, электронная почта и номер телефона
    
- Количество развернутых систем
    
- Дата развертывания
    
- Если у клиента есть менеджер технической учетной записи Майкрософт, имя и контактные данные tam

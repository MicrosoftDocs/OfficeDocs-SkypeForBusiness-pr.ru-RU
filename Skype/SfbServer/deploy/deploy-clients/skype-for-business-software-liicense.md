---
title: Лицензия на программное обеспечение Skype Room System Skype для бизнеса
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
description: Ознакомьтесь с этой темой, чтобы узнать, есть ли у вас лицензия на объем программного обеспечения Skype для бизнеса.
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113095"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Система номеров Skype: лицензия на программное обеспечение Skype для бизнеса
 
Ознакомьтесь с этой темой, чтобы узнать, есть ли у вас лицензия на объем программного обеспечения Skype для бизнеса. 
  
Система номеров Skype использует установленный клиент Skype для бизнеса, для которого требуется лицензия на объем программного обеспечения. Перед развертыванием первой системы номеров Skype узнайте состояние лицензии на объем развертывания с помощью серверов управления ключами (KMS) или нескольких ключей активации (MAK).
  
## <a name="key-management-servers-kms"></a>Серверы управления ключами (KMS)

Если kmS на месте и будет распространять активации лицензии Skype для бизнеса, система номеров Skype автоматически активирует клиент Skype для бизнеса. Чтобы узнать, на месте ли KMS:
  
Из командной подсказки запустите:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Дополнительные сведения см. в примере Обнаружение хостов Office и Windows KMS с помощью DNS и удаление [несанкционированных экземпляров.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Чтобы создать KMS, см. в рублях [активация KMS Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) и GVLKs для KMS и активации [Active Directory Office 2013](/DeployOffice/vlactivation/gvlks)
  
Универсальный ключ лицензии на объем Office 2013 для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ заставляет систему номеров Skype искать KMS в сети.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Несколько ключей активации (MAK) из Центра обслуживания лицензий на объем (VLSC)

Если клиент использует любое другое программное обеспечение лицензии на объем, ИТ-отдел будет управлять активациями программного обеспечения и соглашением о лицензиях на объем (VLA) с помощью VLSC. Это также позволит компании приобрести активации Skype для бизнеса VL, после чего компания может получить MAK для ввода в консоли администрирования системы Skype Room.
  
Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK. В случае неопределенности финансовый отдел клиента должен иметь возможность подтвердить, оплатил ли клиент VLA.
  
Чтобы получить MAK, вы можете получить доступ к Центру службы лицензирования томов для просмотра соглашений и скачивания ключей продукта (MAK). Дополнительные сведения перейдите в [Центр обслуживания лицензирования томов.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK для Microsoft 365 или Office 365 без доступа к VLSC

Если у клиента нет соглашения о лицензии на объем, активации Skype для бизнеса будут намного сложнее управлять. Однако клиенты Microsoft 365 и Office 365 без доступа к VLSC могут получить рекламный MAK, предоставив OEM-службе по продаже системы номеров Skype следующие сведения:
  
- Имя компании
    
- Имя контакта развертывания, электронная почта и номер телефона
    
- Количество развернутых систем
    
- Дата развертывания
    
- Если у клиента есть менеджер технической учетной записи Майкрософт, имя и контактные данные tam

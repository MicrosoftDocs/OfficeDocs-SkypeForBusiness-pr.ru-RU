---
title: Лицензия на программное обеспечение Skype для бизнеса на комнате Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: d1d04dc6c80d4e7e04b6ed7a946dfc393a308933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287687"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Система комнат Skype: лицензия на использование программного обеспечения Skype для бизнеса
 
В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса. 
  
Система комнат Skype использует установленный клиент Skype для бизнеса, для которого требуется программная лицензия. Перед развертыванием первой системы комнаты Skype ознакомьтесь с корпоративным состоянием лицензии на развертывание (с помощью серверов управления ключами (KMS) или ключа многократной активации (MAK).
  
## <a name="key-management-servers-kms"></a>Серверы управления ключами (KMS)

Если на вашем компьютере установлены службы KMS и они будут распространяться на активацию корпоративного лицензирования в Skype для бизнеса, система помещения в Skype будет автоматически активировать клиент Skype для бизнеса. Чтобы узнать, настроены ли серверы управления ключами, выполните следующие действия.
  
В командной строке выполните:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Дополнительные сведения [можно найти в разделе Обнаружение узлов Office и KMS в службе DNS и удаление неавторизованных экземпляров](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Сведения о настройке KMS-активации можно найти в разделе [Активация KMS для office 2013](https://technet.microsoft.com/library/ee624357.aspx) и [гвлкс для KMS и Active Directory активация Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Корпоративная лицензия Office 2013 для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ приводит к тому, что система комнаты Skype будет искать сервер службы KMS в сети).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Ключи многократной активации (MAK) из Volume Licensing Service Center (VLSC)

If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC. Это также позволит компании приобрести активацию корпоративной лицензии Skype для бизнеса, после чего компания сможет получить MAK для ввода данных в консоли администрирования системы комнат Skype.
  
Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK. Если это не было уверенно, финансовый отдел клиента должен подтвердить, оплачивается ли клиент для ВЛА.
  
Для получения MAK необходимо перейти в Volume Licensing Service Center для просмотра соглашения и загрузки ключей продукта (MAK). Дополнительные сведения можно найти в [центре обслуживания для корпоративного лицензирования](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK для Office 365 без получения доступа к VLSC

Если у клиента нет соглашения о корпоративном лицензировании, активация Skype для бизнеса будет сложнее управлять. Тем не менее, пользователи Office 365, у которых нет доступа к централизованному доступу, могут получить рекламный ключ MAK, предоставив следующие данные для OEM-компании, продающей систему комнаты Skype:
  
- Название компании
    
- Имя, адрес электронной почты и номер телефона контактного лица по вопросам развертывания
    
- Количество развернутых систем
    
- Дата развертывания
    
- Если у клиента есть технический консультант Microsoft, имя и контактные данные у КОНСУЛЬТАНТа
    


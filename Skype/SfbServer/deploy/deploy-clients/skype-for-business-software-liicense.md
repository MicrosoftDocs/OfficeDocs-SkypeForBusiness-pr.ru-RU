---
title: Скайп системы Скайп комнаты для бизнеса лицензии на программное обеспечение
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса.
ms.openlocfilehash: e4ba03dacdce0056cb130299f551921042a6790d
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699261"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Система комнат Skype: лицензия на использование программного обеспечения Skype для бизнеса
 
В этом разделе описывается проверка наличия корпоративной лицензии на программное обеспечение Skype для бизнеса. 
  
Система комнаты Скайп использует установленные Скайп для бизнеса клиент, который требуется лицензия корпоративного программного обеспечения. Перед развертыванием первого системы комнаты Скайп Узнайте состояние лицензии корпоративного развертывания — с помощью серверов управления ключами (KMS) или ключи многократной активации (MAK).
  
## <a name="key-management-servers-kms"></a>Серверы управления ключами (KMS)

Если будет распространять Скайп для бизнеса многократной активации KMS на месте, система комнаты Скайп автоматически включает Скайп для клиента Business. Чтобы узнать, настроены ли серверы управления ключами, выполните следующие действия.
  
В командной строке выполните следующую команду:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Для получения дополнительных сведений см [Обнаружение узлов Windows KMS и Office с помощью DNS и удаление несанкционированного экземпляров](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Сведения о настройке KMS см. в разделах [Активация Office 2013 с помощью KMS](https://technet.microsoft.com/library/ee624357.aspx) и [Ключи GVLK для KMS и активации Active Directory в Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Office 2013 универсальный ключ многократной установки для Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (этот ключ система Скайп комнаты следует искать KMS в сети.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Ключи многократной активации (MAK) из Volume Licensing Service Center (VLSC)

If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC. Это также включает компании на покупку Скайп для активации корпоративного лицензирования бизнеса, после которого компании могут получить MAK для ввода данных в консоль администратора системы Скайп помещений.
  
Клиент с VLA должен знать свои учетные данные VLSC, которые будут использоваться для администрирования соглашения и получения MAK. Если определен, должна появиться возможность подтверждение, если клиент оплату за VLA клиента финансового отдела.
  
Для получения MAK необходимо перейти в Volume Licensing Service Center для просмотра соглашения и загрузки ключей продукта (MAK). Дополнительные сведения см. в [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK для Office 365 без получения доступа к VLSC

Если клиент не имеет корпоративного лицензирования, будет гораздо сложнее управлять Скайп для активации бизнеса. Тем не менее пользователи Office 365 без доступа к VLSC могут получить рекламное MAK с указанием следующих сведений ПВТ система комнаты Скайп продажи:
  
- Название компании
    
- Имя, адрес электронной почты и номер телефона контактного лица по вопросам развертывания
    
- Число систем
    
- Дата развертывания
    
- Если клиент имеет Microsoft технического специалиста, СПЕЦИАЛИСТ по имени и контактной информации
    


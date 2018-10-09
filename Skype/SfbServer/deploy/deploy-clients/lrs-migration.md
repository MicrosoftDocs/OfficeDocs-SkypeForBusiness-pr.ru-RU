---
title: Перенос системы комнаты Lync устройств системе комнаты Скайп версии 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: В данном разделе приведены в этой статье описывается перенос системы комнаты Lync устройств для использования версии 2 Скайп комнаты системного программного обеспечения.
ms.openlocfilehash: b6c11e101ab3984f934dab1a9e06d80df3ce5e4f
ms.sourcegitcommit: 80e1983fd631b8ad63c902375f1128faa957e374
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "25450650"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Перенос устройств системы Lync комнаты (LRS) в системе комнаты Скайп версии 2 
[Окончание поддержки на 9 октября 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)достигнет устройств системы Lync комнаты (LRS) с помощью программ Скайп комнаты системы версии 1 (SRS v1). Это означает, что программное обеспечение v1 Скайп комнаты систем не будет любой обновлений продукта или исправления после указанной даты. Пользователям с Lync комнаты системных устройств с использованием Скайп комнаты системное программное обеспечение v1 рекомендуется обновить свои устройства системы комнаты Скайп версии 2 (SRS v2).

Программное обеспечение Скайп комнаты системы версии 2 (SRS v2) работает с группами Майкрософт в дополнение к Скайп Business Server и Online Services для собраний и вызова на всех устройствах SRS поддерживаемые версии 2.

Ваше существующего устройства **может** продолжать работу после окончания v1 Скайп комнаты системное программное обеспечение поддержки. Это программное обеспечение в конечном счете сбора данных, которое должно Microsoft для освобождения исправление ошибки программного обеспечения или могут иметь случая, где существующего протокола обмена данными используемые изменения программного обеспечения v1 Скайп комнаты системы или больше не поддерживаются. Одно из таких известных изменений является об использовании TLS 1.0 / 1.1 в Microsoft Office 365. Дополнительные сведения о [Подготовка TLS 1.0/1.1, которые будут отменены](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).  

## <a name="which-devices-are-affected"></a>Какие устройства будут затронуты?
Ниже приведен список устройств, которые затрагиваются это изменение:
- [Смарт-систем комнаты](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- Crestron RL

## <a name="upgrade-options"></a>Варианты обновления
Существует несколько вариантов обновления Lync комнаты систем следующего поколения Скайп комнаты систем (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Программа Trade-in Crestron оборудование
Для всех клиентов системы комнаты Lync не Crestron Crestron обеспечит обновления [Crestron SR системы](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) или иметь эквивалентные права. Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.  


### <a name="crestron-rl2-to-rl3"></a>Crestron RL2 для RL3
Существующие клиенты Crestron RL2 (также называется Crestron RL200) можно получить в пакет обновления для обновления текущей RL2 RL3, используя для минимальными затратами на устройство. Ознакомиться с подробными сведениями этой программы [здесь](https://support.crestron.com/app/answers/answer_view/a_id/1000220) или <!-- For details, --> [электронной почты](mailto:lrsupgrade@crestron.com) Crestron LRS поддержки.  


### <a name="smart-room-systems-upgrade"></a>Обновление смарт-систем комнаты 
Для клиентов, смарт-LRS, за исключением программы trade-in Crestron оборудования Корпорация Майкрософт и СМАРТ также работают на предоставление решений для обновления до версии 2 Скайп комнаты системы. Это обновление предлагается с помощью ИНТЕЛЛЕКТУАЛЬНОГО все существующие клиенты смарт-LRS. Дополнительные сведения об этой программы будет предоставляться на этой странице в 2018 октября. Убедитесь, что на наличие обновлений.

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a>Что делать?
Мы рекомендуем планируется обновить систему комнаты Lync устройств систем комнаты Скайп версии 2 до устаревания TLS 1.0/1.1, с помощью параметров обновления уже было сказано. Кроме того также можно замена существующего устройства на новых устройств, сертифицированном для SRS версии 2. Просмотреть [устройств комнаты](https://aka.ms/roomdevices) для получения дополнительных сведений и также взглянем на [требования к версии 2 Скайп комнаты систем](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Функции сенсорного ввода и доски еще не поддерживается в системе комнаты Скайп версии 2. Поддержка сенсорного ввода и доски находится в невыполненной работы для системы комнаты Скайп версии 2 и будет добавлен в H1 CY2019.

> [!NOTE]
> Программное обеспечение Скайп комнаты системы версии 2 в настоящее время не поддерживает протокол TLS 1.2. Поддержка TLS 1.2 работает на и будут выполнены до 1/0/1.1 TLS амортизации. Upgradging клиентов к версии 2 SRS не будут отображаться любые влияния амортизации TLS 1.0/1.1 на комнаты устройств с последней версией приложения SRS версии 2.

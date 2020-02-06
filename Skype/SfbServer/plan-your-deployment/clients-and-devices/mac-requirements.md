---
title: Клиентские требования Skype для бизнеса для Mac
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: В этой статье рассказывается о требованиях к оборудованию, программному обеспечению и инфраструктуре для работы Skype для бизнеса на компьютере Mac.
ms.openlocfilehash: 08f3aeabbfd88b432c28f05727ec7cf009e297a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803599"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Клиентские требования Skype для бизнеса для Mac
 
В этой статье рассказывается о требованиях к оборудованию, программному обеспечению и инфраструктуре для работы Skype для бизнеса на компьютере Mac.
  
[Клиент Skype для бизнеса для Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) доступен для скачивания.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Требования к оборудованию и программному обеспечению для Skype для бизнеса на Mac

Для клиента Skype для бизнеса на Mac требуется Mac OS X El Capitan и более поздней версии, а также используется не менее 100 МБ свободного места на диске. Мы поддерживаем все встроенные звуковые и видеоустройства. Внешние устройства должны входить в [Каталог решений Skype для бизнеса](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Этот список является предварительным и некоторые устройства могут быть квалифицированы для Lync, но не поддерживаются в Skype для бизнеса на компьютере Mac. Ознакомьтесь с [требованиями к системе](https://products.office.com/en-us/office-system-requirements) для минимального необходимого оборудования.
  
### <a name="legacy-mac-clients"></a>Клиенты для Mac прежних версий

Skype для бизнеса Server 2015 также поддерживает следующие устаревшие клиенты на компьютерах с операционной системой Mac OS 10.5.8 или более поздней версии или пакетом обновления (ОС для Mac OS 10,9 в настоящее время не поддерживается). Подробные сведения о поддерживаемых функциях можно найти в разделе [Сравнение функций клиента для настольных компьютеров для Skype для бизнеса](desktop-feature-comparison.md).
  
- Microsoft Lync для Mac 2011 (см. [руководство по развертыванию Lync для 2011 Mac](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator для Mac 2011 (см. [руководство по развертыванию Communicator для 2011 Mac](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Эти клиенты не поддерживаются в Skype для бизнеса Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Требования к инфраструктуре Skype для бизнеса на Mac
<a name="Infrastructure"> </a>

Клиент Skype для бизнеса для Mac использует как платформу управления унифицированными связями (УКМП), так и веб-API единой системы обмена сообщениями (УКВА), которые используются нашими клиентами по мобильным технологиям.
  
Требования клиента совпадают с требованиями мобильных клиентов: необходимо развернуть пограничный сервер доступа и обратный прокси-сервер в поддерживаемой конфигурации. 
  
### <a name="authentication"></a>Проверка подлинности

Клиент Skype для бизнеса для Mac поддерживает проверку подлинности на основе сертификатов, Microsoft современной проверки подлинности и многофакторной проверки подлинности при развертывании и включении.
  
> [!NOTE]
> Из-за текущего ограничения учетные данные пользователя Exchange должны совпадать с учетными данными Skype для бизнеса. 
  
### <a name="certificates"></a>Сертификаты

Сертификаты, которые используются на пограничном сервере доступа, обратном прокси-сервере и серверах переднего плана, не должны использовать алгоритм хэширования SHA-512.
  
Список отзыва сертификатов HTTP должен быть определен и доступен для клиента. Например, в качестве списка отзыва сертификатов в сертификате не поддерживается запись LDAP.
  
### <a name="dns"></a>DNS

Для правильной работы Skype для бизнеса на компьютере Mac мобильное приложение должно быть правильно развернуто. Стандартный сценарий сбоя происходит, когда обе следующие записи DNS разрешаются во внутреннюю сеть:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Дополнительные сведения можно найти в статье [развертывание мобильных устройств в Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)и руководство по [мобильному серверу Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>См. также
<a name="Infrastructure"> </a>

[Требования к DNS для Skype для бизнеса Server](../../plan-your-deployment/network-requirements/dns.md)

[Ответы на часто задаваемые вопросы](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Известные проблемы](https://go.microsoft.com/fwlink/p/?LinkId=798228)

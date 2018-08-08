---
title: Скайп для бизнеса на требования к клиентскому Mac
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Прочтите этот раздел, чтобы узнать о оборудование, программное обеспечение и требования к инфраструктуре для запуска Скайп для бизнеса на Mac.
ms.openlocfilehash: 72dfe6aa8479631a3bd3bf6be69e5a5ac2e10dff
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020655"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Скайп для бизнеса на требования к клиентскому Mac
 
Прочтите этот раздел, чтобы узнать о оборудование, программное обеспечение и требования к инфраструктуре для запуска Скайп для бизнеса на Mac.
  
[Скайп для бизнеса на клиентском компьютере Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) доступно для загрузки.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Требования к программному обеспечению и оборудованию для Skype для бизнеса на Mac

Скайп для бизнеса на клиентском компьютере Mac требуется Mac OS X El Capitan и более поздней версии и использует менее 100 МБ дискового пространства. Мы поддерживаем все встроенные звуковые и видеоустройства. Внешние устройства должны быть в [Скайп для каталога бизнес-решений](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Этот список является предварительной и может некоторые устройства могут быть рекомендованные для Lync, но не поддерживается на Скайп для бизнеса на Mac. Обратитесь к [требования к системе](https://products.office.com/en-us/office-system-requirements) для минимальное оборудование, необходимое.
  
### <a name="legacy-mac-clients"></a>Прежних версий клиентов

Скайп для Business Server 2015 также поддерживает следующие устаревших клиентов на компьютерах под управлением Mac OS 10.5.8 или более поздней версии или выпуск (на базе Intel) операционных систем (Mac OS 10,9 операционная система не поддерживается в настоящее время). Для получения дополнительных сведений о поддерживаемых функций видеть [Сравнение функций для настольных компьютеров для Скайп для бизнеса](desktop-feature-comparison.md).
  
- Microsoft Lync для Mac 2011 г. (см [Lync для Mac руководство по развертыванию 2011 г.](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator для Mac 2011 г. (см [Communicator для Mac руководство по развертыванию 2011 г.](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Эти клиенты не поддерживается Скайп для Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Требования к инфраструктуре для Skype для бизнеса на Mac
<a name="Infrastructure"> </a>

Скайп для бизнеса на клиентском компьютере Mac использует объединенные коммуникации управления платформы (UCMP) как, так и Unified Communications Web API (UCWA), используйте наши клиенты мобильной работы.
  
Требования клиента совпадают с требованиями мобильных клиентов: необходимо развернуть пограничный сервер доступа и обратный прокси-сервер в поддерживаемой конфигурации. 
  
### <a name="authentication"></a>Проверка подлинности

Скайп для бизнеса на клиентском компьютере Mac поддерживает проверку подлинности на основе сертификата, современных проверку подлинности Microsoft и многофакторной проверки подлинности при развертывании и включено.
  
> [!NOTE]
> Из-за текущим ограничением учетные данные пользователя Exchange должен совпадать с их Скайп Business учетных данных. 
  
### <a name="certificates"></a>Сертификаты

Сертификаты, которые используются на пограничном сервере доступа, обратном прокси-сервере и серверах переднего плана, не должны использовать алгоритм хэширования SHA-512.
  
Список отзыва сертификатов HTTP должен быть определен и доступен для клиента. Например мы не поддерживают запись LDAP в сертификате как список отзыва сертификатов.
  
### <a name="dns"></a>Служба доменных имен

Мобильной работы необходимо надлежащим образом развертываются для Скайп для бизнеса на клиентском компьютере Mac для правильной работы. Стандартный сценарий сбоя происходит, когда обе следующие записи DNS разрешаются во внутреннюю сеть:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Для получения дополнительных сведений обратитесь: [Руководство по мобильности Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226)и [Развертывание мобильных устройств в Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224).
  
## <a name="see-also"></a>Были ли эти инструкции полезны? Если да, укажите это в конце статьи. Если нет, сообщите нам о недочетах, и мы постараемся найти решение.
<a name="Infrastructure"> </a>

[Требования DNS для Скайп для Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Часто задаваемые вопросы](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Известные проблемы](https://go.microsoft.com/fwlink/p/?LinkId=798228)
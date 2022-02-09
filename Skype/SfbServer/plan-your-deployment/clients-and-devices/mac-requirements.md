---
title: Skype для бизнеса требования к клиентам Mac
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Ознакомьтесь с этой темой, чтобы узнать о требованиях к оборудованию, программному обеспечению и инфраструктуре для Skype для бизнеса на Mac.
ms.openlocfilehash: 5d4e07bda176efa398d8e6766e410be243873bbe
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416472"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype для бизнеса требования к клиентам Mac
 
Ознакомьтесь с этой темой, чтобы узнать о требованиях к оборудованию, программному обеспечению и инфраструктуре для Skype для бизнеса на Mac.
  
Список [Skype для бизнеса Mac Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) доступен для скачивания.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Требования к оборудованию и программному обеспечению для Skype для бизнеса на Mac

Для Skype для бизнеса Mac требуется Mac OS X El Capitan и более высокий уровень и используется не менее 100 МБ дискового пространства. Мы поддерживаем использование всех встроенных аудио- и видео устройств. Внешние устройства должны быть указаны [на Microsoft Teams устройствах](https://www.microsoft.com/microsoft-teams/across-devices/devices). 
  
> [!NOTE]
> Этот список является предварительным, и некоторые устройства могут быть квалифицированы для Lync, но не поддерживаются Skype для бизнеса на Mac. Обратитесь к [требованиям системы к](https://products.office.com/office-system-requirements) минимально необходимому оборудованию.
  
### <a name="legacy-mac-clients"></a>Устаревшие клиенты Mac

Skype для бизнеса Server 2015 г. также поддерживает следующие устаревшие клиенты на компьютерах с операционной системой Mac OS 10.5.8 или последним пакетом служб или выпуска (операционная система Mac OS 10.9 в настоящее время не поддерживается). Подробные сведения о поддерживаемых функциях см. в материале Сравнение функций клиента [для настольных компьютеров для Skype для бизнеса](desktop-feature-comparison.md).
  
- Microsoft Lync для Mac 2011 (см. руководство по развертыванию [Lync для Mac 2011](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14)))
    
- Microsoft Communicator для Mac 2011 (см. Communicator руководства по [развертыванию Mac 2011](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Эти клиенты не поддерживаются Skype для бизнеса Server 2019 г.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Требования к инфраструктуре для Skype для бизнеса mac
<a name="Infrastructure"> </a>

Клиент Skype для бизнеса Mac использует как единую платформу управления коммуникациями (UCMP), так и веб-API единой связи (UCWA), которую используют наши клиенты мобильности.
  
Клиент имеет те же требования, что и наши клиенты мобильности, в том, что в поддерживаемой конфигурации должны быть развернуты сервер Access Edge Server и обратный прокси. 
  
### <a name="authentication"></a>Проверка подлинности

Клиент Skype для бизнеса Mac поддерживает проверку подлинности на основе cert, современную проверку подлинности Майкрософт и многофакторную проверку подлинности при развертывании и включении.
  
> [!NOTE]
> В связи с текущим ограничением учетные данные пользователя Exchange должны быть одинаковыми с Skype для бизнеса учетными данными. 
  
### <a name="certificates"></a>Сертификаты

Сертификаты, которые используются на серверах Access Edge, Reverse Proxy и Front End, не должны использовать алгоритм хаша SHA-512.
  
Список отзыва сертификата HTTP должен быть определен и доступен клиенту. Например, мы не поддерживаем запись LDAP в сертификате в качестве списка отзыва сертификата.
  
### <a name="dns"></a>DNS

Для правильной работы Skype для бизнеса на клиенте Mac необходимо правильно развернуть мобильность. Распространенный сценарий сбоя — разрешить во внутренней сети оба следующих записи DNS:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Дополнительные сведения: Развертывание мобильности в [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility) и Руководство по мобильности [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>См. также
<a name="Infrastructure"> </a>

[Требования DNS для Skype для бизнеса Server](../../plan-your-deployment/network-requirements/dns.md)

[Вопросы и ответы](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Известные проблемы](https://go.microsoft.com/fwlink/p/?LinkId=798228)
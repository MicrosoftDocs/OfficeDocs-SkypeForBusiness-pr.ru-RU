---
title: Требования клиентов Skype для бизнеса на Mac
ms.author: v-cichur
author: cichur
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
description: Ознакомьтесь с этой темой, чтобы узнать о требованиях к оборудованию, программному обеспечению и инфраструктуре для запуска Skype для бизнеса на Mac.
ms.openlocfilehash: e25995173b44cf4f5892c1a34f77529042125c58
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014473"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Требования клиентов Skype для бизнеса на Mac
 
Ознакомьтесь с этой темой, чтобы узнать о требованиях к оборудованию, программному обеспечению и инфраструктуре для запуска Skype для бизнеса на Mac.
  
Skype [для бизнеса на Mac Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) доступен для скачивания.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Требования к оборудованию и программному обеспечению для Skype для бизнеса на Mac

Клиент Skype для бизнеса на Mac требует Mac OS X El Capitan и выше и использует не менее 100 МБ дискового пространства. Мы поддерживаем использование всех встроенных аудио- и видео устройств. Внешние устройства должны быть указаны на [устройствах Microsoft Teams.](https://www.microsoft.com/microsoft-teams/across-devices/devices) 
  
> [!NOTE]
> Этот список является предварительным, и некоторые устройства могут быть квалифицированы для Lync, но не поддерживаются в Skype для бизнеса на Mac. Обратитесь к [требованиям системы к](https://products.office.com/office-system-requirements) минимально необходимому оборудованию.
  
### <a name="legacy-mac-clients"></a>Устаревшие клиенты Mac

Skype для бизнеса Server 2015 также поддерживает следующие устаревшие клиенты на компьютерах с операционной системой Mac OS 10.5.8 или последним пакетом служб или выпуска (операционная система Mac OS 10.9 в настоящее время не поддерживается). Подробные сведения о поддерживаемых функциях см. в материале Сравнение функций клиента [desktop для Skype для бизнеса.](desktop-feature-comparison.md)
  
- Microsoft Lync для Mac 2011 (см. руководство по развертыванию [Lync для Mac 2011)](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))
    
- Microsoft Communicator для Mac 2011 (см. Communicator руководство по развертыванию [Mac 2011)](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14))
 
Эти клиенты не поддерживаются Skype для бизнеса Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Требования к инфраструктуре для Skype для бизнеса на Mac
<a name="Infrastructure"> </a>

Клиент Skype для бизнеса на Mac использует как единую платформу управления коммуникациями (UCMP), так и веб-API единой связи (UCWA), который используют наши клиенты мобильности.
  
Клиент имеет те же требования, что и наши клиенты мобильности, в том, что в поддерживаемой конфигурации должны быть развернуты сервер Access Edge Server и обратный прокси. 
  
### <a name="authentication"></a>Проверка подлинности

Клиент Skype для бизнеса на Mac поддерживает проверку подлинности на основе cert, современную проверку подлинности Майкрософт и многофакторную проверку подлинности при развертывании и включении.
  
> [!NOTE]
> В связи с текущим ограничением учетные данные Exchange пользователя должны быть одинаковыми с учетными данными Skype для бизнеса. 
  
### <a name="certificates"></a>Сертификаты

Сертификаты, которые используются на серверах Access Edge, Reverse Proxy и Front End, не должны использовать алгоритм хаша SHA-512.
  
Список отзыва сертификата HTTP должен быть определен и доступен клиенту. Например, мы не поддерживаем запись LDAP в сертификате в качестве списка отзыва сертификата.
  
### <a name="dns"></a>DNS

Для правильной работы Skype для бизнеса на клиенте Mac необходимо правильно развернуть мобильность. Распространенный сценарий сбоя — разрешить во внутренней сети оба следующих записи DNS:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Дополнительные сведения можно найти в руководстве по мобильности [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)и руководстве по мобильности [Microsoft Lync Server 2010.](https://go.microsoft.com/fwlink//p/?LinkId=798226)
  
## <a name="see-also"></a>См. также
<a name="Infrastructure"> </a>

[Требования DNS для Skype для бизнес-сервера](../../plan-your-deployment/network-requirements/dns.md)

[Вопросы и ответы](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Известные проблемы](https://go.microsoft.com/fwlink/p/?LinkId=798228)
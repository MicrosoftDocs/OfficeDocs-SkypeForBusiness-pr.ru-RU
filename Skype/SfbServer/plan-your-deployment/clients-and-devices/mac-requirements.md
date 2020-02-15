---
title: Требования к клиентам в Skype для бизнеса и Mac
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
description: В этом разделе рассказывается о требованиях к оборудованию, программному обеспечению и инфраструктуре для запуска Skype для бизнеса на Mac.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013462"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Требования к клиентам в Skype для бизнеса и Mac
 
В этом разделе рассказывается о требованиях к оборудованию, программному обеспечению и инфраструктуре для запуска Skype для бизнеса на Mac.
  
[Клиент Skype для бизнеса на Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) доступен для скачивания.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Требования к оборудованию и программному обеспечению для Skype для бизнеса на Mac

Для клиента Skype для бизнеса на Mac требуется Mac OS X El Capitan и более поздней версии, а также по крайней мере 100 МБ свободного места на диске. Поддерживается использование всех встроенных аудио и видеоустройств. Внешние устройства должны находиться в [каталоге решений Skype для бизнеса](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Этот список является предварительным и некоторые устройства могут быть квалифицированы для Lync, но не поддерживаются в Skype для бизнеса на компьютере Mac. Ознакомьтесь с [требованиями к системе](https://products.office.com/office-system-requirements) для минимального необходимого оборудования.
  
### <a name="legacy-mac-clients"></a>Клиенты прежних версий Mac

Skype для бизнеса Server 2015 также поддерживает следующие устаревшие клиенты на компьютерах под управлением ОС Mac OS 10.5.8 или более поздней версии с пакетом обновления или операционной системой на базе корпорации Intel (операционная система Mac OS 10,9 в настоящее время не поддерживается). Дополнительные сведения о поддерживаемых возможностях можно найти в статье [Сравнение функций клиента для настольных ПК в Skype для бизнеса](desktop-feature-comparison.md).
  
- Microsoft Lync для Mac 2011 (см. [руководство по развертыванию Lync для 2011 Mac](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator для Mac 2011 (см. [руководство по развертыванию Communicator for mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Эти клиенты не поддерживаются в Skype для бизнеса Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Требования к инфраструктуре для Skype для бизнеса на Mac
<a name="Infrastructure"> </a>

Клиент Skype для бизнеса на Mac использует как единую платформу управления связями (УКМП), так и веб-API объединенных коммуникаций (UCWA), который использует наши мобильные клиенты.
  
Клиент имеет те же требования, что и наши мобильные клиенты в том, что в поддерживаемой конфигурации должен быть развернут пограничный сервер доступа и обратный прокси-сервер. 
  
### <a name="authentication"></a>Проверка подлинности

Клиент Skype для бизнеса на Mac поддерживает проверку подлинности на основе сертификатов, современная проверка подлинности Майкрософт и многофакторную проверку подлинности при развертывании и включении.
  
> [!NOTE]
> В связи с текущим ограничением учетные данные пользователя Exchange должны совпадать с учетными данными Skype для бизнеса. 
  
### <a name="certificates"></a>Сертификаты

Сертификаты, используемые на пограничном сервере доступа, обратном прокси-сервере и серверах переднего плана, не должны использовать хэш-алгоритм SHA-512.
  
Список отзыва сертификатов HTTP должен быть определен и доступен клиенту. Например, запись LDAP в сертификате не поддерживается в качестве списка отзыва сертификатов.
  
### <a name="dns"></a>DNS

Для правильной работы Skype для бизнеса на клиенте Mac требуется правильное развертывание мобильности. Типичный сценарий сбоя состоит в том, что обе записи DNS разрешимы во внутренней сети:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Для получения дополнительных сведений обратитесь к разделу: [развертывание мобильной работы в Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)и [руководство по мобильному серверу Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>См. также
<a name="Infrastructure"> </a>

[Требования к DNS для Skype для бизнеса Server](../../plan-your-deployment/network-requirements/dns.md)

[Вопросы и ответы](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Известные проблемы](https://go.microsoft.com/fwlink/p/?LinkId=798228)

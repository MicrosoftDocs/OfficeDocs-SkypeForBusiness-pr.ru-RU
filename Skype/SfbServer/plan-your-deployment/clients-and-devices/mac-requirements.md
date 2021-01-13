---
title: Требования к клиенту Skype для бизнеса на Mac
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
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: В этом разделе вы узнаете о требованиях к оборудованию, программному обеспечению и инфраструктуре для запуска Skype для бизнеса на компьютере Mac.
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832169"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Требования к клиенту Skype для бизнеса на Mac
 
В этом разделе вы узнаете о требованиях к оборудованию, программному обеспечению и инфраструктуре для запуска Skype для бизнеса на компьютере Mac.
  
Клиент [Skype для бизнеса на Mac доступен](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) для скачивания.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Требования к оборудованию и программному обеспечению для Skype для бизнеса на Mac

Для клиента Skype для бизнеса на Mac требуется Mac OS X El И более высокий уровень и используется не менее 100 МБ дискового пространства. Мы поддерживаем использование всех встроенных аудио- и видео устройств. Внешние устройства должны быть в каталоге [решений Skype для бизнеса.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Этот список является предварительным, и некоторые устройства могут иметь право на Lync, но не поддерживаются в Skype для бизнеса на Mac. Обратитесь к [системным требованиям к](https://products.office.com/office-system-requirements) минимальному требуемом оборудованию.
  
### <a name="legacy-mac-clients"></a>Устаревшие клиенты Mac

Skype для бизнеса Server 2015 также поддерживает следующие устаревшие клиенты на компьютерах под управлением операционной системы Mac OS 10.5.8 или последнего пакета обновления или выпуска (на основе Intel) (операционная система Mac OS 10.9 в настоящее время не поддерживается). For details about supported features, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync для Mac 2011 (см. руководство по развертыванию [Lync для Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268786)
    
- Microsoft Communicator для Mac 2011 (см. Communicator руководство по [развертыванию для Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268787)
 
Эти клиенты не поддерживаются Skype для бизнеса Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Требования к инфраструктуре для Skype для бизнеса на Mac
<a name="Infrastructure"> </a>

Клиент Skype для бизнеса на Mac использует как платформу управления объединенными коммуникациями (UCMP), так и веб-API объединенных коммуникаций (UCWA), которые используют наши мобильные клиенты.
  
Клиент предъявляет те же требования, что и наши мобильные клиенты, так как в поддерживаемой конфигурации должны быть развернуты сервер доступа и обратный прокси-сервер. 
  
### <a name="authentication"></a>Проверка подлинности

Клиент Skype для бизнеса на Mac поддерживает проверку подлинности на основе сертификатов, современную проверку подлинности Майкрософт и многофакторную проверку подлинности при развертывании и включаемой.
  
> [!NOTE]
> Из-за текущего ограничения учетные данные пользователя Exchange должны быть одинаковыми с учетными данными Skype для бизнеса. 
  
### <a name="certificates"></a>Сертификаты

Сертификаты, которые используются на серверах доступа, обратном прокси-сервере и сервере переднего сервера, не должны использовать алгоритм hash SHA-512.
  
Клиент должен определить и получить доступ к списку отзыва сертификатов HTTP. Например, мы не поддерживаем запись LDAP в сертификате в качестве списка отзыва сертификатов.
  
### <a name="dns"></a>DNS

Для правильной работы клиента Skype для бизнеса на Mac необходимо правильно развернуть мобильность. Распространенный сценарий сбоя — разрешить во внутренней сети обе следующие записи DNS:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Дополнительные сведения: [развертывание мобильности в Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)и руководство [по microsoft Lync Server 2010 Mobility Guide.](https://go.microsoft.com/fwlink//p/?LinkId=798226)
  
## <a name="see-also"></a>См. также
<a name="Infrastructure"> </a>

[Требования К DNS для Skype для бизнеса Server](../../plan-your-deployment/network-requirements/dns.md)

[Вопросы и ответы](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Известные проблемы](https://go.microsoft.com/fwlink/p/?LinkId=798228)

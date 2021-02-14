---
title: Классы и описания схемы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: В этом разделе описываются все классы схемы, используемые Skype для бизнеса Server.
ms.openlocfilehash: 6c4b5d12baf85a1e9f168940fc889f6f18063616
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813559"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Классы и описания схемы в Skype для бизнеса Server
 
В этом разделе описываются все классы схемы, используемые Skype для бизнеса Server. 
  
## <a name="schema-classes-and-descriptions"></a>Классы схемы и описания

|**Класс**|**Описание**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Получатель электронной почты единой системы обмена сообщениями Exchange.  <br/> |Этот вспомогательный класс совместно с exchange UM.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Этот класс является контейнером для нескольких контактов приложения и не содержит никакие атрибуты.  <br/> |Новые возможности Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Этот класс размещает запись точки управления службой для экземпляра служб Unified Communications Application Services (UCAS).  <br/> |Новые возможности Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Этот класс обеспечивает связь определенного пула со службой приложений.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Этот вспомогательный класс для msRTCSIP-ApplicationServer содержит атрибуты, представляющие параметры для экземпляров службы приложений.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (устаревший)  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к архивации.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (устаревший)  <br/> |Этот класс представляет один сервер архивации обмена мгновенными сообщениями. Экземпляр этого класса создается при активации компьютера в качестве сервера архивации обмена мгновенными сообщениями, например, компьютера с установленной службой архивации обмена мгновенными сообщениями.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит никакие атрибуты.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Этот класс содержит атрибуты, представляющие параметры для конкретного каталога конференций.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Универсальная точка управления службой (SCP) для указания компьютера в качестве сервера под управлением Skype для бизнеса Server.  <br/> |Новые возможности в Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Этот вспомогательный класс содержит параметры для банка Skype для бизнеса Web App.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Этот класс содержит атрибуты, задающие настроенные домены регистратора SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Этот контейнер класса представляет одну побра бытовую службу доступа. Так как по периметру служба доступа развернута в сети периметра, и клиенты обычно не позволяют доменным службам Active Directory получать доступ из сети периметра, экземпляры службы по периметру доступа не присоединяются к сети Active Directory интрасети. Следовательно, прокси-серверы доступа не регистрируются в AD DS автоматически. Администратор должен вручную настроить существование каждого экземпляра службы access Edge в AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Этот дополнительный к msRTCSIP-MCU класс содержит атрибуты, представляющие параметры для серверов конференций.  <br/> |Новые возможности Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Этот дополнительный к msRTCSIP-MediationServer класс содержит атрибуты, представляющие параметры для серверов-посредников.  <br/> |Новые возможности Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Этот дополнительный к msRTCSIP-Server класс содержит атрибуты, представляющие параметры для серверов SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к федерации.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Этот класс содержит все параметры, которые применяются в развертывании Skype для бизнеса Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (устаревший)  <br/> |Этот класс представляет одну политику собраний Office Communications Server.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Локальный объект параметров глобальной топологии.  <br/> |Новые возможности в Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Контейнер для хранения объектов параметров глобальной топологии.  <br/> |Новые возможности в Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Этот класс является контейнером, представляющим экземпляр правила нормализации местонахождения.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Этот класс создается приложением помощника по конференц-связи и содержит атрибуты, используемые для классификации телефонных номеров конференций по регионам.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местонахождений и не содержит никакие атрибуты.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Этот класс является контейнером, представляющим конкретный профиль местонахождения.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (устаревший)  <br/> |Этот класс является контейнером для нескольких профилей местонахождений и не содержит какие-либо атрибуты.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (устаревший)  <br/> |Этот класс является контейнером для нескольких локальных правил нормализации и не содержит какие-либо атрибуты.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Этот класс представляет один сервер конференций.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Этот класс размещает несколько классов msRTCSIP-MCUFactory и не содержит какие-либо атрибуты.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа среды передачи. Экземпляр этого класса создается, когда активируется первый сервер конференций для этого конкретного типа.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Этот класс предоставляет связь конкретного пула с его фабрикой серверов конференций.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |В этом классе содержится запись точки управления службой для сервера-посредника.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (устаревший)  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие настраиваемые параметры собрания.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Контейнер, хранящий глобальные параметры мобильности.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Этот класс содержит атрибуты, которые представляют параметры для одного сервера мониторинга.  <br/> |Новые возможности Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (устаревший)  <br/> |Этот класс является контейнером, представляющим экземпляр наименее затратного маршрута к шлюзу или ряду шлюзов. Данная информация используется всеми пулами или серверами Enterprise, на которых установлен выпуск Standard Edition, для маршрутизации исходящих вызовов в телефонную сеть общего пользования (ТСОП) по принципу наименьшей стоимости.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (устаревший)  <br/> |Этот класс является контейнером для нескольких наименее затратных маршрутов и не содержит какие-либо атрибуты.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-Policies (устаревший)  <br/> |Этот класс содержит несколько классов политики Lync Server и не имеет никаких атрибутов.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Этот класс представляет один пул Skype для бизнеса Server.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Этот класс содержит несколько пулов Skype для бизнеса Server и не имеет никаких атрибутов.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Этот класс представляет точку управления службой пула. Атрибут msRTCSIP-PrimaryHomeServer пользователей, размещенных в пуле, указывает на экземпляр данного класса.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Контейнер, хранящий глобальные параметры присутствия.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие пользовательские параметры, которые поддерживаются серверами регистратора SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (устаревший)  <br/> |Этот класс является контейнером, представляющим экземпляр использования телефонных маршрутов. Класс использований телефонных маршрутов состоит из поля атрибута и поля описания. Поле атрибута определяет тип использования. В поле описания администраторы могут ввести описание использования для этого атрибута в телефонном маршруте.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (устаревший)  <br/> |Этот класс содержит несколько экземпляров класса msRTCSIP-RouteUsage и не имеет никаких атрибутов.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, которые ограничивают область результатов поиска и управляют ею.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Этот класс представляет один сервер со Skype для бизнеса Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Этот класс содержит контейнер глобальных параметров и объекты класса msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера конференций.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedMCU и не имеет никаких атрибутов.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Этот класс содержит несколько экземпляров классов msRTCSIP-TrustedProxy и не имеет никаких атрибутов.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Этот класс является контейнером, представляющим сервер, на котором работает прокси-сервер. Экземпляр данного класса создается при активации нового прокси-сервера на компьютере, подключенном к AD DS.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Этот класс является контейнером, представляющим доверенную службу, которая маршрутизируется с помощью адреса GRUU. Экземпляр этого класса создается при активации нового сервера, которому доверяет Skype для бизнеса Server. Этот доверенный сервер должен быть подключен к домену Active Directory.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Этот класс является контейнером для нескольких серверов GRUU и не содержит никакие атрибуты.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Этот класс содержит атрибуты, которые представляют параметры для доверенного веб-компонента.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedWebComponentServer и не имеет никаких атрибутов.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (устаревший)  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, относящиеся к объединенным коммуникациям.  <br/> |Устаревшее в Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Этот класс содержит точку управления службой для сервера IIS. Он определяет сервер как сервер веб-компонентов.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Этот класс предоставляет связь конкретного пула с веб-компонентом, который будет использовать этот пул.  <br/> |Новые возможности Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Этот дополнительный к msRTCSIP-WebComponents класс содержит атрибуты, представляющие параметры для веб-компонентов.  <br/> |Новые возможности Communications Server 2007.  <br/> |
   


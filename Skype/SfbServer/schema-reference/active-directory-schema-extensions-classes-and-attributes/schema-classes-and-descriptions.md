---
title: Классы и описания схемы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: В этом разделе описываются все классы схемы, используемые Skype для бизнеса Server.
ms.openlocfilehash: d7f05cd76074740e49f3972c97875e8993dd7b06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743265"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Классы и описания схемы в Skype для бизнеса Server
 
В этом разделе описываются все классы схемы, используемые Skype для бизнеса Server. 
  
## <a name="schema-classes-and-descriptions"></a>Классы схемы и описания

|**Класс**|**Описание**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange Получатель электронной почты Единой системы обмена сообщениями (ЕДИНОЙ СИСТЕМЫ обмена сообщениями).  <br/> |Этот вспомогательный класс совместно с Exchange um.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Этот класс является контейнером для нескольких контактов приложения и не содержит никакие атрибуты.  <br/> |Новое в Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Этот класс размещает запись точки управления службой для экземпляра служб Unified Communications Application Services (UCAS).  <br/> |Новое в Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Этот класс предоставляет связь из определенного пула в свою службу приложений.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Этот вспомогательный класс для msRTCSIP-ApplicationServer содержит атрибуты, представляющие параметры для экземпляров службы приложений.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (устаревший)  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к архивации.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (устаревший)  <br/> |Этот класс представляет один сервер архивации обмена мгновенными сообщениями. Экземпляр этого класса создается при активации компьютера в качестве сервера архивации обмена мгновенными сообщениями, например, компьютера с установленной службой архивации обмена мгновенными сообщениями.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Этот класс является контейнером для нескольких экземпляров каталогов конференций и не содержит никакие атрибуты.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Этот класс содержит атрибуты, представляющие параметры для конкретного каталога конференций.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Общая точка управления службой (SCP), чтобы указать компьютер в качестве сервера, на Skype для бизнеса Server.  <br/> |Новое в Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Этот вспомогательный класс содержит параметры для Skype для бизнеса Web App банка.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Этот класс содержит атрибуты, задающие настроенные домены регистратора SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Этот контейнер класса представляет одну службу Access Edge. Так как служба Access Edge развернута в сети периметра, и клиенты обычно не позволяют службам домена Active Directory получить доступ из сети периметра, экземпляры службы Access Edge не присоединяются к сети Active Directory интрасети. Следовательно, прокси-серверы доступа не регистрируются в AD DS автоматически. Администратор должен вручную настроить существование каждого экземпляра службы Access Edge в AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Этот дополнительный к msRTCSIP-MCU класс содержит атрибуты, представляющие параметры для серверов конференций.  <br/> |Новое в Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Этот дополнительный к msRTCSIP-MediationServer класс содержит атрибуты, представляющие параметры для серверов-посредников.  <br/> |Новое в Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Этот дополнительный к msRTCSIP-Server класс содержит атрибуты, представляющие параметры для серверов SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит все параметры, относящиеся к федерации.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Этот класс содержит все параметры, которые применяются во Skype для бизнеса Server развертывания.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (устаревший)  <br/> |Этот класс представляет единую политику Office серверов связи.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Локальный объект параметров глобальной топологии.  <br/> |Новое в Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Контейнер для хранения объектов параметров глобальной топологии.  <br/> |Новое в Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Этот класс является контейнером, представляющим экземпляр правила нормализации местонахождения.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Этот класс создается с помощью приложение и содержит атрибуты, используемые для классификации номеров телефонов конференции по регионам.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Этот класс является контейнером для нескольких экземпляров сопоставлений контактов местонахождений и не содержит никакие атрибуты.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Этот класс является контейнером, представляющим конкретный профиль местонахождения.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (устаревший)  <br/> |Этот класс является контейнером для нескольких профилей местонахождений и не содержит какие-либо атрибуты.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (устаревший)  <br/> |Этот класс является контейнером для нескольких локальных правил нормализации и не содержит какие-либо атрибуты.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Этот класс представляет один сервер конференций.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Этот класс размещает несколько классов msRTCSIP-MCUFactory и не содержит какие-либо атрибуты.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Этот класс является контейнером, представляющим фабрику серверов конференций для одного типа среды передачи. Экземпляр этого класса создается, когда активируется первый сервер конференций для этого конкретного типа.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Этот класс предоставляет связь конкретного пула с его фабрикой серверов конференций.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |В этом классе содержится запись точки управления службой для сервера-посредника.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (устаревший)  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие настраиваемые параметры собрания.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Контейнер, хранящий глобальные параметры мобильности.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Этот класс содержит атрибуты, которые представляют параметры для одного сервера мониторинга.  <br/> |Новое в communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (устаревший)  <br/> |Этот класс является контейнером, представляющим экземпляр наименее затратного маршрута к шлюзу или ряду шлюзов. Данная информация используется всеми пулами или серверами Enterprise, на которых установлен выпуск Standard Edition, для маршрутизации исходящих вызовов в телефонную сеть общего пользования (ТСОП) по принципу наименьшей стоимости.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (устаревший)  <br/> |Этот класс является контейнером для нескольких наименее затратных маршрутов и не содержит какие-либо атрибуты.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-Policies (устаревший)  <br/> |Этот класс содержит несколько классов политики Lync Server и не имеет никаких атрибутов.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Этот класс представляет один Skype для бизнеса Server пул.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Этот класс содержит несколько Skype для бизнеса Server пулов и не имеет никаких атрибутов.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Этот класс представляет точку управления службой пула. Атрибут msRTCSIP-PrimaryHomeServer пользователей, размещенных в пуле, указывает на экземпляр данного класса.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Контейнер, хранящий глобальные параметры присутствия.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, представляющие пользовательские параметры, которые поддерживаются серверами регистратора SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (устаревший)  <br/> |Этот класс является контейнером, представляющим экземпляр использования телефонных маршрутов. Класс использований телефонных маршрутов состоит из поля атрибута и поля описания. Поле атрибута определяет тип использования. В поле описания администраторы могут ввести описание использования для этого атрибута в телефонном маршруте.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (устаревший)  <br/> |Этот класс содержит несколько экземпляров класса msRTCSIP-RouteUsage и не имеет никаких атрибутов.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, которые ограничивают область результатов поиска и управляют ею.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Этот класс представляет один сервер, работающий Skype для бизнеса Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Этот класс содержит контейнер глобальных параметров и объекты класса msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера конференций.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedMCU и не имеет никаких атрибутов.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Этот класс содержит несколько экземпляров классов msRTCSIP-TrustedProxy и не имеет никаких атрибутов.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Этот класс является контейнером, представляющим сервер, на котором работает прокси-сервер. Экземпляр данного класса создается при активации нового прокси-сервера на компьютере, подключенном к AD DS.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Этот класс содержит атрибуты, которые представляют параметры для доверенного сервера.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Этот класс является контейнером, представляющим доверенную службу, которая маршрутизируется с помощью адреса GRUU. Экземпляр этого класса создается при активации нового сервера, которому доверяют Skype для бизнеса Server. Этот доверенный сервер должен быть подключен к домену Active Directory.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Этот класс является контейнером для нескольких серверов GRUU и не содержит никакие атрибуты.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Этот класс содержит атрибуты, которые представляют параметры для доверенного веб-компонента.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Этот класс содержит несколько экземпляров класса msRTCSIP-TrustedWebComponentServer и не имеет никаких атрибутов.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (устаревший)  <br/> |Этот дополнительный к msRTCSIP-GlobalContainer класс содержит атрибуты, относящиеся к объединенным коммуникациям.  <br/> |Устаревший в Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Этот класс содержит точку управления службой для сервера IIS. Он определяет сервер как сервер веб-компонентов.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Этот класс предоставляет связь конкретного пула с веб-компонентом, который будет использовать этот пул.  <br/> |Новое в Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Этот дополнительный к msRTCSIP-WebComponents класс содержит атрибуты, представляющие параметры для веб-компонентов.  <br/> |Новое в Communications Server 2007.  <br/> |
   


---
title: Управление конфигурацией пограничного сервера в организации
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После развертывания одного или более серверов необходимо включить типы доступа внешних доменов или поставщиков, удаленный доступ пользователей и анонимный доступ пользователей к конференциям через серверы, которые будут поддерживаться в вашей организации.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817339"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>Управление конфигурацией пограничного сервера в организации

После развертывания одного или более серверов необходимо включить типы доступа внешних доменов или поставщиков, удаленный доступ пользователей и анонимный доступ пользователей к конференциям через серверы, которые будут поддерживаться в вашей организации.

Ниже перечислены типы доступа, которые можно настроить на странице **Настройка пограничного доступа**:

  - **Включить федерацию и подключение к общедоступным системам im**   В этом случае вы хотите поддерживать доступ пользователей к федератным доменам партнеров. Этот параметр применяется к федерации SIP, настроенной для глобальных областей сайта или пользователей на странице "Политика **внешнего** доступа". Для применения параметров федераций необходимо настроить поддержку федераций на обеих страницах.
    
    Существуют два параметра, которые являются необязательными настройками для обнаружения федеративных партнеров и для передачи контактам уведомлений об отказе от архивации (уведомление федеративным контактам о том, что в развертывании включена архивная архива и архивированы ли сведения о связи):
    
      - **Включить обнаружение доменов партнеров**   Выбор этого параметра позволяет автоматически обнаруживать домены, с которые можно вести федератерию. Skype для бизнеса Server использует записи системы доменных имен (DNS) для обнаружения доменов, не указанных в списке разрешенных доменов, автоматически оценивая входящий трафик от обнаруженных федераированных партнеров и ограничив или блокируя этот трафик на основе уровня доверия, объема трафика и параметров администратора. Если этот параметр не выбран, доступ будет разрешен только для федеративных пользователей из доменов, включенных в список разрешенных доменов. Независимо от выбора этого параметра можно указать отдельные домены, которые будут заблокированы или разрешены, включая ограничение доступа к конкретным серверам пограничной службы доступа в федеративном домене. Подробные сведения см. в [подстройке "Настройка поддержки разрешенных внешних доменов".](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)
    
      - **Отправка федеративным**   партнерам заявление об отказе от архива   При выборе этого параметра федеративным партнерам можно отправлять федеративным партнерам сообщение об отказе в архиве, которое сообщает им о записи сведений о связи. При архивировании внешних взаимодействий с доменами федеративных партнеров следует включить уведомление об архивации, чтобы предупредить партнеров о том, что их сообщения и сведения о взаимодействии с ними будут архивироваться в вашей среде. Дополнительные сведения об архивировании см. в подтипе ["Enable or disable sending an Archiving disclaimer to federated partner "Enable or disable sending an Archiving disclaimer to federated partner".](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - **Включить доступ удаленных пользователей**   Включении этого параметра необходимо, чтобы пользователи в вашей организации, которые находятся за пределами брандмауэра, такие как телекоммуникационные метры и пользователи, которые находятся в командировке, могли подключаться к Skype для бизнеса Server. Подробные сведения см. в [сведениях о включаемом или отключаемом доступе удаленных пользователей.](enable-or-disable-remote-user-access.md)

  - **Доступ анонимных пользователей к конференциям**   В этом случае внутренние пользователи должны приглашать внешних анонимных пользователей в конференции, которые они организовывают. Включение этого параметра только разрешает анонимным пользователям участвовать в конференциях.

> [!NOTE]  
> Кроме поддержки разрешения доступа внешних пользователей, прежде чем внешним пользователям станет доступен любой тип доступа, также нужно настроить политики управления. Дополнительные сведения о создании, настройке и применении политик доступа внешних пользователей см. в политике управления внешним [доступом для организации.](../external-access-policies/manage-external-access-policy-for-your-organization.md)

**Просмотр сведений о конфигурации edge доступа с помощью Windows PowerShell управления**

  - Сведения о конфигурации edge доступа можно просмотреть с помощью Windows PowerShell и с помощью Windows PowerShell **Get-CsAccessEdgeConfiguration.** Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell. 
    
    To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:
    
     `Get-CsAccessEdgeConfiguration`
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting


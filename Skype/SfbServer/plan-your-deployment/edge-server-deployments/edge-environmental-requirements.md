---
title: Требования к среде пограничных серверов для Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 'Сводка: Сведения о окружающей среды требования для пограничного сервера в Скайп для Business Server 2015.'
ms.openlocfilehash: fd3c7d6c5fe138878b0122ea5c1885ad6ef84171
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server-2015"></a>Требования к среде пограничных серверов для Skype для бизнеса Server 2015
 
**Сводка:** Узнайте о окружающей среды требования для пограничного сервера в Скайп для Business Server 2015.
  
Много планирование и подготовка должен происходят вне Скайп для самой среде Business Server 2015 пограничного сервера. В этой статье мы рассмотрим, что подготовительные действия должны быть выполнены в среде организации, согласно нашего списка ниже:
  
- [Планирование топологии](edge-environmental-requirements.md#TopoPlan)
    
- [Планирование DNS](edge-environmental-requirements.md#DNSPlan)
    
- [Планирование сертификации](edge-environmental-requirements.md#CertPlan)
    
- [Планирование порта и брандмауэра](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>Планирование топологии
<a name="TopoPlan"> </a>

Скайп для пограничного сервера Business Server 2015 топологий, могут использовать:
  
- общедоступные IP-адреса с поддержкой маршрутизации;
    
- частные IP-адреса, не поддерживающий маршрутизацию, если используется **симметричное** преобразование сетевых адресов (NAT).
    
> [!TIP]
> Пограничный сервер может быть настроена на использование один IP-адрес с отдельными порты для каждой службы, или его можно использовать различные IP-адреса для каждой службы, но использовать один и тот же порт по умолчанию (который по умолчанию будет TCP 443). У нас есть Дополнительные сведения в разделе Требования к IP-адрес, ниже. 
  
Если вы решите использовать частные IP-адреса без поддержки маршрутизации с NAT, обратите внимание на следующие требования.
  
- Необходимо использовать частные IP-адреса с поддержкой маршрутизации на **всех трех** внешних интерфейсах.
    
- Необходимо настроить **симметричное** преобразование сетевых адресов для входящего и исходящего трафика. Симметричное преобразование сетевых адресов — поддерживается только преобразование сетевых адресов можно использовать с Скайп Business Server 2015 пограничного сервера.
    
- Настройте NAT не изменение входящих адреса источника. A / V Edge службе необходимо иметь возможность принимать входящие адрес источника для поиска пути к мультимедиа оптимальной.
    
- Пограничных серверов необходимо иметь возможность для взаимодействия друг с другом от своих общедоступных A / V Edge IP-адресов. Трафик должен брандмауэра.
    
- Преобразование сетевых адресов могут получать **только для** использоваться для масштабированной консолидированной среды пограничных серверов, если использовать балансировку нагрузки DNS. Если вы используете (аппаратного балансировщика Нагрузки) Балансировка нагрузки на оборудование, необходимо использовать открыто маршрутизируемыми IP-адресов адреса **без** преобразование сетевых адресов.
    
Вам придется проблем нет доступа, веб-конференций и A / V Edge интерфейсы за маршрутизатором или брандмауэром, для выполнения симметричное преобразование сетевых адресов для одного и масштабируемого консолидированного топологии пограничный сервер (при условии, что вы не используете аппаратная Балансировка нагрузки).
  
### <a name="summary-of-edge-server-topology-options"></a>Сводка вариантов топологии пограничных серверов

У нас есть несколько топологии параметры, предусмотренные для Скайп для развертываний Business Server 2015 пограничного сервера:
  
- Единая консолидированная пограничная топология с закрытыми IP-адресами и преобразованием сетевых адресов
    
- Единая консолидированная пограничная топология с общедоступными IP-адресами
    
- Масштабируемая консолидированная пограничная топология с закрытыми IP-адресами и преобразованием сетевых адресов
    
- Масштабируемая консолидированная пограничная топология с общедоступными IP-адресами
    
- Масштабируемая консолидированная пограничная топология с аппаратными средствами балансировки нагрузки
    
Выбрать подходящий вариант с помощью таблицы со сводкой вариантов для каждой топологии:
  
|**Топология**|**Высокая доступность**|**Дополнительные записи DNS, необходимые для внешних пограничных серверов в пограничном пуле?**|**Отработка отказа пограничных для Скайп для сеансов Business Server**|**Отработка отказа пограничных для Скайп для сеансов сервера федерации**|
|:-----|:-----|:-----|:-----|:-----|
|Единая консолидированная пограничная топология с закрытыми IP-адресами и преобразованием сетевых адресов  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Единая консолидированная пограничная топология с общедоступными IP-адресами  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Масштабируемая консолидированная пограничная топология с закрытыми IP-адресами и преобразованием сетевых адресов (с балансировкой нагрузки DNS)  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да & sup1;  <br/> |
|Масштабируемая консолидированная пограничная топология с общедоступными IP-адресами (с балансировкой нагрузки DNS)  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да & sup1;  <br/> |
|Масштабируемая консолидированная пограничная топология с аппаратными средствами балансировки нагрузки  <br/> |Да  <br/> |Нет (одна запись A DNS на каждый виртуальный IP-адрес)  <br/> |Да  <br/> |Да  <br/> |
   
& sup1; Отработка отказа удаленных пользователей Exchange единой системе обмена СООБЩЕНИЯМИ с помощью Балансировка нагрузки на DNS требуется Exchange 2013 или более поздней версии.
  
### <a name="ip-address-requirements"></a>Требования к IP-адресам

На уровне фундаментальные три службы должны IP-адресов; Доступ к служба пограничного сервера, служба пограничного сервера конференц-связи Web и A / V Edge службы. Можно использовать либо три IP-адреса (по одному для каждой политики), либо использовать один IP-адрес с возможностью размещения всех служб в разных портах (подробнее см. раздел [Планирование порта и брандмауэра](edge-environmental-requirements.md#PortFirewallPlan)). Вот и все, что нужно учесть при использовании единой консолидированной среды пограничного сервера.
  
> [!NOTE]
> Как указано выше, можно выбрать один IP-адрес для всех трех служб и запустить их на разных портах. Однако следует отметить, что такой подход не рекомендуется. Если ваши клиенты не смогут получить доступ к альтернативным портам, используемым в этом сценарии, они не смогут получить доступ ко всем возможностям среды пограничного сервера. 
  
Использование масштабируемых консолидированных топологий представляет собой более сложный процесс. Рассмотрим таблицы, иллюстрирующие требования к IP-адресам, не забывая о том, что основными факторами при выборе топологии являются высокая доступность и балансировка нагрузки. Требования к высокой доступности могут влиять на решение в отношении балансировки нагрузки (к этому вопросу мы вернемся после рассмотрения таблиц).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Требования к IP-адресам для масштабированной консолидированной среды пограничного сервера (отдельный IP-адрес для каждой роли)

|**Количество пограничных серверов в пуле**|**Балансировка нагрузки число IP-адресов для DNS**|**Число IP-адресов для балансировки нагрузки оборудования**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3 (по 1 на виртуальный IP-адрес) + 6  <br/> |
|3  <br/> |9  <br/> |3 (по 1 на виртуальный IP-адрес) + 9  <br/> |
|4  <br/> |12  <br/> |3 (по 1 на виртуальный IP-адрес) + 12  <br/> |
|5  <br/> |15  <br/> |3 (по 1 на виртуальный IP-адрес) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>Требования к IP-адресам для масштабированной консолидированной среды пограничного сервера (один IP-адрес для всех ролей)

|**Количество пограничных серверов в пуле**|**Балансировка нагрузки число IP-адресов для DNS**|**Число IP-адресов для балансировки нагрузки оборудования**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (по 1 на виртуальный IP-адрес) + 2  <br/> |
|3  <br/> |3  <br/> |1 (по 1 на виртуальный IP-адрес) + 3  <br/> |
|4  <br/> |4  <br/> |1 (по 1 на виртуальный IP-адрес) + 4  <br/> |
|5  <br/> |5  <br/> |1 (по 1 на виртуальный IP-адрес) + 5  <br/> |
   
Рассмотрим несколько вопросов, которые необходимо учесть при планировании.
  
- **Высокая доступность**: Если в вашем развертывании требуется высокий уровень доступности, следует развернуть по крайней мере два пограничных серверов в пуле. Очень важно отметить, что один пул пограничного сервера будут поддерживать до 12 пограничных серверов (хотя Topology Builder можно добавить до 20, не проверен или не поддерживается, поэтому мы рекомендуем не делать этого). Если вам требуется более 12 пограничных серверов, необходимо создать дополнительные пограничные пулы их.
    
- **Аппаратная Балансировка нагрузки**: рекомендуется для большинства вариантов Балансировка нагрузки DNS. Аппаратная Балансировка нагрузки также поддерживается, конечно, но особенно это необходимо для одного сценария через Балансировка нагрузки на DNS:
    
  - Внешний доступ к Exchange 2007 или Exchange 2010 (с не SP) единой системы обмена сообщениями (единой системы обмена СООБЩЕНИЯМИ).
    
- **Балансировка нагрузки на DNS**: для единой системы обмена СООБЩЕНИЯМИ Exchange 2010 SP1 и более новое являются могут поддерживаться балансировку нагрузки DNS. Обратите внимание, что если вам нужно перейти с DNS балансировку нагрузки для более ранней версии Exchange, он будет работать, но весь трафик для данного будут поступать на первый сервер в пуле, и если он недоступен, трафик, не будут выполнены.
    
    Балансировка нагрузки на DNS также рекомендуется в случае федерация с организациями, с помощью Lync Server 2010, Lync Server 2013 и Microsoft Office 365.
    
## <a name="dns-planning"></a>Планирование DNS
<a name="DNSPlan"> </a>

Когда речь идет о Скайп для развертывания пограничного сервера Business Server 2015, крайне важно для подготовки к DNS должным образом. С правом записями на месте развертывание будет более простым. Надеюсь выбора топологии в разделе выше, как мы будем выполнять обзор, а затем список две таблицы структуры DNS-записей для этих сценариев. У нас будет также некоторые [Дополнительные DNS пограничного сервера планирования для Скайп для Business Server 2015](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) для чтения, более глубокий, если это необходимо.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>DNS-записей для одного консолидированного пограничного сервера сценариев

Это будут DNS-записей, которые вы собираетесь требуются для на одном пограничном сервере с помощью любого из общего IP-адреса или частных IP-адреса с преобразование сетевых адресов. Так как это демонстрационных данных дается пример IP-адреса, чтобы упростить работу свои собственные записи:
  
- Внутренний сетевой адаптер: 172.25.33.10 (шлюз по умолчанию не назначен)
    
    > [!NOTE]
    > Убедитесь, что существует маршрут от сети, содержащей внутренний интерфейс пограничного сервера, и любыми сетями, содержащими серверы Скайп для клиентов Business Server 2015 и Lync Server 2013 (например, от 172.25.33.0 до 192.168.10.0). 
  
- Внешний сетевой адаптер:
    
  - Общедоступные IP-адреса:
    
  - Пограничный сервер доступа: 131.107.155.10 (основной шлюз по умолчанию задан в общедоступный маршрутизатор, например: 131.107.155.1)
    
  - Пограничный сервер конференций Web: 131.107.155.20 (дополнительный)
    
  - A / V Edge: 131.107.155.30 (дополнительный)
    
  Веб-конференций и A / V Edge общедоступный IP-адреса, Дополнительные (дополнительный) IP-адресов в разделе Дополнительно свойства протокола Интернета версии 4 (TCP/IPv4) и протокола Интернета версии 6 (TCP/IPv6) из свойств подключения локальной сети в Windows Server.
    
  - Закрытые IP-адреса:
    
  - Пограничный сервер доступа: 10.45.16.10 (основной шлюз по умолчанию задан маршрутизатор, например: 10.45.16.1)
    
  - Пограничный сервер конференций Web: 10.45.16.20 (дополнительный)
    
  - A / V Edge: 10.45.16.30 (дополнительный)
    
Веб-конференций и A / V Edge общедоступный IP-адреса, Дополнительные (дополнительный) IP-адресов в разделе Дополнительно свойства протокола Интернета версии 4 (TCP/IPv4) и протокола Интернета версии 6 (TCP/IPv6) из свойств подключения локальной сети в Windows Server.
  
> [!TIP]
>Возможны другие конфигурации:
  
- Можно использовать один IP-адрес для внешнего сетевого адаптера. Мы не рекомендуем так как затем вам потребуется для различения тебя служб с помощью различных портов (которые вы можете сделать в Скайп для Business Server), но существуют некоторые брандмауэры, может блокировать альтернативного порты. Дополнительные сведения см. в статье [Планирование порта и брандмауэра](edge-environmental-requirements.md#PortFirewallPlan).
    
- Можно назначить три внешних сетевых адаптера вместо одного и назначить один из IP-адресов службы каждому из них. Это разделит службы, если возникнут проблемы, то есть позволит упростить устранение неполадок и обеспечит бесперебойную работу служб несмотря на сбои.
    
|**Расположение**|**Тип**|**Порт**|**Полное доменное имя или DNS-запись**|**IP-адрес или полное доменное имя**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Внешняя DNS  <br/> |Запись  <br/> |NA  <br/> |sip.contoso.com  <br/> |**общедоступных:** 131.107.155.10 <br/> **закрытый:** 10.45.16.10 <br/> |Внешний интерфейс пограничного сервера доступа службы. Один для каждого домена SIP с Скайп необходимо для коммерческих пользователей.  <br/> |
|Внешняя DNS  <br/> |Запись  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**общедоступных:** 131.107.155.20 <br/> **закрытый:** 10.45.16.20 <br/> |Внешний интерфейс для службы Web пограничный сервер конференций.  <br/> |
|Внешняя DNS  <br/> |Запись  <br/> |NA  <br/> |AV.contoso.com  <br/> |**общедоступных:** 131.107.155.30 <br/> **закрытый:** 10.45.16.30 <br/> |Внешний интерфейс для вашей A / V Edge службы.  <br/> |
|Внешняя DNS  <br/> |SRV-запись  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |SIP.contoso.com  <br/> |Внешний интерфейс пограничного сервера доступа службы. Эта запись SRV необходима для Скайп для клиентов Business Server 2015, Lync Server 2013 и Lync Server 2010 для работы извне. Один для каждого домена с Скайп необходимо для коммерческих пользователей.  <br/> |
|Внешняя DNS  <br/> |SRV-запись  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |Внешний интерфейс пограничного сервера доступа службы. Эта запись SRV необходима для автоматического обнаружения DNS федеративных партнеров, вызов SIP-разрешенных доменов. Один для каждого домена с Скайп необходимо для коммерческих пользователей.  <br/> |
|Внутренняя DNS  <br/> |Запись  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |Внутренний интерфейс для консолидированной среды пограничного сервера.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>DNS records for Scaled DNS and hardware Edge Server scenarios

These will be the DNS records you're going to need for a singe Edge Server using either public IPs or private IPs with NAT. Because this is sample data, we'll give example IPs so you can work out your own entries more easily:
  
- Внутренний сетевой адаптер:
    
  - Узел 1: 172.25.33.10 (шлюз по умолчанию не назначен)
    
  - Узел 2: 172.25.33.11 (шлюз по умолчанию не назначен)
    
    > [!NOTE]
    > Убедитесь, что существует маршрут от сети, содержащей внутренний интерфейс пограничного сервера, и любыми сетями, содержащими серверы Скайп для клиентов Business Server 2015 и Lync Server 2013 (например, от 172.25.33.0 до 192.168.10.0). 
  
- Внешний сетевой адаптер:
    
  - Узел 1
    
     - Общедоступные IP-адреса:
    
        - Пограничный сервер доступа: 131.107.155.10 (основной шлюз по умолчанию задан в общедоступный маршрутизатор, например: 131.107.155.1)
    
        - Пограничный сервер конференций Web: 131.107.155.20 (дополнительный)
    
        - A/V Edge: 131.107.155.30 (secondary)
    
          Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
    - Закрытые IP-адреса:
    
         - Access Edge: 10.45.16.10 (this is the primary, with default gateway set to your router, ex: 10.45.16.1)
    
         - Web Conferencing Edge: 10.45.16.20 (secondary)
    
         - A/V Edge: 10.45.16.30 (secondary)
    
      Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
  - Узел 2
    
     - Общедоступные IP-адреса:
    
       - Access Edge: 131.107.155.11 (this is the primary, with default gateway set to your public router, ex: 131.107.155.1)
    
       - Web Conferencing Edge: 131.107.155.21 (secondary)
    
       - A/V Edge: 131.107.155.31 (secondary)
    
      Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
  - Закрытые IP-адреса:
    
      - Access Edge: 10.45.16.11 (this is the primary, with default gateway set to your router, ex: 10.45.16.1)
    
      - Web Conferencing Edge: 10.45.16.21 (secondary)
    
      - A/V Edge: 10.45.16.31 (secondary)
    
      Web conferencing and A/V Edge public IP addresses are additional (secondary) IP addresses in the Advanced section of the properties of Internet Protocol Version 4 (TCP/IPv4) and Internet Protocol Version 6 (TCP/IPv6) of the Local Area Connection Properties in Windows Server.
    
Возможны другие конфигурации:
  
- Можно использовать один IP-адрес для внешнего сетевого адаптера. We don't recommend this because then you're going to need to differentiate between the thee services using different ports (which you can do in Skype for Business Server) but there are some firewalls that may block the alternate ports. Дополнительные сведения см. в статье [Планирование порта и брандмауэра](edge-environmental-requirements.md#PortFirewallPlan).
    
- Можно назначить три внешних сетевых адаптера вместо одного и назначить один из IP-адресов службы каждому из них. Это разделит службы, если возникнут проблемы, то есть позволит упростить устранение неполадок и обеспечит бесперебойную работу служб несмотря на сбои.
    
|**Расположение**|**Type**|**Порт**|**FQDN or DNS record**|**IP address or FQDN**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Внешняя DNS  <br/> |Запись  <br/> |NA  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 and 131.107.155.11 <br/> **private:** 10.45.16.10 and 10.45.16.11 <br/> |An external interface for your Access Edge service. You'll need one for every SIP domain with Skype for Business users.  <br/> |
|Внешняя DNS  <br/> |Запись  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 and 131.107.155.21 <br/> **private:** 10.45.16.20 and 10.45.16.21 <br/> |An external interface for your Web Conferencing Edge service.  <br/> |
|Внешняя DNS  <br/> |Запись  <br/> |NA  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 and 131.107.155.31 <br/> **private:** 10.45.16.30 and 10.45.16.31 <br/> |An external interface for your A/V Edge service.  <br/> |
|Внешняя DNS  <br/> |SRV-запись  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |An external interface for your Access Edge service. This SRV record is required for Skype for Business Server 2015, Lync Server 2013, and Lync Server 2010 clients to work externally. You'll need one for every domain with Skype for Business.  <br/> |
|Внешняя DNS  <br/> |SRV-запись  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |An external interface for your Access Edge service. This SRV record is required for automatic DNS discovery of federated partners called Allowed SIP domains. You'll need one for every domain with Skype for Business.  <br/> |
|Внутренняя DNS  <br/> |Запись  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 и 172.25.33.11  <br/> |Внутренний интерфейс для консолидированной среды пограничного сервера.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>DNS-запись для федерации (все сценарии)

|**Расположение**|**Type**|**Порт**|**FQDN**|**FQDN host record**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Внешняя DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |The SIP Access Edge external interface required for automatic DNS discovery. Used by your other potential federation partners. It's also known as "Allow SIP domains." You'll need one of these for each SIP domain with Skype for Business users.  <br/><br/> **Note:** You will need this SRV record for mobility and the push notification clearing house. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>DNS-записи для протокола Extensible Messaging and Presence Protocol

|**Расположение**|**Type**|**Порт**|**FQDN**|**IP address or FQDN host record**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Внешняя DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |The XMPP proxy interface on your Access Edge service or Edge pool. You need to repeat this as needed for all internal SIP domains with Skype for Business enabled users, where contact with XMPP contacts is allowed through:  <br/> • a global policy  <br/> • a site policy where the user's enabled  <br/> • a user policy applied to the Skype for Business enabled user  <br/> Необходимо также сконфигурировать разрешенную политику XMPP в политике федеративных партнеров XMPP.  <br/> |
|Внешняя DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |IP address of the Access Edge service on the Edge Server or Edge pool hosting your XMPP Proxy service  <br/> |This points to the Access Edge service on the Edge Server or Edge pool that hosts the XMPP Proxy service. Typically the SRV record that you create will point to this host (A or AAAA) record.  <br/> |
   
## <a name="certificate-planning"></a>Планирование сертификации
<a name="CertPlan"> </a>

Skype for Business Server 2015 uses certificates for secure, encrypted communications both between servers and from server to client. Как и можно было ожидать, для сертификатов понадобятся DNS-записи, чтобы серверы подходили любому имени субъекта (SN) и альтернативному имени субъекта (SAN) в сертификатах. Это требует принятия определенных мер на стадии планирования, для регистрации подходящих полных доменных имен в DNS для записей SN и SAN ваших сертификатов.
  
Мы рассмотрим требования к внешним и внутренним сертификатам по отдельности, а затем ознакомимся с таблицей, в которой объединены и те, и другие требования.
  
### <a name="external-certificates"></a>Внешние сертификаты

At a minimum, the certificate assigned to your external Edge Server interfaces will need to be provided by a public Certificate Authority (CA). We can't recommend a specific CA to you, but we do have a list of CAs, [Unified Communications certificate partners](https://support.microsoft.com/en-us/kb/929395) that you can take a look at to see if your preferred CA is listed.
  
Когда и как отравлять запрос на получение общедоступного сертификата в центр сертификации? Есть несколько способов.
  
- You can go through the installation of Skype for Business Server, and then the Edge Server deployment. The Skype for Business Server Deployment Wizard will have a step to generate a certificate request, which you can then send to your chosen CA.
    
- You can also use Windows PowerShell commands to generate this request, if that's more inline with your business needs or deployment strategy.
    
- Finally, your CA may have their own submission process, which may also involve Windows PowerShell or another method. В этом случае вы должны будете обратиться к документации центра сертификации в дополнение к представленной здесь информации.
    
After you've gotten the certificate, you'll need to go ahead and assign it to these services in Skype for Business Server:
  
- Access Edge service interface
    
- Web Conferencing Edge service interface
    
- Audio/Video Authentication service (don't confuse this with the A/V Edge service, as that doesn't use a certificate to encrypt audio and video streams)
    
> [!IMPORTANT]
> Все пограничные серверы должны использовать один и тот же сертификат с одним и тем же закрытым ключом для службы проверки подлинности при ретрансляции мультимедиа. 
  
### <a name="internal-certificates"></a>Внутренние сертификаты

For the internal Edge Server interface, you can use a public certificate from a public CA, or a certificate issued from your organization's internal CA. The thing to remember about the internal certificate is that it uses an SN entry, and no SAN entries, so you don't have to worry about SAN on the internal cert at all.
  
### <a name="required-certificates-table"></a>Таблица "Обязательные сертификаты"

Приведенная здесь таблица поможет вам лучше ориентироваться в запросах. Записи полного доменного имени в этой таблице являются примерами доменов. Вам потребуется выполнять запросы на основе собственных закрытых доменов и публичных доменов. Мы использовали:
  
- contoso.com: общедоступное полное доменное имя
    
- fabrikam.com: дополнительное общедоступное полное доменное имя (добавлено для демонстрации запроса при наличии нескольких доменов SIP)
    
- Contoso.net: внутренний домен
    
#### <a name="edge-certificate-table"></a>Таблица "Сертификат пограничного сервера"

Regardless of whether you're doing a single Edge Server or an Edge pool, this is what you'll need for your certificate:
  
|**Компонент**|**Subject name (SN)**|**Subject alternative names (SAN)/order**|**Примечания**|
|:-----|:-----|:-----|:-----|
|Внешняя пограничная служба  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |Этот сертификат потребуется запросить в общедоступном ЦС и назначить его внешним интерфейсам пограничного сервера для следующих целей:<br/> • Access Edge  <br/> • Web Conferencing Edge  <br/> • Audio/Video Authentication  <br/> <br/>The good news is that SANs are automatically added to your certificate request, and therefore your certificate after you submit the request, based on what you defined for this deployment in Topology Builder. You'll only need to add SAN entries for any additional SIP domains or other entries you need to support. Why is sip.contoso.com replicated in this instance? That happens automatically as well, and it's needed for things to work properly.  <br/><br/> **Note:** This certificate can also be used for Public Instant Messaging connectivity. Эта процедура ничем не изменилась, но в предыдущих версиях этой документации она была  представлена в отдельной таблице. <br/> |
|Внутренняя пограничная служба  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |Этот сертификат можно получить в общедоступном или внутреннем центре сертификации. Сертификат должен содержать расширенное использование ключа (EKU), и его необходимо назначить внутреннему интерфейсу пограничного сервера.  <br/> |
   
Если для расширяемого протокола XMPP требуется сертификат, он будет идентичен приведенным выше записям таблицы внешнего пограничного сервера, но при этом будет содержать две дополнительные записи альтернативного имени субъекта:
  
- xmpp.contoso.com
    
- \*.contoso.com
    
Помните о том, что в настоящее время протокол XMPP поддерживается только для Google Talk. Чтобы использовать его для других целей, необходимо подтвердить использование сторонних функций.
  
## <a name="port-and-firewall-planning"></a>Планирование порта и брандмауэра
<a name="PortFirewallPlan"> </a>

Getting your planning right for ports and firewalls for Skype for Business Server Edge Server deployments can save you days or weeks of troubleshooting and stress. As a result, we're going to list a couple of tables that will indicate our protocol usage and what ports you need to have open, inbound and outbound, both for NAT and public IP scenarios. We'll also have separate tables for hardware load balanced scenarios (HLB) and some further guidance on that. For more reading from there, we also have [Technical diagrams for Skype for Business Server 2015](../../technical-diagrams.md), as well as some [Edge Server scenarios in Skype for Business Server 2015](scenarios.md) you can check out for your particular deployment concerns.
  
### <a name="general-protocol-usage"></a>Общие сведения об использовании протоколов

Прежде чем приступить к обсуждению сводных таблиц для внешних и внутренних брандмауэров, рассмотрим следующую таблицу:
  
|**Audio/Video transport**|**Usage**|
|:-----|:-----|
|UDP  <br/> |Предпочитаемый протокол транспортного уровня для аудио- и видеоданных.  <br/> |
|TCP  <br/> |Резервный протокол транспортного уровня для аудио- и видеоданных.  <br/> The required transport layer protocol for application sharing to Skype for Business Server 2015, Lync Server 2013, and Lync Server 2010.  <br/> The required transport layer protocol for file transfer to Skype for Business Server 2015, Lync Server 2013, and Lync Server 2010.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>Таблица сводки по брандмауэру внешних портов

Исходный IP-адрес и конечный IP-адрес будут содержать информацию для пользователей, использующих частные IP-адреса с NAT, а также для людей, использующих общедоступные IP-адреса. This will cover all the permutations in our [Edge Server scenarios in Skype for Business Server 2015](scenarios.md) section.
  
|**Role or protocol**|**TCP or UDP**|**Destination Port or port range**|**Source IP address**|**Destination IP address**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Любой  <br/> |XMPP Proxy service (shares an IP address with the Access Edge service  <br/> |The XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations.  <br/> |
|Доступ/HTTP  <br/> |TCP  <br/> |80  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Любой  <br/> |Отзыв сертификата и проверка и поиск CRL.  <br/> |
|Доступ/DNS  <br/> |TCP  <br/> |53  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Любой  <br/> |DNS-запрос по протоколу TCP.  <br/> |
|Доступ/DNS  <br/> |UDP  <br/> |53  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Любой  <br/> |DNS-запрос по протоколу UDP.  <br/> |
|Доступ/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Трафик SIP от клиента к серверу для доступа внешних пользователей.  <br/> |
|Доступ/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP.  <br/> |
|Доступ/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Любой  <br/> |Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP.  <br/> |
|Веб-конференции/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server Web Conferencing Edge service <br/> **Public IP:** Edge Server Web Conferencing Edge service service public IP address <br/> |Web conferencing media.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**Private IP using NAT:** Edge Server A/V Edge service service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |Любой  <br/> |Используется для ретрансляции трафика мультимедиа.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**Private IP using NAT:** Edge Server A/V Edge service service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |Любой  <br/> |Используется для ретрансляции трафика мультимедиа.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**Private IP using NAT:** Edge Server A/V Edge service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |Любой  <br/> |Исходящий порт 3478:   <br/> • Used by Skype for Business Server to determine the version of Edge Server it's communicating with.  <br/> • Used for media traffic between Edge Servers.  <br/> • Required for federation with Lync Server 2010.  <br/> • Needed if multiple Edge pools are deployed within your organization.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server A/V Edge service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |STUN/TURN – согласование кандидатов по протоколу UDP и порту 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server A/V Edge service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |STUN/TURN – согласование кандидатов по протоколу TCP и порту 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**Private IP using NAT:** Edge Server A/V Edge service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |Любой  <br/> |STUN/TURN – согласование кандидатов по протоколу TCP и порту 443.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>Таблица сводки по брандмауэру внутренних портов

|**Protocol**|**TCP or UDP**|**Порт**|**Source IP address**|**Destination IP address**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Любая среда, в которой работает служба шлюза XMPP:  <br/> • Front End Server  <br/> • Front End pool  <br/> |Edge Server internal interface  <br/> |Outbound XMPP traffic from your XMPP Gateway service running on your Front End Server or Front End pool.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Любая:  <br/> • Director  <br/> • Director pool  <br/> • Front End Server  <br/> • Front End pool  <br/> |Edge Server internal interface  <br/> |Outbound SIP traffic from your Director, Director pool, Front End Server or Front End pool to your Edge Server internal interface.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |Edge Server internal interface  <br/> |Любая:  <br/> • Director  <br/> • Director pool  <br/> • Front End Server  <br/> • Front End pool  <br/> |Inbound SIP traffic to your Director, Director pool, Front End Server, or Front End pool from your Edge Server internal interface.  <br/> |
|PSOM/MTLS/8057  <br/> |TCP  <br/> |8057  <br/> |Любая:  <br/> • Front End Server  <br/> • Each Front End Server  <br/>  in your Front End pool <br/> |Edge Server internal interface  <br/> |Web conferencing traffic from your Front End Server or each Front End Server (if you have a Front End pool) to your Edge Server internal interface.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Любая:  <br/> • Front End Server  <br/> • Front End pool  <br/> • Any Survivable Branch Appliance using this Edge Server  <br/> • Any Survivable Branch Server using this Edge Server  <br/> |Edge Server internal interface  <br/> |Authentication of A/V users from your Front End Server or Front End pool, or your Survivable Branch Appliance or Survivable Branch Server, using your Edge Server.  <br/> |
|UDP (STUN/MSTURN)  <br/> |UDP  <br/> |3478  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Preferred path for A/V media transfer between your internal and external users and your Survivable Branch Appliance or Survivable Branch Server.  <br/> |
|UDP (STUN/MSTURN)  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Fallback path for A/V media transfer between your internal and external users and your Survivable Branch Appliance or Survivable Branch Server, if UDP communication doesn't work. Для передачи файлов и общего доступа к рабочему столу используется TCP.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Любая:  <br/> • Front End Server that holds the Central Management store  <br/> • Front End pool that holds the Central Management store  <br/> |Edge Server internal interface  <br/> |Replication of changes from your Central Management store store to your Edge Server.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Centralized Logging Service controller using Skype for Business Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Centralized Logging Service controller using Skype for Business Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Centralized Logging Service controller using Skype for Business Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Аппаратные средства балансировки нагрузки для таблиц пограничных портов

Мы добавили раздел, посвященный аппаратным средствам балансировки нагрузки и пограничным портам, так как дополнительное оборудование — более сложная тема. Для получения рекомендаций по конкретным сценарием ознакомьтесь со следующими таблицами:
  
#### <a name="external-port-firewall-summary-table"></a>Таблица сводки по брандмауэру внешних портов

Исходный IP-адрес и конечный IP-адрес будут содержать информацию для пользователей, использующих частные IP-адреса с NAT, а также для людей, использующих общедоступные IP-адреса. This will cover all the permutations in our [Edge Server scenarios in Skype for Business Server 2015](scenarios.md) section.
  
|**Role or protocol**|**TCP or UDP**|**Destination Port or port range**|**Source IP address**|**Destination IP address**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Доступ/HTTP  <br/> |TCP  <br/> |80  <br/> |Edge Server Access Edge service public IP address  <br/> |Любой  <br/> |Отзыв сертификата и проверка и поиск CRL.  <br/> |
|Доступ/DNS  <br/> |TCP  <br/> |53  <br/> |Edge Server Access Edge service public IP address  <br/> |Любой  <br/> |DNS-запрос по протоколу TCP.  <br/> |
|Доступ/DNS  <br/> |UDP  <br/> |53  <br/> |Edge Server Access Edge service public IP address  <br/> |Любой  <br/> |DNS-запрос по протоколу UDP.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edge Server A/V Edge service IP address  <br/> |Любой  <br/> |Используется для ретрансляции трафика мультимедиа.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge Server A/V Edge service public IP address  <br/> |Любой  <br/> |Используется для ретрансляции трафика мультимедиа.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge Server A/V Edge service public IP address  <br/> |Любой  <br/> |Исходящий порт 3478:   <br/> • Used by Skype for Business Server to determine the version of Edge Server it's communicating with.  <br/> • Used for media traffic between Edge Servers.  <br/> • Required for federation.  <br/> • Needed if multiple Edge pools are deployed within your organization.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Любой  <br/> |Edge Server A/V Edge service public IP address  <br/> |STUN/TURN – согласование кандидатов по протоколу UDP и порту 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |Edge Server A/V Edge service public IP address  <br/> |STUN/TURN – согласование кандидатов по протоколу TCP и порту 443.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Edge Server A/V Edge service public IP address  <br/> |Любой  <br/> |STUN/TURN – согласование кандидатов по протоколу TCP и порту 443.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>Таблица сводки по брандмауэру внутренних портов

|**Protocol**|**TCP or UDP**|**Порт**|**Source IP address**|**Destination IP address**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |Любая среда, в которой работает служба шлюза XMPP:  <br/> • Front End Server  <br/> • Front End pool VIP address running the XMPP Gateway service  <br/> |Edge Server internal interface  <br/> |Outbound XMPP traffic from your XMPP Gateway service running on your Front End Server or Front End pool.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |Любая:  <br/> • Front End Server that holds the Central Management store  <br/> • Front End pool that holds the Central Management store  <br/> |Edge Server internal interface  <br/> |Replication of changes from your Central Management store to your Edge Server.  <br/> |
|PSOM/MTLS/8057  <br/> |TCP  <br/> |8057  <br/> |Любая:  <br/> • Front End Server  <br/> • Each Front End Server in your Front End pool  <br/> |Edge Server internal interface  <br/> |Web conferencing traffic from your Front End Server or each Front End Server (if you have a Front End pool) to your Edge Server internal interface.  <br/> |
|UDP (STUN/MSTURN)  <br/> |UDP  <br/> |3478  <br/> |Любая:  <br/> • Front End Server  <br/> • Each Front End Server in your Front End pool  <br/> |Edge Server internal interface  <br/> |Preferred path for A/V media transfer between your internal and external users and your Survivable Branch Appliance or Survivable Branch Server.  <br/> |
|UDP (STUN/MSTURN)  <br/> |TCP  <br/> |443  <br/> |Любая:  <br/> • Front End Server  <br/> • Each Front End Server in your pool  <br/> |Edge Server internal interface  <br/> |Fallback path for A/V media transfer between your internal and external users and your Survivable Branch Appliance or Survivable Branch Server, if UDP communication doesn't work. Для передачи файлов и общего доступа к рабочему столу используется TCP.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Centralized Logging Service controller using Skype for Business Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection.  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Centralized Logging Service controller using Skype for Business Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection.  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Centralized Logging Service controller using Skype for Business Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>Виртуальные IP-адреса внешнего интерфейса

|**Role or protocol**|**TCP or UDP**|**Destination Port or port range**|**Source IP address**|**Destination IP address**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> |TCP  <br/> |5269  <br/> |Любой  <br/> |XMPP Proxy service (shares an IP address with the Access Edge service)  <br/> |The XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations.  <br/> |
|XMPP  <br/> |TCP  <br/> |5269  <br/> |XMPP Proxy service (shares an IP address with the Access Edge service)  <br/> |Любой  <br/> |The XMPP Proxy service sends traffic from XMPP contacts in defined XMPP federations.  <br/> |
|Доступ/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Трафик SIP от клиента к серверу для доступа внешних пользователей.  <br/> |
|Доступ/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server Access Edge service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP.  <br/> |
|Доступ/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**Private IP using NAT:** Edge Server Access Edge service service <br/> **Public IP:** Edge Server Access Edge service public IP address <br/> |Любой  <br/> |Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP.  <br/> |
|Веб-конференции/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server Web Conferencing Edge service <br/> **Public IP:** Edge Server Web Conferencing Edge service public IP address <br/> |Web conferencing media.  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server A/V Edge service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |STUN/TURN – согласование кандидатов по протоколу UDP и порту 3478.  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |**Private IP using NAT:** Edge Server A/V Edge service <br/> **Public IP:** Edge Server A/V Edge service public IP address <br/> |STUN/TURN – согласование кандидатов по протоколу TCP и порту 443.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>Виртуальные IP-адреса внутреннего интерфейса

Приведенные здесь рекомендации немного отличаются. Фактически при использовании аппаратной балансировки нагрузки теперь рекомендуется использовать маршрутизацию через внутренний виртуальный IP-адрес только при следующих условиях:
  
- If you are using Exchange 2007 or Exchange 2010 Unified Messaging (UM).
    
- У вас есть устаревшие клиенты, использующие пограничный сервер.
    
The following table does give guidance for those scenarios, but otherwise, you should be able to depend on Central Management store (CMS) to route traffic to the individual Edge Server it's aware of (this does require that CMS is kept up to date on Edge Server information, of course).
  
|**Protocol**|**TCP or UDP**|**Порт**|**Source IP address**|**Destination IP address**|**Примечания**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Доступ/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Любая:  <br/> • Director  <br/> • Director pool VIP address  <br/> • Front End Server  <br/> • Front End pool VIP address  <br/> |Edge Server internal interface  <br/> |Outbound SIP traffic from your Director, Director pool VIP address, Front End Server, or Front End pool VIP address to your Edge Server internal interface.  <br/> |
|Доступ/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Edge Server internal VIP interface  <br/> |Любая:  <br/> • Director  <br/> • Director pool VIP address  <br/> • Front End Server  <br/> • Front End pool VIP address  <br/> |Inbound SIP traffic to your Director, Director pool VIP address, Front End Server, or Front End pool VIP address from your Edge Server internal interface.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |Любая:  <br/> • Front End Server IP address  <br/> • Front End pool IP address  <br/> • Any Survivable Branch Appliance using this Edge Server  <br/> • Any Survivable Branch Server using this Edge Server  <br/> |Edge Server internal interface  <br/> |Authentication of A/V users from your Front End Server or Front End pool, or your Survivable Branch Appliance or Survivable Branch Server, using your Edge Server.  <br/> |
|UDP (STUN/MSTURN)  <br/> |UDP  <br/> |3478  <br/> |Любой  <br/> |Edge Server internal interface  <br/> |Предпочитаемый путь передачи аудио/видео между внутренними и внешними пользователями.  <br/> |
|UDP (STUN/MSTURN)  <br/> |TCP  <br/> |443  <br/> |Любой  <br/> |Edge Server internal VIP interface  <br/> |Резервный путь для передачи аудио/видео между внутренними и внешними пользователями, устройством в случае, если подключение UDP не работает. Для передачи файлов и общего доступа к рабочему столу используется TCP.  <br/> |
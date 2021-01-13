---
title: Требования К DNS для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: Сводка. Просмотрите вопросы DNS, рассмотренные в этом разделе, перед внедрением Skype для бизнеса Server.
ms.openlocfilehash: 3db3641e5b884ef5bca43222fcf001bd4c5a538a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825279"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Требования К DNS для Skype для бизнеса Server

**Сводка:** Просмотрите вопросы DNS, рассмотренные в этом разделе, прежде чем внедрять Skype для бизнеса Server.

Эта статья посвящена только планированию DNS для развертывание Skype для бизнеса Server в локальной сети организации. For Skype for Business Online refer to "Office 365 URLs and IP address ranges" at [https://aka.ms/o365ips](https://aka.ms/o365ips) .

DNS-сервер сопоирует имена хостов (например, www. <span></span> contoso .com, предположительно веб-сервер) для IP-адресов <span></span> (например, 10.10.10.10). Это помогает клиентам и взаимозависимым серверам взаимодействовать друг с другом в сети. При выполнении реализации Skype для бизнеса Server 2015 необходимо убедиться, что сопоставление новых имен серверов (обычно отражающих роль, которую они будут использовать) соответствует IP-адресам, которые им назначены.

Хотя на первый взгляд это может показаться немного сложным, сложные задачи по планированию этого можно сделать с помощью средства планирования Skype для бизнеса [Server 2015.](https://www.microsoft.com/download/details.aspx?id=50357) После ответа на вопросы мастера о том, какие функции планируется использовать, для каждого определенного сайта можно просмотреть отчет DNS в отчете об администрировании по краям и использовать сведения, указанные в нем, для создания записей DNS. Вы также можете внести изменения во многие используемые имена и IP-адреса. Подробные сведения см. в отчете [по DNS.](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report) Помните, что вы можете экспортировать отчет об администрировании по краям в таблицу Excel, и отчет DNS будет одним из таблиц в файле. Хотя это средство включает функции, неподготовленные из Skype для бизнеса [Server 2019,](../../../SfBServer2019/deprecated.md)оно по-прежнему можно использовать для создания первоначального плана, если эти функции не выбраны

When you are installing a new implementation as described in [Create DNS records for Skype for Business Server](../../deploy/install/create-dns-records.md) and building your topology for Skype for Business Server, we recognize that you can choose to use the DNS capabilities built in to Windows Server 2016 or a third-party DNS package, so we'll keep the discussions in this article general rather than specific. We're detailing what's needed, and how you meet that need is your decision to make.

Опытные администраторы Skype для бизнеса, Lync и Office Communications Suite, вероятно, поймут следующие таблицы. Если таблица вас запутает, в последующих разделах или статьях будет немного пролиться свет на следующие понятия:

## <a name="summary-tables"></a>Сводные таблицы
<a name="BK_Summary"> </a>

В следующих таблицах фиксировать DNS-записи, которые Skype для бизнеса Server использует для предоставления услуг пользователям. Некоторые из них являются необязательными, так как они необходимы только для поддержки определенных функций, и их можно пропустить, если эти функции не нужны. Записи DNS, необходимые только для внутреннего доступа, находятся только в первой таблице, а развертыванию, разрешанию внутреннего и внешнего доступа, необходимы записи из обеих таблиц.

**Внутренние сопоставления DNS**

|Record Type|Value (Значение)|Разрешается в|Назначение|Обязательно|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN пула переднего входа  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |IP-адреса сервера пула переднего сервера  <br/>  DNS LB до *192.168.21.122 192.168.21.123 192.168.21.124*   |Балансировка нагрузки на DNS для пулов переднего входа. Сопоает имя пула переднего входа набору IP-адресов.  <br/> См. [развертывание балансировки нагрузки на DNS в пулах переднего входа и в пулах директоров](load-balancing.md#BK_FE_Dir)  |Да   |
|A/AAAA   | FQDN каждого сервера переднего сервера или сервера Standard Edition в пуле или отдельного сервера <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |Соответствующий IP-адрес каждого сервера  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Сопозовет имя сервера с ЕГО IP-адресом.   |Да   |
|A/AAAA   |Переопределения FQDN внутренних веб-служб корпоративного пула  <br/> *Web-int. <span></span> contoso <span></span> .com*   |VIP-сервер HLB для внутренних веб-служб сервера переднего сервера  <br/> *192.168.21.120*   |Требуется для того, чтобы включить веб-трафик между клиентами, например скачивание Skype для бизнеса Web App. Также требуется для мобильных клиентов.   |Да   |
|A/AAAA   |Переопределения FQDN внешних веб-служб корпоративного пула  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |VIP-сервер HLB для внешних веб-служб сервера переднего сервера  <br/>*68.123.56.90*   |Требуется для того, чтобы включить веб-трафик между клиентами, например скачивание Skype для бизнеса Web App. Обязательно, если мобильные клиенты будут разрешать DNS внутренним образом. Может разрешаться в IP-адрес обратного прокси-сервера DMZ или IP-адрес Интернета.   ||
|A/AAAA   | FQDN SQL тыловом сервере <br/> *SQL1. <span></span> contoso <span></span> .com*   |IP-адрес сервера  <br/> *192.168.11.90*   |Сопозовет имя сервера для серверной SQL, работая с пулом переднего сервера, с ЕГО IP-адресом   ||
|A/AAAA   |FQDN зеркального SQL тыловом сервере  <br/> *SQL2. <span></span> contoso <span></span> .com*   |IP-адрес сервера  <br/> *192.168.11.91*   |Сопозовет имя сервера для серверного зеркального SQL, работая с пулом переднего сервера, с ЕГО IP-адресом   ||
|A/AAAA   |FQDN пула директоров  <br/>**Примечание.** Не применимо при использовании автономных серверов директоров <br/> *DirPool. <span></span> contoso <span></span> .com*   |IP-адреса пула директоров  <br/> DNS LB до *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Балансировка нагрузки на DNS серверов пула директоров. Сопоирует имя пула директоров с IP-адресом. См. статью "Развертывание балансировки нагрузки на DNS в пулах переднего входа и [пулах директоров"](load-balancing.md#BK_FE_Dir) <br/> Директор может проверить подлинность пользователя и является необязательным.   ||
|A/AAAA   |FQDN директора   |IP-адрес каждого сервера директора   |Сопоирует имя пула директора с IP-адресом, см. статью "Развертывание балансировки нагрузки на DNS в пулах переднего входа и [пулах директоров"](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN пула серверов-посредников   |IP-адреса пула   |Роль сервера-посредника необязательна. Службы, предоставляемые сервером-посредником, можно совместно разместить на сервере переднего сервера или в пуле. См. [использование балансировки нагрузки на DNS в пулах серверов-посредников](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN сервера-посредника   |IP-адрес сервера;   |Службы, предоставляемые сервером-посредником, можно совместно разместить на сервере переднего сервера или в пуле. См. [использование балансировки нагрузки на DNS в пулах серверов-посредников](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN сервера сохраняемой беседы   |IP-адрес сервера сохраняемой беседы   |Сервер сохраняемой беседы необходим для функции сохраняемой беседы и в противном случае необязателен.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |IP-адрес пула переднего концев HLB или IP-адрес директора  <br/>  192.168.21.121  |Внутренняя служба автоdiscover1, необходимая для поддержки мобильности. Если для разрешения для мобильных устройств используется внутренняя служба DNS, она должна указать на внешний IP-адрес или IP-адрес DMZ.  <br/> Для веб-служб требуется HLB в пуле переднего входа, так как ПРОТОКОЛ HTTPS не может использовать DNS. Для пула переднего сервера или пула директоров это должно разрешаться в IP-адрес HLB или обычный IP-адрес для сервера Standard edition или сервера автономных директоров.   |Да   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |HLB FE Pool FQDN or Director FQDN  <br/> Web-int. <span></span> contoso <span></span> .com   |Внутренняя служба автооружия1 <br/> При желании его можно реализовать в качестве CNAME вместо записи A.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |IP-адреса сервера пула переднего сервера (или каждый IP-адрес Директора)  <br/>  DNS LB до *192.168.21.122 192.168.21.123 192.168.21.124*   |Необходимые для автоматической настройки см. в по [walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Запись или записи, указывающие на серверы пула переднего сервера или серверы директоров во внутренней сети или службу доступа, когда клиент является внешним   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |HLB FE Pool VIP Or Director Pool HLB VIP , or SE/Director Server IP  <br/>  192.168.21.121  |Развертывание этой записи является необязательным &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Порт 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Порт 5061  |FQDN пула переднего входа  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Включает автоматический вход внутренних пользователей 1 на интерфейсный сервер/пул или сервер SE/пул, который обеспечивает проверку подлинности и перенаправление клиентских запросов на вход.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |FQDN пула переднего входа  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Внутренний доступ пользователей &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Источник NTP, необходимый для устройств Lync Phone Edition   |Это необходимо для поддержки настольных телефонов.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN службы по краям доступа <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Создайте одну запись SRV для каждого домена SIP с клиентами IOS или Windows Phone Mobile.   |Поддержка мобильных клиентов   |
|A/AAAA   |URL-адрес администратора  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Панель управления Skype для бизнеса Server, [см. простые URL-адреса](dns.md#BK_Simple)  ||
|A/AAAA   |URL-адрес meet  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Собрания по сети, [см. простые URL-адреса](dns.md#BK_Simple)  ||
|A/AAAA   |URL-адрес для телефонного номера  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Conferencing dial-in, see [Simple URLs](dns.md#BK_Simple)  ||
|A/AAAA   |внутреннее FQDN веб-служб  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Веб-служба Skype для бизнеса, используемая Skype для бизнеса Web App   ||
|A/AAAA   |FQDN пула серверов Office Web Apps  <br/> OWA. <span></span> contoso <span></span> .com   | VIP-адрес пула серверов Office Web Apps <br/> 192.168.1.5   |Определяет FQDN пула серверов Office Web Apps   ||
|A/AAAA   | Внутреннее веб-FQDN <br/> Web-int. <span></span> contoso <span></span> .com   | IP-адрес пула переднего ip-адреса <br/> 192.168.21.121   |Определяет внутреннее веб-FQDN, используемую Skype для бизнеса Web App  <br/> Если в этом пуле используется балансировка нагрузки на DNS, то сервер переднего и внутреннего веб-серверов не могут иметь одинаковое FQDN.   ||

&#x2776; используется клиентом для обнаружения интерфейсного сервера или интерфейсного пула, а также для проверки подлинности и входа в качестве пользователя. Дополнительные подробности об этом можно сделать в по [walkthrough of Skype for Business clients locating services.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; это необходимо только для поддержки устаревших клиентов до Lync 2013 и настольных телефонов.

&#x2778; ситуации, когда устройство unified Communications включено, но пользователь никогда не вошел в систему, запись A позволяет устройству обнаружить сервер, на котором размещена веб-служба обновления устройств, и получить обновления. В противном случае устройство получает сведения о сервере посредством автоматической подготовки при первом входе пользователя.

На следующей схеме показан пример, который включает как внутренние, так и внешние DNS-записи, а также многие записи, показанные в следующих таблицах:

**Схема сети edge с использованием общедоступных IPv4-адресов**

![пример сетевой схемы DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Сопоставления DNS сети периметра (как внутренние, так и внешние интерфейсы)**

|Record Type|Value (Значение)|Разрешается в|Назначение|Обязательно|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |Внутреннее FQDN пула  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |IP-адреса внутреннего пула  <br/> 172.25.33.10, 172.25.33.11   |IP-адреса внутреннего интерфейса консолидированного пула   |Да   |
|A/AAAA   |FQDN сервера  <br/>*Минусы-1. <span></span> contoso <span></span> .com*  |IP-адрес внутреннего сервера для сервера в пуле edge  <br/> 172.25.33.10   |Создайте запись для каждого сервера в пуле с ИД FQDN сервера, указывав ip-адрес внутреннего узла сервера в пуле, см. под балансировку нагрузки [на DNS](load-balancing.md#BK_Edge)в пулах серверов.   |Да   |
|A/AAAA   |FQDN пула службы доступа  <br/>*Access1. <span></span> contoso <span></span> .com*  |Внешние IP-адреса пула службы доступа  <br/> 131.107.16.10, 131.107.16.11   |Пограничная служба доступа предоставляет единую доверенную точку подключения как для исходящего, так и для входящего трафика протокола SIP.   |Да   |
|A/AAAA   |FQDN пула службы веб-служб  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Внешние IP-адреса службы веб-службы  <br/> 131.107.16.90, 131.107.16.91   |Побереговая служба веб-службы позволяет внешним пользователям присоединяться к собраниям, которые находятся во внутренней среде Skype для бизнеса Server.   |Да   |
|A/AAAA   |*av.\<sip-domain\>* Полное доменное имя пула <br/>*AV1. <span></span> contoso <span></span> .com*  |Внешние IP-адреса A/V Edge  <br/> 131.107.16.170, 131.107.16.171   |По краям аудио- и видеосвязи внешние пользователи могут получить доступ к аудио- и видеофайлам, предоставлению общего доступа к приложениям и передаче файлов.   |Да   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN пула внешнего доступа  <br/>*Access1. <span></span> contoso <span></span> .com*  |Находит пул серверов. См. [по walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Да   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN внешнего доступа  <br/>_Access1. <span></span> contoso <span></span> .com_  |Используется для доступа внешних пользователей. См. [по walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Да   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN внешнего доступа  <br/>*Access1. <span></span> contoso <span></span> .com*  |Используется для федерации и подключения к общедоступным службе мгновенных услуг   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN внешнего доступа  <br/>*Access1. <span></span> contoso <span></span> .com*  |Прокси-служба XMPP принимает и отправляет сообщения XMPP настроенным федератным партнерам XMPP и от них.   |Y, чтобы развернуть федерацию, в противном случае необязательно  <br/> Отсутствует в Skype для бизнеса Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN внешнего доступа  <br/>*Access1. <span></span> contoso <span></span> .com*  |Для поддержки службы push-уведомлений и службы push-уведомлений Apple необходимо создать одну запись SRV для каждого домена SIP. &#x2778;  ||
|A/AAAA   |FQDN веб-служб внешнего пула переднего входа  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Общедоступный IP-адрес обратного прокси-сервера, прокси-сервер vip внешних веб-служб для пула переднего &#x2776; <br/> 131.107.155.1 proxy to 192.168.21.120   |Внешний интерфейс интерфейсного пула, используемый Skype для бизнеса Web App   |Да   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Общедоступный IP-адрес обратного прокси-сервера, разрешаемой в IP-адрес внешних веб-служб для пула директоров, если он есть, или для пула переднего &#x2777; <br/> 131.107.155.1 proxy to 192.168.21.120   | Внешняя запись для клиентского автообнаружия, также используемая мобильными приложениями, Skype для бизнеса Web App и веб-приложением планатора, разрешенная обратным прокси-сервером <br/> Для поддержки службы push-уведомлений и службы push-уведомлений Apple создается одна запись SRV для каждого домена SIP с клиентами Microsoft Lync Mobile. 3   |Да   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Общедоступный IP-адрес обратного прокси-сервера, разрешаемой во внешний веб-интерфейс для интерфейсного пула  <br/> 131.107.155.1 proxy to 192.168.21.120   |Прокси-сервер в веб-службу Skype для бизнеса  <br/> См. [простые URL-адреса](dns.md#BK_Simple)  |Да   |
|A/AAAA   |dial-in.*\<sipdomain\>* <br/> dial-in. *<span></span> contoso <span></span> .com*  |Общедоступный IP-адрес обратного прокси-сервера, прокси-сервер внешнего веб-интерфейса для интерфейсного пула  <br/> 131.107.155.1 proxy to 192.168.21.120   |Прокси-сервер в веб-службу Skype для бизнеса  <br/> См. [простые URL-адреса](dns.md#BK_Simple)  |Да   |
|A/AAAA   |FQDN пула серверов Office Web Apps  <br/> OWA. <span></span> contoso <span></span> .com   | Общедоступный IP-адрес обратного прокси-сервера, прокси-сервер для внешнего веб-интерфейса сервера Office Web Apps <br/> 131.107.155.1 proxy to 192.168.1.5   | VIP-адрес пула серверов Office Web Apps <br/> 192.168.1.5   |Определяет FQDN пула серверов Office Web Apps   |

&#x2776; требуется для развертывания федерации, в противном случае необязательный.

&#x2777; используется клиентом для обнаружения интерфейсного сервера или интерфейсного пула, а также для проверки подлинности и входа в качестве пользователя.

&#x2778; Это требование применяется только к клиентам на мобильных устройствах Apple или Майкрософт. Устройства Android и Nokia Symbian не используют push-уведомления.

 Дополнительные подробности о серверах и сетях периметра см. в содержимом планирования [DNS для этого](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) сервера.

> [!IMPORTANT]
> Skype для бизнеса Server поддерживает использование IPv6-адресов. Дополнительные сведения см. в сведениях о планировании [IPv6](ipv6.md) в Skype для бизнеса.

> [!IMPORTANT]
> Дополнительные подробности о FQDNs см. в [основах DNS.](basics.md)

**Разделенная DNS** 
 <a name="BK_split"></a>

Разделенная DNS — это конфигурация DNS, в которой две зоны DNS имеют одно пространство имен. Первая зона DNS обрабатывает внутренние запросы, а вторая зона DNS обрабатывает внешние запросы, как упоминалось в этих таблицах. Подробнее об этом см. в [разделенной DNS.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

## <a name="hybrid-considerations"></a>Гибридные аспекты
<a name="BK_Hybrid"> </a>

If you plan to have some users homed online and some homed on premises, refer to the Hybrid connectivity planning article [Skype for Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). You will need to configure DNS as normal for Skype for Business Server 2015 and also add additional DNS records.

Чтобы подтвердить, что ваши пользователи будут иметь доступ к нужным ресурсам, обратитесь к подсети "URL-адреса и диапазоны IP-адресов Office [https://aka.ms/o365ips](https://aka.ms/o365ips) 365".

## <a name="simple-urls"></a>Простые URL-адреса
<a name="BK_Simple"> </a>

URL-адрес — это ссылка на веб-ресурс, который указывает его расположение в сети компьютера и протокол, используемый для его извлечения.

Skype для бизнеса Server поддерживает использование трех "простых" URL-адресов для доступа к службам:

- **Meet** используется в качестве базового URL-адреса для всех конференций на сайте. Пример простого URL-адреса meet: https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. URL-адрес для конкретного собрания может быть https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com/_username_/7322994.

    С помощью простого URL-адреса meet ссылки на собрания легко переосмыслеть и легко общаться.

- **Dial-in** enables access to the Dial-in Conferencing Settings web page. На этой странице отображаются номера телефонных номеров конференций с доступными языками, назначенная информация о конференциях (т. е. для собраний, которые не требуются для запланированного) и элементы управления DTMF в конференции, а также поддерживается управление личным идентификационным номером (PIN-кодом) и назначенной информацией конференц-связи. Простой URL-адрес телефонного номера включен во все приглашения на собрания, чтобы пользователи, желающие дозвониться до собрания, могли получить доступ к необходимому номеру телефона и ПИН-коду. Примером простого URL-адреса для телефонного https:// <span></span> dialin. <span></span> contoso <span></span> .com.

- **Администратор** обеспечивает быстрый доступ к панели управления Skype для бизнеса Server. На любом компьютере в пределах брандмауэров организации администратор может открыть панель управления Skype для бизнеса Server, введя простой URL-адрес администратора в браузере. Этот URL-адрес используется внутри организации. Пример простого URL-адреса администратора — https:// <span></span> администратора. <span></span> contoso <span></span> .com.

Простые URL-адреса более подробно обсуждаются в требованиях DNS для простых URL-адресов [в Skype для бизнеса Server.](simple-urls.md)

## <a name="dns-by-server-role"></a>DNS по роли сервера
<a name="BK_Servers"> </a>

Вы можете настроить имена этих пулов и серверов по своему желанию, но сделать их запоминающимися и отражать их функции в системе.

### <a name="dns-records-for-individual-servers-or-pools"></a>Записи DNS для отдельных серверов или пулов

Эти общие требования к записям применяются к любой роли сервера, используемой Skype для бизнеса. Пул — это набор серверов, на которых запущены те же службы, которые работают вместе для обработки клиентских запросов, направляемого на них с помощью подстройки нагрузки. Подробные [сведения см. в](load-balancing.md) требованиях к балансировку нагрузки для Skype для бизнеса

**Требования к записям DNS для ролей сервера или пула (предполагается балансировка нагрузки на DNS)**

|Сценарий развертывания|Требование DNS|
|:-----|:-----|
|Один сервер:  <br/> Сохраняемая беседа, директор, сервер-посредник, сервер переднего сервера   |Внутренняя запись A, разрешающая полное доменное имя сервера в IP-адрес.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Пул:  <br/> Сохраняемая беседа, директор, сервер-посредник, сервер-посредник, сервер переднего сервера   |Внутренняя запись A, которая соединена с IP-адресом полного доменного имени каждого узла сервера в пуле.  <br/>**Пример** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Несколько внутренних записей A, которые соедиируют полное доменное имя пула с IP-адресами узлов сервера в пуле.  <br/>**Пример** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Разделы О DNS для конкретного сервера

 To plan edge server deployment, review [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md), and [Advanced Edge Server DNS planning for Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) which has the following sections

- [Аварийное восстановление DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Балансировка нагрузки на DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Автоматическая настройка без разделенной DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [Разделенная DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)



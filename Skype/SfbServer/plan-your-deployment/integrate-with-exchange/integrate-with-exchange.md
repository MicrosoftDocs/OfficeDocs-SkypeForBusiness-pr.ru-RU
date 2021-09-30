---
title: Планирование интеграции Skype для бизнеса и Exchange
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: Сводка. Просмотрите эту тему для получения сведений о том, как интегрировать Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013 г.
ms.openlocfilehash: f2650e8a18767e70ab98e8763e9ec2863e99df90
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012563"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Планирование интеграции Skype для бизнеса и Exchange
 
**Сводка:** Просмотрите эту тему, чтобы узнать, как интегрировать Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013 г.
  
Прежде чем интегрировать Skype для бизнеса Server и Exchange Server, необходимо убедиться, что Exchange Server и Skype для бизнеса Server полностью установлены и запущены. 
  
Дополнительные сведения об установке Exchange Server см. в Exchange Server документации по планированию и развертыванию для Exchange. 
   
После запуска и запуска серверов необходимо назначить сертификаты проверки подлинности от сервера к серверу как для Skype для бизнеса Server, так и для Exchange Server; эти сертификаты позволяют Skype для бизнеса Server и Exchange Server обмениваться информацией и общаться друг с другом. При установке Exchange Server для вас создается самозаверяется сертификат с именем Microsoft Exchange Server сертификата Auth. Этот сертификат, который можно найти в локальном хранилище сертификатов компьютера, следует использовать для проверки подлинности от сервера к серверу на Exchange Server. Сведения о назначении сертификатов в Exchange Server см. в [материале Configure Mail Flow клиентского доступа.](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)
  
Для Skype для бизнеса Server вы можете использовать существующий сертификат Skype для бизнеса Server в качестве сертификата проверки подлинности от сервера к серверу; например, сертификат по умолчанию также может использоваться в качестве сертификата OAuthTokenIssuer. Skype для бизнеса Server позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности от сервера к серверу при условии, что:
  
- этот сертификат содержит имя домена SIP в поле "Тема";
    
- тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;
    
- длина сертификата составляет не менее 2048 бит.
    
Сведения о сертификатах проверки подлинности от сервера к серверу для Skype для бизнеса Server см. в материале Назначение сертификата проверки подлинности от сервера к [Skype для бизнеса Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
После присвоения сертификатов необходимо настроить службу автооткрытия в Exchange Server. В Exchange Server служба автооткрытия настраивает профили пользователей и предоставляет доступ к Exchange при входе пользователей в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователю следующую информацию:
  
- Сведения о подключении для внутреннего и внешнего подключения к Exchange Server.
    
- Расположение сервера почтовых ящиков пользователя.
    
- URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;
    
- параметры сервера мобильного Outlook.
    
Службу автооткрытия необходимо настроить, прежде чем вы сможете интегрировать Skype для бизнеса Server и Exchange Server. Вы можете проверить, была ли настроена служба автообнаружия, выведя следующую команду из командной Exchange Server и проверив значение свойства AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI будет выглядеть примерно так: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
URI автообнаружения можно назначить с помощью следующей команды:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Сведения о службе автооткрытия см. в материале [Autodiscover Service.](/Exchange/architecture/client-access/autodiscover)
  
После настройки службы автооткрытия необходимо изменить параметры конфигурации Skype для бизнеса Server OAuth; это гарантирует, что Skype для бизнеса Server знает, где найти службу автооткрытия. Чтобы изменить параметры конфигурации OAuth в Skype для бизнеса Server, запустите следующую команду из Skype для бизнеса Server командной оболочки. При запуске этой команды убедитесь, что вы указываете службу автообнаружения службе автообнаружения Exchange Server и что вы используете **autodiscover.svc** для указания расположения службы вместо **autodiscover.xml** (что указывает на XML-файл, используемый службой):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Параметр Identity в предыдущей команде необязателен; это потому, что Skype для бизнеса Server позволяет иметь только одну глобальную коллекцию параметров конфигурации OAuth. Помимо прочего, это означает, что вы можете настроить URL-адрес автооткрытия с помощью этой немного более простой команды: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " " 
> 
> [!NOTE]
> Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени. 
  
Помимо настройки службы автооткрытия необходимо также создать запись DNS для службы, которая указывает на Exchange Server. Например, если служба автооткрытия расположена по адресу autodiscover.litwareinc.com, вам потребуется создать запись DNS для autodiscover.litwareinc.com, которая разрешит полное доменное имя вашего Exchange Server (например, atl-exchange-001.litwareinc.com).
  
Если вы интегрируете Skype для бизнеса Server с Exchange Online, ваши следующие действия находятся в Настройке интеграции между локальной Skype для бизнеса Server и [Outlook Web App,](../../deploy/integrate-with-exchange-server/outlook-web-app.md)в противном случае см. в Skype для бизнеса Server с [Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Поддержка функций
<a name="feature_support"> </a>

>[!Important]
> Skype для бизнеса Он-лайн будет отменен 31 июля 2021 г. после того, как Exchange, перечисленные ниже, которые включают службу, больше не будут поддерживаться.

В следующей таблице подробно представлены функции, поддерживаемые в различных сочетаниях в Интернете или в помещениях для Exchange и Skype для бизнеса.
  
|&nbsp;|Exchange 2016/2013/2010 (в помещении) + Skype для бизнеса Server (на месте)|Exchange Online + Skype для бизнеса Server (на месте)**|**Exchange 2010 (на месте) + Skype для бизнеса Online|Exchange 2016/2013 (на месте) + Skype для бизнеса Online**|**Exchange Online + Skype для бизнеса Online|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Присутствие в Outlook   |Да   |Да   |Да   |Да   |Да   |
|Отвечать с помощью чата, вызова PSTN, Skype или видеосвязи по электронной Outlook электронной почты   |Да   |Да   |Да   |Да   |Да   |
|Расписание и участие в собраниях через Outlook   |Да   |Да   |Да   |Да   |Да   |
|Присутствие в Outlook Web App   |Да   |Да   |Нет   |Нет   |Да   |
|Отвечать с помощью чата, вызова PSTN, Skype или видеовызова по электронной почте OWA   |Да   |Да   |Нет   |Нет   |Да   |
|Запланировать и присоединиться к собраниям через Outlook Web App   |Да   |Да   |Нет   |Нет   |Да   |
|Чат/присутствие в мобильных клиентах   |Да   |Да   |Да   |Да   |Да   |
|Регистрация онлайн-собраний в мобильных клиентах   |Да   |Да   |Да   |Да   |Да   |
|Публикация состояния на основе Outlook и сведений о занятости в календаре   |Да   |Да   |Да   |Да   |Да   |
|Список контактов (через Единый магазин контактов)   |Y (Exchange 2016/2013)   |Да   |Нет   |Нет   |Да   |
|Контактная фотография с высоким разрешением (требуется как минимум Skype для бизнеса Lync 2013 или Skype для бизнеса. Не поддерживается для LWA, мобильных приложений, Lync 2010, Lync для Mac и других старых клиентов.)   |Y (Exchange 2016/2013)   |Да   |Нет   |Да   |Да   |
|Делегирования собраний   |Да   |Да   |Да   |Да   |Да   |
|История пропущенных разговоров и журналы вызовов пишутся в почтовый ящик exchange пользователя   |Да   |Да   |Да   |Да   |Да   |
|Архивавка контента (im и meeting) в Exchange   |Y (Exchange 2016/2013)   |Да   |Нет   |Нет   |Да   |
|Поиск архивного контента   |Y (Exchange 2016/2013)   |Да   |Нет   |Нет   |Да   |
|Exchange Голосовая почта um   |Да   |Да   |Нет   |Нет   |Нет   |
|История разговоров стороной сервера   |Да   |Да   |Нет   |Да   |Да   |

> [!NOTE]
> Существует служба облачная голосовая почта, которая поддерживается для Skype для бизнеса Online, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 и Lync Server 2013.
> 

## <a name="see-also"></a>См. также
<a name="feature_support"> </a>

[Настройка интеграции между локальной Skype для бизнеса Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Настройка OAuth между Skype для бизнеса Online и Exchange в помещениях](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Интеграция Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Интеграция Exchange Server 2013 г. с Lync Server 2013, Skype для бизнеса Online или гибридным развертыванием Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Настройка партнерских приложений в Skype для бизнеса Server и Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
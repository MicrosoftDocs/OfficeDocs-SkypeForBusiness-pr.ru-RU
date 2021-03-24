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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: Сводка. Обзор этой темы для получения сведений о том, как интегрировать Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013.
ms.openlocfilehash: 6b2fdab1a25db7d56c99e965877cb684d102da36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098675"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Планирование интеграции Skype для бизнеса и Exchange
 
**Сводка:** Просмотрите эту тему, чтобы узнать, как интегрировать Skype для бизнеса Server Exchange Server 2016 или Exchange Server 2013.
  
Прежде чем интегрировать Skype для бизнеса Server и Exchange Server, необходимо убедиться, что Exchange Server и Skype для бизнеса Server полностью установлены и запущены. 
  
Дополнительные сведения об установке Exchange Server см. в Exchange Server документации по планированию и развертыванию для вашей версии Exchange. 
   
После запуска и запуска серверов необходимо назначить сертификаты проверки подлинности от сервера к серверу как Skype для бизнеса Server, так и Exchange Server; эти сертификаты позволяют Skype для бизнеса Server и Exchange Server обмениваться информацией и общаться друг с другом. При установке Exchange Server для вас создается самозаверяется сертификат с именем Microsoft Exchange Server сертификата Auth. Этот сертификат, который можно найти в локальном хранилище сертификатов компьютера, следует использовать для проверки подлинности от сервера к серверу на Exchange Server. Сведения о назначении сертификатов в Exchange Server см. в материале Настройка потока почты [и клиентского доступа.](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)
  
Для Skype для бизнеса Server можно использовать существующий сертификат Skype для бизнеса Server в качестве сертификата проверки подлинности от сервера к серверу; например, сертификат по умолчанию также может использоваться в качестве сертификата OAuthTokenIssuer. Skype для бизнеса Server позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности от сервера к серверу при условии, что:
  
- этот сертификат содержит имя домена SIP в поле "Тема";
    
- тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;
    
- длина сертификата составляет не менее 2048 бит.
    
Сведения о сертификатах проверки подлинности от сервера к серверу для Skype для бизнеса см. в материале Назначение сертификата проверки подлинности от сервера к серверу [Skype для бизнеса Server.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
После присвоения сертификатов необходимо настроить службу автооткрытия на Exchange Server. В Exchange Server служба автообнаружия настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователей в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователю следующую информацию:
  
- Сведения о подключении для внутреннего и внешнего подключения к Exchange Server.
    
- Расположение сервера почтовых ящиков пользователя.
    
- URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;
    
- параметры сервера мобильного Outlook.
    
Чтобы интегрировать Skype для бизнеса Server и Exchange Server, необходимо настроить службу автоматического Exchange Server. Вы можете проверить, была ли настроена служба автообнаружия, выведя следующую команду из командной Exchange Server и проверив значение свойства AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI будет выглядеть примерно так: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
URI автообнаружения можно назначить с помощью следующей команды:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Сведения о службе автооткрытия см. в материале [Autodiscover Service.](/Exchange/architecture/client-access/autodiscover)
  
После настройки службы автооткрытия необходимо изменить параметры конфигурации Skype для бизнеса Server OAuth; Это гарантирует, что Skype для бизнеса Server знает, где найти службу автооткрытия. Чтобы изменить параметры конфигурации OAuth в Skype для бизнеса Server, запустите следующую команду из командной оболочки Skype для бизнес-серверов. При запуске этой команды убедитесь, что вы указываете службу автообнаружения службе автообнаружения, запущенную на Exchange Server, и что вы используете **autodiscover.svc** для указания расположения службы вместо **autodiscover.xml** (что указывает на XML-файл, используемый службой):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Параметр Identity в предыдущей команде необязателен; Это потому, что Skype для бизнеса Server позволяет иметь только одну глобальную коллекцию параметров конфигурации OAuth. Помимо прочего, это означает, что вы можете настроить URL-адрес автооткрытия с помощью этой немного более простой команды: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " " 
> 
> [!NOTE]
> Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени. 
  
Помимо настройки службы автооткрытия необходимо также создать запись DNS для службы, которая указывает на Exchange Server. Например, если служба автооткрытия расположена по адресу autodiscover.litwareinc.com, вам потребуется создать запись DNS для autodiscover.litwareinc.com, которая разрешит полное доменное имя вашего Exchange Server (например, atl-exchange-001.litwareinc.com).
  
Если вы интегрируете Skype для бизнеса Server с Exchange Online, ваши дальнейшие действия в настройке интеграции между локальной skype для бизнеса Server и [Outlook Web App,](../../deploy/integrate-with-exchange-server/outlook-web-app.md)в противном случае см. в этой ссылке Интеграция [Skype для](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)бизнеса Server с Exchange Server .
  
## <a name="feature-support"></a>Поддержка функций
<a name="feature_support"> </a>

>[!Important]
> Skype для бизнеса Online будет отменен 31 июля 2021 г. после того, как интеграции Exchange, перечисленные ниже, которые включают службу, больше не будут поддерживаться.

В следующей таблице представлены функции, поддерживаемые в различных сочетаниях в Интернете или на локальной основе для Exchange и Skype для бизнеса.
  
||**Exchange 2016/2013/2010 (на месте) + Skype для бизнеса Server (на месте)**|**Exchange Online + Skype для бизнеса Server (на месте)**|**Exchange 2010 (на месте) + Skype для бизнеса Online**|**Exchange 2016/2013 (на месте) + Skype для бизнеса Online**|**Exchange Online + Skype для бизнеса Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Присутствие в Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Отвечать с помощью чата, вызова PSTN, skype call или видеосвязи из электронной почты Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Расписание и участие в онлайн-собраниях через Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Присутствие в Outlook Web App  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Отвечать с помощью чата, вызова PSTN, skype call или видеовызова по электронной почте OWA  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Расписание и участие в собраниях через Outlook Web App  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Чат/присутствие в мобильных клиентах  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Регистрация онлайн-собраний в мобильных клиентах  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Публикация состояния на основе сведений о свободном/загруженном календаре Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Список контактов (через Единый магазин контактов)  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Контактная фотография с высоким разрешением (требуется как минимум для клиентов Lync 2013 или Skype для бизнеса). Не поддерживается для LWA, мобильных приложений, Lync 2010, Lync для Mac и других старых клиентов.)  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |Да  <br/> |Да  <br/> |
|Делегирования собраний  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|История пропущенных разговоров и журналы вызовов пишутся в почтовый ящик exchange пользователя  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Архивавка контента (im и meeting) в Exchange  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Поиск архивного контента  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Голосовая почта exchange um  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |N  <br/> |
|История разговоров стороной сервера  <br/> |Да  <br/> |Да  <br/> |N  <br/> |Да  <br/> |Да  <br/> |

> [!NOTE]
> Существует служба облачной голосовой почты, которая поддерживается для Skype для бизнеса Online, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 и Lync Server 2013.
> 

## <a name="see-also"></a>См. также
<a name="feature_support"> </a>

[Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Настройка OAuth между Skype для бизнеса Online и Exchange на локальной основе](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Интеграция Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Интеграция Exchange Server 2013 г. с Lync Server 2013, Skype для бизнеса Online или гибридное развертывание Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Настройка партнерских приложений в Skype для бизнеса Server и Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
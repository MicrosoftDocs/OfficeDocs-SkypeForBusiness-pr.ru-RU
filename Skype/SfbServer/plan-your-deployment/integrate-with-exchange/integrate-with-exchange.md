---
title: Планирование интеграции Skype для бизнеса и Exchange
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Сводка: Просмотрите в этом разделе приведены сведения об интеграции Скайп для Business Server с Exchange Server 2016 или Exchange Server 2013.'
ms.openlocfilehash: 3e94e1ab399e8a8a825826e37a281b377a31037e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213930"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Планирование интеграции Skype для бизнеса и Exchange
 
**Сводка:** Просмотрите в этом разделе приведены сведения об интеграции Скайп для Business Server с Exchange Server 2016 или Exchange Server 2013.
  
Перед Скайп можно интегрировать Business Server и Exchange Server, вам необходимо убедиться, что Скайп для Business Server и Exchange Server полностью установлен и вверх и работает. 
  
Для получения дополнительных сведений об установке Exchange Server в документации Exchange Server планирования и развертывания для вашей версии Exchange. 
   
После серверы, запущено и работает, необходимо назначить сертификаты проверки подлинности сервер сервер для обоих Скайп для Business Server и Exchange Server; Эти сертификаты позволяют Скайп для Business Server и Exchange Server для обмена данными и общаться друг с другом. При установке Exchange Server самозаверяющий сертификат с именем Microsoft Exchange Server проверкой подлинности на основе сертификата будет создан автоматически. Этот сертификат, который можно найти в хранилище сертификатов локального компьютера, можно использовать для проверки подлинности сервер сервер на сервере Exchange. Для получения дополнительных сведений о назначении сертификатов в Exchange Server см [Настройка почтового потока и клиентского доступа](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Для Скайп для Business Server можно использовать существующие Скайп для сертификата Business Server как сертификат проверки подлинности сервер сервер; Например сертификат по умолчанию можно также использовать в качестве сертификат OAuthTokenIssuer. Скайп для Business Server позволяет использовать любой сертификат веб-сервера, как сертификат для проверки подлинности сервер сервер при условии, что:
  
- этот сертификат содержит имя домена SIP в поле "Тема";
    
- тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;
    
- длина сертификата составляет не менее 2048 бит.
    
Для получения дополнительных сведений о сертификатах проверки подлинности сервер сервер для Скайп для Business Server см [назначить сертификат проверки подлинности сервер сервер, который будет Скайп для Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
После назначения сертификатов, затем необходимо настроить службы автообнаружения на сервере Exchange. В Exchange Server службы автообнаружения настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователей в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователям следующую информацию:
  
- Сведения о подключении для внутренних и внешних подключение к Exchange Server.
    
- Расположение сервера почтовых ящиков пользователя.
    
- URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;
    
- параметры сервера мобильного Outlook.
    
Перед интеграцией Скайп для Business Server и Exchange Server, необходимо настроить службы автообнаружения. Вы можете проверить, настроен ли служба автообнаружения, выполнив следующую команду из командной консоли Exchange Server и проверки значения свойства AutoDiscoverServiceInternalUri:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI будет выглядеть примерно так:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
URI автообнаружения можно назначить с помощью следующей команды:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Для получения дополнительных сведений о службе автообнаружения см [Службы автообнаружения](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
После настройки службы автоматического обнаружения необходимо затем изменить Скайп о параметрах конфигурации Business Server OAuth; Это гарантирует, что Скайп для Business Server знает расположение службы автообнаружения. Для изменения параметров конфигурации OAuth в Скайп для Business Server, выполните следующую команду в Скайп для консоли Business Server. При запуске этой команды, убедитесь, что указан URI для службы автообнаружения, запущенные на сервере Exchange, и использовать **autodiscover.svc** для указания на расположение службы вместо **autodiscover.xml** (которая указывает XML-файла используется службой):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Параметр Identity в предыдущей команде является необязательным; Вот так, как только, Скайп для Business Server позволяет иметь одной, глобальной коллекции параметров конфигурации OAuth. Помимо прочего, это означает, что URL-адрес автообнаружения можно настроить с помощью следующей команды несколько упрощает: 
> 
> [!NOTE]
> SET-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени. 
  
В дополнение к настройке службы автообнаружения, необходимо также создать запись DNS для службы, указывающий на сервере Exchange. Например если службы автообнаружения располагается по autodiscover.litwareinc.com необходимо будет создать запись DNS для autodiscover.litwareinc.com, которая разрешает полное доменное имя сервера Exchange (например, ATL-exchange-001.litwareinc.com).
  
Если вы реализуете интеграцию Скайп для Business Server с Exchange Online, выполните следующие действия, в [Настройка интеграции между локальной Скайп для Business Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), в противном случае см [Скайп интегрировать для Business Server с Exchange Сервер](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Поддержка функций
<a name="feature_support"> </a>

В следующей таблице описаны функции, поддерживаемые в разделе различные сочетания версией через Интернет или локальной Exchange и Скайп для бизнеса.
  
||**Exchange 2016/2013/2010 (локально) + Скайп для Business Server (локально)**|**Exchange Online + Скайп для Business Server (локально)**|**Exchange 2010 (локально) + Скайп для бизнеса в Интернет**|**Exchange 2016/2013(on premises) + Скайп для бизнеса в Интернет**|**Exchange Online + Скайп для бизнеса в Интернете**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Присутствие в Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Ответ с помощью мгновенного сообщения, вызова ТСОП, вызова Skype или видеовызова из сообщения электронной почты Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Планирование собраний по сети и присоединение к ним с помощью Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Присутствие в веб-приложении Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Y  <br/> |
|Ответ с помощью мгновенного сообщения, вызова ТСОП, вызова Skype или видеовызова из сообщения электронной почты OWA  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Y  <br/> |
|Планирование собраний по сети и присоединение к ним с помощью веб-приложения Outlook OWA  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Y  <br/> |
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Присоединение к собраниям по сети в мобильных клиентах  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Публикация состояния в соответствии со сведениями о доступности в календаре Outlook  <br/> |Да  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Да  <br/> |
|Список контактов (из единого хранилища контактов)  <br/> |Да (требуется Exchange 2016 или 2013)  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Y  <br/> |
|С высоким разрешением фотографий контактов (требует Lync 2013 или Скайп пользователей по крайней мере. Не поддерживается для LWA, мобильных приложений, Lync 2010, Lync для Mac и других устаревших версий клиентов.)  <br/> |Да (требуется Exchange 2016 или 2013)  <br/> |Y  <br/> |Нет  <br/> |Y  <br/> |Y  <br/> |
|Делегирование собрания  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Почтовый ящик exchange пользователя должны записываться пропущенных журнал бесед и журналы вызовов  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> |Да (требуется Exchange 2016 или 2013)  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Y  <br/> |
|Поиск заархивированного содержимого  <br/> |Да (требуется Exchange 2016 или 2013)  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Да  <br/> |
|Голосовая почты системы обмена сообщениями Exchange  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Нет  <br/> |Нет  <br/> |
|Журнал бесед на стороне сервера  <br/> |Да  <br/> |Y  <br/> |Нет  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Существует голосовой почты облачной службы, которая поддерживается для Скайп для бизнеса в Интернет, Скайп для Business Server 2019, Скайп для Business Server 2015 и Lync Server 2013.
> 

## <a name="see-also"></a>См. также
<a name="feature_support"> </a>

[Настройка интеграции между локальной Скайп для Business Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Настройка подключения по протоколу OAuth между Skype для бизнеса Online и локальной системой Exchange](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Интеграция Скайп для Business Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Как можно интегрировать Exchange Server 2013 с Lync Server 2013, Скайп для бизнеса в Интернет или гибридного развертывания Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Настройка партнерских приложений в Скайп Business Server и Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)

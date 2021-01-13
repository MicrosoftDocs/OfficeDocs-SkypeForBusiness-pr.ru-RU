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
description: Сводка. Сведения об интеграции Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013.
ms.openlocfilehash: f2a9dfc718b7891a0cbe9b7b1455df24531a6ed0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810104"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Планирование интеграции Skype для бизнеса и Exchange
 
**Сводка:** В этом разделе вы также знаете, как интегрировать Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013.
  
Перед интеграцией Skype для бизнеса Server и Exchange Server необходимо убедиться, что обе системы Exchange Server и Skype для бизнеса Server полностью установлены и запущены. 
  
Дополнительные сведения об установке Exchange Server см. в документации Exchange Server планирования и развертывания для вашей версии Exchange. 
   
После того как серверы будут запущены, необходимо назначить сертификаты проверки подлинности "сервер-сервер" как Skype для бизнеса Server, так и Exchange Server; эти сертификаты позволяют Skype для бизнеса Server и Exchange Server обмениваться информацией и взаимодействовать друг с другом. При установке Exchange Server сертификат с именем Microsoft Exchange Server сертификата auth создается самостоятельно. Этот сертификат, который можно найти в хранилище сертификатов локального компьютера, следует использовать для проверки подлинности "сервер-сервер" в Exchange Server. Подробные сведения о назначении сертификатов в Exchange Server см. в подстроке "Настройка потока почты [и клиентского доступа".](https://go.microsoft.com/fwlink/p/?LinkId=268540)
  
Для Skype для бизнеса Server можно использовать существующий сертификат Skype для бизнеса Server в качестве сертификата проверки подлинности "сервер-сервер"; Например, сертификат по умолчанию также можно использовать в качестве сертификата OAuthTokenIssuer. Skype для бизнеса Server позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности "сервер-сервер" при условии, что:
  
- этот сертификат содержит имя домена SIP в поле "Тема";
    
- тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;
    
- длина сертификата составляет не менее 2048 бит.
    
Подробные сведения о сертификатах проверки подлинности "сервер-сервер" для Skype для бизнеса Server см. в сведениях о назначении сертификата проверки подлинности ["сервер-сервер" Skype для бизнеса Server.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
После того как сертификаты будут назначены, необходимо настроить службу автоотнаружия на Exchange Server. В Exchange Server служба автообнаружия настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователей в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователю следующую информацию:
  
- Сведения о под соединении как для внутреннего, так и для внешнего подключения к Exchange Server.
    
- Расположение сервера почтовых ящиков пользователя.
    
- URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;
    
- параметры сервера мобильного Outlook.
    
Перед интеграцией Skype для бизнеса Server и Exchange Server необходимо настроить службу автоо Exchange Server. Вы можете проверить, настроена ли служба автообнаружия, выведя следующую команду из командной Exchange Server и проверив значение свойства AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI выглядит примерно так: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
URI автообнаружения можно назначить с помощью следующей команды:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Подробные сведения о службе автоотнаружия см. в [этой теме.](https://go.microsoft.com/fwlink/p/?LinkId=268542)
  
После настройки службы автооружия необходимо изменить параметры конфигурации OAuth Skype для бизнеса Server; Это гарантирует, что Skype для бизнеса Server знает, где найти службу автооружия. To modify the OAuth configuration settings in Skype for Business Server, run the following command from within the Skype for Business Server Management Shell. При запуске этой команды необходимо указать URI для службы автообнаружения, запущенной в службе Exchange Server, и указать расположение службы с помощью **autodiscover.svc** **вместоautodiscover.xml** (что указывает на XML-файл, используемый службой):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Параметр Identity в предыдущей команде является необязательным; Это потому, что Skype для бизнеса Server позволяет использовать только одну глобальную коллекцию параметров конфигурации OAuth. Помимо прочего, это означает, что вы можете настроить URL-адрес автооружия с помощью этой немного более простой команды: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени. 
  
Помимо настройки службы автоотнаружение, необходимо также создать запись DNS для службы, которая указывает на Exchange Server. Например, если служба автоотнаружия расположена по адресу autodiscover.litwareinc.com вам потребуется создать запись DNS для autodiscover.litwareinc.com, которая будет разрешать полное доменное имя Exchange Server (например, atl-exchange-001.litwareinc.com).
  
Если вы интегрируете Skype для бизнеса Server с Exchange Online, вы можете настроить интеграцию между [локальной](../../deploy/integrate-with-exchange-server/outlook-web-app.md)skype для бизнеса Server и Outlook Web App. В противном случае см. ["Интеграция Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)для бизнеса Server с Exchange Server.
  
## <a name="feature-support"></a>Поддержка функций
<a name="feature_support"> </a>

>[!Important]
> Skype для бизнеса Online будет отключен 31 июля 2021 г. после того, как перечисленные ниже интеграции Exchange, включив службу, больше не будут поддерживаться.

В следующей таблице представлены функции, поддерживаемые различными сочетаниями сетевых или сетевых функций для Exchange и Skype для бизнеса.
  
||**Exchange 2016/2013/2010 (локально) + Skype для бизнеса Server (локально)**|**Exchange Online + Skype для бизнеса Server (локально)**|**Exchange 2010 (локально) + Skype для бизнеса Online**|**Exchange 2016/2013 (локально) + Skype для бизнеса Online**|**Exchange Online + Skype для бизнеса Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Присутствие в Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Ответ с помощью мгновенных сообщений, звонков по STN, звонков Skype или видеозвонков из электронной почты Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Планировать собрания по сети и присоединяться к ним через Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Присутствие в Outlook Web App  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Ответ с помощью мгновенных сообщений, звонков по STN, звонков Skype или видеовызовов из электронной почты OWA  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Запланировать собрания по сети и присоединиться к ним с помощью Outlook Web App  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Im/Presence в мобильных клиентах  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Присоединяйтесь к собраниям по сети в мобильных клиентах  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Публикация состояния на основе сведений о занятости в календаре Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Список контактов (через единое хранилище контактов)  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Фотография контакта с высоким разрешением (требуется как минимум клиенты Lync 2013 или Skype для бизнеса). Не поддерживается для LWA, мобильных приложений, Lync 2010, Lync для Mac и других старых клиентов.)  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |Да  <br/> |Да  <br/> |
|Делегирования собраний  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Журнал пропущенных бесед и журналы вызовов записаны в почтовый ящик exchange пользователя  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Архивное содержимое (im и meeting) в Exchange  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Поиск архивного контента  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Голосовая почта exchange UM  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |N  <br/> |
|История бесед на стороне сервера  <br/> |Да  <br/> |Да  <br/> |N  <br/> |Да  <br/> |Да  <br/> |

> [!NOTE]
> Для Skype для бизнеса Online, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 и Lync Server 2013 поддерживается облачная служба голосовой почты.
> 

## <a name="see-also"></a>См. также
<a name="feature_support"> </a>

[Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Настройка OAuth между Skype для бизнеса Online и локальной сетью Exchange](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Интеграция Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Интеграция Exchange Server 2013 с Lync Server 2013, Skype для бизнеса Online или гибридным развертыванием Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Настройка партнерских приложений в Skype для бизнеса Server и Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)

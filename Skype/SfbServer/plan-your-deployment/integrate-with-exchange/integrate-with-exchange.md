---
title: Планирование интеграции Skype для бизнеса и Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: Сводка. Ознакомьтесь с этой статьей, чтобы узнать, как интегрировать Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013.
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359265"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Планирование интеграции Skype для бизнеса и Exchange
 
**Сводка:** Просмотрите этот раздел, чтобы узнать, как интегрировать Skype для бизнеса Server с Exchange Server 2016 или Exchange Server 2013.
  
Перед интеграцией Skype для бизнеса Server и Exchange Server необходимо убедиться, что серверы Exchange Server и Skype для бизнеса Server полностью установлены и запущены. 
  
Для получения дополнительных сведений об установке Exchange Server ознакомьтесь с документацией по планированию и развертыванию Exchange Server для вашей версии Exchange. 
   
После установки и запуска серверов необходимо назначить сертификаты проверки подлинности между серверами в Skype для бизнеса Server и Exchange Server. Эти сертификаты позволяют Skype для бизнеса Server и Exchange Server обмениваться информацией и общаться друг с другом. При установке Exchange Server создается самозаверяющий сертификат с именем сертификата проверки подлинности Microsoft Exchange Server. Этот сертификат, который можно найти в хранилище сертификатов локального компьютера, должен использоваться для проверки подлинности между серверами на сервере Exchange Server. Более подробную информацию о назначении сертификатов в Exchange Server можно узнать в статье [Настройка почтового процесса и клиентского доступа](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Для Skype для бизнеса Server вы можете использовать существующий сертификат Skype для бизнеса Server в качестве сертификата проверки подлинности "сервер-сервер"; Например, сертификат по умолчанию также можно использовать в качестве сертификата OAuthTokenIssuer. Skype для бизнеса Server позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности "сервер-сервер", при условии, что:
  
- этот сертификат содержит имя домена SIP в поле "Тема";
    
- тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;
    
- длина сертификата составляет не менее 2048 бит.
    
Сведения о сертификатах проверки подлинности "сервер-сервер" для Skype для бизнеса Server приведены [в статье назначение сертификата проверки подлинности "сервер-сервер" в Skype для бизнеса Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
После назначения сертификатов необходимо настроить службу автообнаружения на сервере Exchange Server. В Exchange Server служба автообнаружения настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователей в систему. Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователю следующую информацию:
  
- Сведения о подключении для внутреннего и внешнего подключения к серверу Exchange Server.
    
- Расположение сервера почтовых ящиков пользователя.
    
- URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;
    
- параметры сервера мобильного Outlook.
    
Прежде чем интегрировать Skype для бизнеса Server и Exchange Server, необходимо настроить службу автообнаружения. Вы можете проверить, настроена ли служба автообнаружения, выполнив следующую команду в командной консоли Exchange Server и проверив значение свойства AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Если это значение пусто, необходимо назначить URI службе автообнаружения. Как правило, этот URI будет выглядеть примерно так: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
URI автообнаружения можно назначить с помощью следующей команды:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Подробные сведения о службе автообнаружения можно найти в статье [Служба автообнаружения](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
После настройки службы автообнаружения необходимо изменить параметры конфигурации OAuth для Skype для бизнеса Server; Это гарантирует, что Skype для бизнеса Server будет знать, где найти службу автообнаружения. Чтобы изменить параметры конфигурации OAuth в Skype для бизнеса Server, выполните следующую команду в командной консоли Skype для бизнеса Server. При выполнении этой команды необходимо указать URI для службы автообнаружения, запущенной на сервере Exchange Server, а также использовать службу **автообнаружения. svc** для указания расположения службы, а не **autodiscover.xml** (что указывает на XML-файл, используемый службой):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Параметр Identity в предыдущей команде является необязательным; Это связано с тем, что Skype для бизнеса Server позволяет только использовать одну глобальную коллекцию параметров конфигурации OAuth. Помимо прочего, это означает, что вы можете настроить URL-адрес автообнаружения, используя немного более простую команду: 
> 
> [!NOTE]
> Set – CsOAuthConfiguration — Ексчанжеаутодисковерурл " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени. 
  
В дополнение к настройке службы автообнаружения необходимо также создать запись DNS для службы, указывающей на сервер Exchange. Например, если служба автообнаружения расположена по адресу autodiscover.litwareinc.com, необходимо создать запись DNS для autodiscover.litwareinc.com, которая разрешается в полное доменное имя сервера Exchange (например, atl-exchange-001.litwareinc.com).
  
Если вы интегрируете Skype для бизнеса Server с Exchange Online, выполните следующие действия, чтобы [настроить интеграцию между локальной системой Skype для бизнеса Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), в противном случае ознакомьтесь со статьей [интеграция Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Поддержка функций
<a name="feature_support"> </a>

>[!Important]
> Skype для бизнеса Online будет прекращен до 31 июля 2021 после того, как перечисленные ниже интеграции Exchange, содержащие эту службу, больше не будут поддерживаться.

В следующей таблице подробно описаны функции, поддерживаемые в различных сочетаниях в Интернете или локальной среде для Exchange и Skype для бизнеса.
  
||**Exchange 2016/2013/2010 (локальная среда) + Skype для бизнеса Server (локальная)**|**Exchange Online + Skype для бизнеса Server (локально)**|**Exchange 2010 (локальная среда) + Skype для бизнеса Online**|**Exchange 2016/2013 (локальная среда) + Skype для бизнеса Online**|**Exchange Online + Skype для бизнеса Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Присутствие в Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Ответ через мгновенные сообщения, Звонок по PSTN, вызов Skype или видеозвонок из электронной почты Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Планирование и присоединение к собраниям по сети с помощью Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Сведения о присутствии в Outlook Web App  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Ответ через мгновенные сообщения, Звонок по PSTN, вызов Skype или видеовызов из электронной почты OWA  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Планирование и присоединение к собраниям по сети с помощью Outlook Web App  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Обмен мгновенными сообщениями и присутствие в мобильных клиентах  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Присоединение к собраниям по сети в мобильных клиентах  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Публикация состояния на основе сведений о доступности в календаре Outlook  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Список контактов (через единое хранилище контактов)  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Фото контакта с высоким разрешением (требуются клиенты Lync 2013 или Skype для бизнеса как минимум. Не поддерживается для лва, мобильных приложений, Lync 2010, Lync для Mac и других более ранних версий клиентов.)  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |Да  <br/> |Да  <br/> |
|Делегирование собрания  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Журнал бесед и журналы звонков записываются в почтовый ящик Exchange пользователя  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |Да  <br/> |
|Архивация содержимого (мгновенных сообщений и собраний) в Exchange  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Поиск в архивном контенте  <br/> |Y (требуется Exchange 2016/2013)  <br/> |Да  <br/> |N  <br/> |N  <br/> |Да  <br/> |
|Голосовая почта единой системы обмена сообщениями Exchange  <br/> |Да  <br/> |Да  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Журнал бесед на стороне сервера  <br/> |Да  <br/> |Да  <br/> |N  <br/> |Да  <br/> |Да  <br/> |

> [!NOTE]
> Существует облачная служба голосовой почты, которая поддерживается в Skype для бизнеса Online, Skype для бизнеса Server 2019, Skype для бизнеса Server 2015 и Lync Server 2013.
> 

## <a name="see-also"></a>См. также
<a name="feature_support"> </a>

[Настройка интеграции между локальной системой Skype для бизнеса Server и Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Настройка OAuth между Skype для бизнеса Online и Exchange локально](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Интеграция Skype для бизнеса Server с Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Интеграция Exchange Server 2013 с Lync Server 2013, Skype для бизнеса Online или гибридным развертыванием Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Настройка партнерских приложений в Skype для бизнеса Server и Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)

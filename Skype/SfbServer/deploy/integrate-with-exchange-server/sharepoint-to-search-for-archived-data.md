---
title: Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Сводка: Настройка SharePoint Server для поиска данных архивации с Exchange Server и Скайп для Business Server.'
ms.openlocfilehash: f6bf82348744ea5c3d650c348634dddd7628ad74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894269"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint
 
**Сводка:** Настройка SharePoint Server для поиска данных архивации с Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server.
  
Одним из главных преимуществ для хранения обмен мгновенными сообщениями и конференц-связи Web расшифровки в Exchange Server вместо Скайп для Business Server — это, что хранение данных в одном месте позволяет администраторам использовать единый инструмент для поиска архивированных данных Exchange и/или Скайп архивных данных Business Server. Так как все, что данные хранятся в одном поместить (Exchange) любое средство, которое можно найти архивированных данных Exchange можно выполнять поиск архивных Скайп для данных Business Server.
  
Одно средство, которое облегчает поиск архивных данных является Microsoft SharePoint Server 2013. Если вы хотите использовать SharePoint для поиска для Скайп данных Business Server, необходимо сначала выполнить все шаги, необходимые для настройки архивации на базе Exchange в Скайп для Business Server. После Скайп для Business Server и Exchange Server успешно интеграции, затем необходимо установить [Управляемого API веб-служб](https://go.microsoft.com/fwlink/p/?LinkId=258305) Exchange на сервере SharePoint. Загруженный файл (EWSManagedAPI.msi) можно сохранить в любой папке на сервере SharePoint.
  
По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:
  
1. Для открытия командного окна нажмите кнопку **Пуск**, выберите **Все программы**, затем **Стандартные**, щелкните на элементе **Командная строка** правой кнопкой мыши и выберите **Запуск от имени администратора**.
    
2. В командном окне с помощью команды cd измените текущий каталог, указав папку, в которой сохранен файл EWSManagedAPI.msi. Например если вы сохранили файл C:\Downloads введите следующую команду в командной строке и нажмите клавишу ВВОД:
    
   ```
   cd C:\Downloads
   ```

3. Установка API-интерфейса, введите следующую команду, затем нажмите клавишу ВВОД:
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. После установки API сброс служб IIS, введя следующую команду и нажмите клавишу ВВОД:
    
   ```
   iisreset
   ```

После установки веб-служб Exchange необходимо затем настроить проверки подлинности сервер сервер между SharePoint Server и Exchange Server. Для этого откройте консоль управления SharePoint и выполните следующий набор команд:
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не используйте пример URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
После создания автора маркера и настройки службы маркеров выполните следующие команды, подставив URL-адрес сайта SharePoint для примера URL-адресаhttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Для настройки проверки подлинности сервер сервер для Exchange Server, откройте командную консоль Exchange и выполните команду следующего вида (предполагается, что Exchange была установлена на диске C: и что он использует путь к папке по умолчанию).
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

После настройки партнерского приложения рекомендуется остановите и перезапустите Internet Information Services (IIS) на всех почтовых ящиков и клиентского доступа серверах Exchange. Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.
  
```
iisreset atl-exchange-001
```

Эту команду можно выполнить из командной консоли Exchange или из другого командного окна.
  
Затем выполните команду, аналогичную следующей, которая предоставляет указанному пользователю (в данном примере kenmyer) право на выполнение обнаружения в Exchange:
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

После установки проверки подлинности сервер сервер между Exchange и SharePoint следующим шагом является создание на сайте eDiscovery в SharePoint. Который можно выполнить с помощью команды следующего вида из консоли управления SharePoint:
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции. 
  
Когда новый сайт будет готов, следующим шагом является настройка Exchange Server для действия в результате источника для SharePoint. Это можно сделать, выполнив следующую процедуру на странице центра администрирования SharePoint:
  
1. На странице центра администрирования выберите **Управление приложениями-службами**, затем **Приложение-служба поиска**.
    
2. На странице "Приложение-служба поиска: администрирование поиска" выберите **Источники результатов**, затем **Создать источник результата**.
    
3. В области **Новый источник результата** введите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите в качестве источника результатов **протокол** **Exchange** , а затем введите URL-адрес источника web services для сервера Exchange в поле **URL-адрес источника Exchange** . URL-адрес источника имеет следующий вид:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Убедитесь в том, что не выбран режим **Использовать автоопределение**, затем нажмите **ОК**.
    
И, наконец создайте новое обращение eDiscovery и новый набор eDiscovery, выполнив следующую процедуру с сайта SharePoint Discovery (например,https://atl-sharepoint-001/sites/discovery):
  
1. На странице "Содержимое сайта" выберите **Создать обращение**.
    
2. На странице "Содержимое сайта: новый сайт SharePoint" введите псевдоним пользователя электронной почты (например, **kenmyer**) в поле **Заголовок**, затем добавьте этот URL-адрес в поле **Адрес веб-сайта**. Получается URL-адрес следующего вида:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Нажмите **Создать**.
    
4. При появлении страницы набора eDiscovery выберите **Создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.
    
5. На странице "Создать: набор обнаружения" введите псевдоним пользователя электронной почты в поле **Имя набора обнаружения**. Введите **eDiscovery Lync\\*** в **Фильтр** и нажмите кнопку **Добавить &amp; Управление источниками**.
    
6. На странице Добавление &amp; Управление источниками введите псевдоним электронной почты пользователя в текстовом поле первой в группе **почтовые ящики**. Щелкните на значке почтового ящика рядом со учебником для проверки связи SharePoint с указанным почтовым ящиком.
    
7. Нажмите **ОК**.
    
8. На странице набора eDiscovery нажмите кнопку **Сохранить** для сохранения нового набора eDiscovery.
    
На этом этапе можно выполнить поиск указанного почтового ящика (kenmyer) и/или включить на месте хранения так же, как и для любой другой SharePoint содержимого или источника результатов.
  


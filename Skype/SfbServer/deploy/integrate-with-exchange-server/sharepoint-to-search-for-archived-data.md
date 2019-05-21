---
title: Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Сводка: Настройка SharePoint Server для поиска данных, архивированных сервером Exchange Server и приложением Skype для бизнеса Server.'
ms.openlocfilehash: 2fb4b601e594ca48105afcf2e0c75107b2c6bceb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278079"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint
 
**Сводка:** Настройте сервер SharePoint Server для поиска данных, архивированных с помощью Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
  
Одним из основных преимуществ хранения мгновенных сообщений и веб-конференций на сервере Exchange Server, а не в Skype для бизнеса, является хранение данных в одном и том же месте, позволяющее администраторам использовать один инструмент для поиска архивных данных Exchange. и (или) архивированные данные в Skype для бизнеса Server. Так как все данные хранятся на одном и том же место (Exchange), все средства, которые могут искать архивные данные Exchange, также могут выполнять поиск архивированных данных в Skype для бизнеса Server.
  
Одним из средств, позволяющим найти архивные данные, является Microsoft SharePoint Server 2013. Если вы хотите использовать SharePoint для поиска данных сервера Skype для бизнеса, необходимо сначала выполнить все действия, связанные с настройкой архивации Exchange в Skype для бизнеса Server. После успешной интеграции Exchange Server и Skype для бизнеса Server необходимо установить [управляемый API веб-служб](https://go.microsoft.com/fwlink/p/?LinkId=258305) Exchange на сервер SharePoint. Загруженный файл (EWSManagedAPI.msi) можно сохранить в любой папке на сервере SharePoint.
  
По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:
  
1. Для открытия командного окна нажмите кнопку **Пуск**, выберите **Все программы**, затем **Стандартные**, щелкните на элементе **Командная строка** правой кнопкой мыши и выберите **Запуск от имени администратора**.
    
2. В командном окне с помощью команды cd измените текущий каталог, указав папку, в которой сохранен файл EWSManagedAPI.msi. Например, если вы сохранили файл в К:\довнлоадс, введите в окне команд следующую команду и нажмите клавишу ВВОД.
    
   ```
   cd C:\Downloads
   ```

3. Чтобы установить API-интерфейс, введите указанную ниже команду и нажмите клавишу ВВОД.
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. После установки API выполните следующую команду и нажмите клавишу ВВОД, чтобы выполнить сброс IIS.
    
   ```
   iisreset
   ```

После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" между SharePoint Server и Exchange Server. Для этого сначала откройте командную консоль SharePoint и выполните следующий набор команд:
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не используйте образец URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
После создания поставщика маркера и настройки службы маркеров выполните следующие команды, чтобы заменить URL-адрес сайта SharePoint на пример URL-адреса.http://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Чтобы настроить проверку подлинности "сервер-сервер" для Exchange Server, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и для него используется путь к папке по умолчанию):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS на всех ваших почтовом ящике Exchange и серверах клиентского доступа. Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.
  
```
iisreset atl-exchange-001
```

Эту команду можно выполнять в командной консоли Exchange или в любом другом окне команд.
  
Затем выполните следующую команду, которая предоставляет указанному пользователю (в данном примере, кенмер) право на обнаружение в Exchange.
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

После установки проверки подлинности между сервером Exchange и SharePoint следующим шагом является создание сайта обнаружения электронных данных в SharePoint. Это можно сделать, запустив команды, аналогичные указанным в командной консоли SharePoint:
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции. 
  
После того как новый сайт будет готов, далее следует настроить сервер Exchange Server для работы в качестве источника результатов для SharePoint. Это можно сделать, выполнив описанную ниже процедуру на странице центра администрирования SharePoint.
  
1. На странице центра администрирования выберите **Управление приложениями-службами**, затем **Приложение-служба поиска**.
    
2. На странице "Приложение-служба поиска: администрирование поиска" выберите **Источники результатов**, затем **Создать источник результата**.
    
3. В области **Новый источник результата** введите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите **Exchange** в качестве **протокола**источника результатов, а затем введите URL-адрес источника веб-служб для сервера Exchange в поле **URL-адрес источника данных Exchange** . URL-адрес источника имеет следующий вид:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Убедитесь в том, что не выбран режим **Использовать автоопределение**, затем нажмите **ОК**.
    
Наконец, создайте новый сценарий обнаружения электронных данных и новый набор eDiscovery, выполнив описанные ниже действия на сайте обнаружения SharePoint (например,https://atl-sharepoint-001/sites/discovery):
  
1. На странице "Содержимое сайта" выберите **Создать обращение**.
    
2. На странице "Содержимое сайта: новый сайт SharePoint" введите псевдоним пользователя электронной почты (например, **kenmyer**) в поле **Заголовок**, затем добавьте этот URL-адрес в поле **Адрес веб-сайта**. Получается URL-адрес следующего вида:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Нажмите **Создать**.
    
4. При появлении страницы набора eDiscovery выберите **Создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.
    
5. На странице "Создать: набор обнаружения" введите псевдоним пользователя электронной почты в поле **Имя набора обнаружения**. Введите **Lync\\* для обнаружения электронных**данных в поле " **Фильтр** " и нажмите кнопку " ** &amp; добавить Управление источниками**".
    
6. На странице Add &amp; Sources in (добавить источники) введите псевдоним электронной почты пользователя в первом поле в разделе Почтовые **ящики**. Щелкните на значке почтового ящика рядом со учебником для проверки связи SharePoint с указанным почтовым ящиком.
    
7. Нажмите **ОК**.
    
8. На странице набора eDiscovery нажмите кнопку **Сохранить** для сохранения нового набора eDiscovery.
    
На этом этапе вы можете выполнить поиск по указанному почтовому ящику (кенмер) и (или) разрешать на месте, так же, как и в случае с другим контентом или источником результатов SharePoint.
  


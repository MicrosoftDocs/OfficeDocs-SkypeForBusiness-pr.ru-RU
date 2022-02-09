---
title: Настройка SharePoint Server для поиска архивных Skype для бизнеса данных
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: Сводка. Настройте SharePoint Server для поиска данных, архивируемых Exchange Server и Skype для бизнеса Server.
ms.openlocfilehash: 0f2954d5a9875e3009733fc6d869ca57afbf086b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397298"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Настройка SharePoint Server для поиска архивных Skype для бизнеса данных
 
**Сводка:** Настройте SharePoint Server для поиска данных, архивируемых Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
  
Одно из главных преимуществ хранения стенограмм обмена мгновенными сообщениями и веб-конференций в Exchange Server вместо Skype для бизнеса Server заключается в том, что хранение данных в одном расположении позволяет администраторам использовать единый инструмент для поиска архивных Exchange данных и/или архива. Skype для бизнеса Server данных. Так как все данные хранятся в одном месте (Exchange), любой инструмент, который может искать архивные Exchange, также может искать архивные Skype для бизнеса Server данные.
  
Одним из средств, упрощает поиск архивных данных, является Microsoft SharePoint Server 2013 г. Если вы хотите использовать SharePoint для поиска Skype для бизнеса Server данных, сначала необходимо выполнить все действия, связанные с настройкой Exchange архива в Skype для бизнеса Server. После Exchange Server и Skype для бизнеса Server успешной интеграции необходимо установить [API](https://go.microsoft.com/fwlink/p/?LinkId=258305) управляемых Exchange веб-служб на SharePoint Server. Загруженный файл (EWSManagedAPI.msi) можно сохранить в любую папку на сервере SharePoint.
  
По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:
  
1. Чтобы открыть командную строку, нажмите **Пуск**, выберите пункт **Все программы**, **Стандартные**, щелкните правой кнопкой мыши **Командная строка** и выберите **Запуск от имени администратора**.
    
2. В командной строке введите команду cd, чтобы изменить текущий каталог на папку, в которую сохранен файл EWSManagedAPI.msi. Например, если файл сохранен в C:\Downloads, введите следующую команду в окне команды и нажмите кнопку Ввод:
    
   ```console
   cd C:\Downloads
   ```

3. Чтобы установить API, введите следующую команду, а затем нажмите кнопку Введите:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. После установки API сбросить IIS, введя следующую команду и нажав кнопку Ввод:
    
   ```console
   iisreset
   ```

После Exchange веб-служб необходимо настроить проверку подлинности от сервера к серверу между SharePoint Server и Exchange Server. Для этого сначала откройте SharePoint командную команду и запустите следующий набор команд:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не используйте образец URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
После создания эмитента маркеров и настройки службы маркеров запустите эти команды, чтобы заменить URL SharePoint сайта для примера URL-адреса`http://atl-sharepoint-001`:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Чтобы настроить проверку подлинности от сервера к серверу для Exchange Server, откройте команду Exchange Management Shell и запустите команду, аналогичную этой (если предположить, что Exchange установлена на диске C: и что она использует путь папки по умолчанию):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS (IIS) на всех Exchange почтовых ящиках и серверах клиентского доступа. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Эта команда может запускаться из Exchange или из любого другого окна команды.
  
Далее запустите команду, аналогичную следующей, которая дает указанному пользователю (в этом примере kenmyer) право на обнаружение в Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

После проверки подлинности между сервером и сервером между Exchange и SharePoint, следующим шагом будет создание сайта по обнаружению электронных данных в SharePoint. Это можно сделать, запуская команды, аналогичные этим из SharePoint Командная оболочка:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции. 
  
Когда новый сайт будет готов, следующим шагом будет настройка Exchange Server, чтобы действовать в качестве источника результатов для SharePoint. Это можно сделать, завершив следующую процедуру на странице SharePoint центра администрирования:
  
1. На странице Центра администрирования выберите **Управление приложениями-службами**, после чего нажмите **Приложение службы поиска**.
    
2. На странице "Приложение службы поиска: администрирование поиска" выберите **Источники результатов** и нажмите **Создать источник результатов**.
    
3. В области **Новый источник результатов** укажите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите **Exchange** в качестве источника результатов **Протокола**, а затем введите URL-адрес источника веб-служб для Exchange сервера в **поле Exchange исходный URL-адрес**. Исходный URL-адрес выглядит следующим образом:
    
    `https://atl-exchange-001.litwareinc.com/ews/exchange.asmx`
    
4. Убедитесь в том, что не выбран пункт **Использовать автоопределение**, и нажмите **ОК**.
    
Наконец, создайте новый случай обнаружения электронных обнаружений и набор новых электронных открытий, завершив следующую процедуру с сайта SharePoint Discovery (например, `https://atl-sharepoint-001/sites/discovery`):
  
1. На странице "Содержимое сайта" выберите **Создать обращение**.
    
2. На странице "Содержимое сайта: новый сайт SharePoint" укажите псевдоним электронной почты пользователя (например, **kenmyer**) в поле **Заголовок**, после чего добавьте этот URL-адрес в поле **Адрес веб-сайта**. В результате получаем URL-адрес следующего вида:
    
    `https://atl-sharepoint-001/sites/eDiscovery/kenmyer`
    
3. Нажмите **Создать**.
    
4. После того как отобразится страница набора eDiscovery, выберите **создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.
    
5. На странице "Создать: набор обнаружения" введите псевдоним электронной почты пользователя в поле **Имя набора обнаружения**. **Введите Lync\\_ eDiscovery** в поле _ *Filter** и нажмите **кнопку Добавить источники &amp; управления**.
    
6. На странице Add &amp; Manage Sources введите псевдоним электронной почты пользователя в первом текстовом ящике в **почтовых ящиках**. Щелкните значок почтового ящика рядом со значком учебника, чтобы проверить подключение SharePoint к указанному почтовому ящику.
    
7. Нажмите кнопку **ОК**.
    
8. На странице "Набор eDiscovery" нажмите **Сохранить**, чтобы сохранить набор eDiscovery.
    
На этом этапе можно искать указанный почтовый ящик (kenmyer) и/или включить In-Place, как и для любого другого SharePoint или источника результатов.
  


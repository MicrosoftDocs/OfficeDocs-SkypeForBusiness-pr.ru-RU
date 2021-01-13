---
title: Настройка SharePoint Server для поиска архивных данных Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: Сводка. Настройка SharePoint Server для поиска данных, архивируемых Exchange Server и Skype для бизнеса Server.
ms.openlocfilehash: 406e0a713c65bc147ce6eb492f251a25ea2a3afc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833949"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Настройка SharePoint Server для поиска архивных данных Skype для бизнеса
 
**Сводка:** Настройте SharePoint Server для поиска данных, архивируемых Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
  
Одно из основных преимуществ хранения расшифровок мгновенных сообщений и веб-конференций в Exchange Server вместо Skype для бизнеса Server заключается в том, что хранение данных в одном расположении позволяет администраторам использовать одно средство для поиска архивных данных Exchange и/или архивных данных Skype для бизнеса Server. Так как все данные хранятся в одном месте (Exchange), любое средство, которое может искать архивные данные Exchange, также может искать архивные данные Skype для бизнеса Server.
  
Одним из средств, упрощая поиск архивных данных, является Microsoft SharePoint Server 2013. Если вы хотите использовать SharePoint для поиска данных Skype для бизнеса Server, сначала необходимо выполнить все действия по настройке архива exchange в Skype для бизнеса Server. После Exchange Server интеграции Skype для бизнеса Server необходимо установить управляемый [API](https://go.microsoft.com/fwlink/p/?LinkId=258305) веб-служб Exchange на сервере SharePoint Server. Загруженный файл (EWSManagedAPI.msi) можно сохранить в любую папку на сервере SharePoint.
  
По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:
  
1. Чтобы открыть командную строку, нажмите **Пуск**, выберите пункт **Все программы**, **Стандартные**, щелкните правой кнопкой мыши **Командная строка** и выберите **Запуск от имени администратора**.
    
2. В командной строке введите команду cd, чтобы изменить текущий каталог на папку, в которую сохранен файл EWSManagedAPI.msi. Например, если файл сохранен в папке C:\Downloads, введите в командном окне следующую команду и нажмите ввод:
    
   ```console
   cd C:\Downloads
   ```

3. Чтобы установить API, введите следующую команду и нажмите ввод:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. После установки API сбросить IIS, введя следующую команду и нажав ввод:
    
   ```console
   iisreset
   ```

После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" между SharePoint Server и Exchange Server. Для этого сначала откройте командную оболочку SharePoint и запустите следующий набор команд:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не используйте пример https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 URI. 
  
После создания и настройки службы маркеров запустите эти команды, заменив URL-адрес сайта SharePoint на пример URL-адреса http://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Чтобы настроить проверку подлинности "сервер-сервер" для Exchange Server, откройте командную Exchange Server Exchange и запустите команду, аналогичную этой (предполагается, что Exchange установлен на диске C: и использует путь к папке по умолчанию):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на всех серверах почтовых ящиков и клиентского доступа Exchange. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Эту команду можно выполнить из командной оболочки Exchange или из любого другого командного окна.
  
Затем запустите команду, аналогичную следующей, которая предоставляет указанному пользователю (в данном примере kenmyer) право на обнаружение в Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

После проверки подлинности "сервер-сервер" между Exchange и SharePoint необходимо создать сайт eDiscovery в SharePoint. Для этого можно использовать команды, аналогичные указанным в командной оболочке SharePoint:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции. 
  
Когда новый сайт будет готов, необходимо настроить Exchange Server в качестве источника результатов для SharePoint. Это можно сделать, выполив следующую процедуру на странице центра администрирования SharePoint:
  
1. На странице Центра администрирования выберите **Управление приложениями-службами**, после чего нажмите **Приложение службы поиска**.
    
2. На странице "Приложение службы поиска: администрирование поиска" выберите **Источники результатов** и нажмите **Создать источник результатов**.
    
3. В области **Новый источник результатов** укажите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите Exchange в качестве протокола источника результатов, а затем введите URL-адрес источника веб-служб для сервера **Exchange** в поле **"URL-адрес источника Exchange".** Исходный URL-адрес выглядит следующим образом:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Убедитесь в том, что не выбран пункт **Использовать автоопределение**, и нажмите **ОК**.
    
Наконец, создайте новое дело eDiscovery и новый набор eDiscovery, выполнив следующую процедуру на сайте обнаружения SharePoint (например, https://atl-sharepoint-001/sites/discovery):
  
1. На странице "Содержимое сайта" выберите **Создать обращение**.
    
2. На странице "Содержимое сайта: новый сайт SharePoint" укажите псевдоним электронной почты пользователя (например, **kenmyer**) в поле **Заголовок**, после чего добавьте этот URL-адрес в поле **Адрес веб-сайта**. В результате получаем URL-адрес следующего вида:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Нажмите **Создать**.
    
4. После того как отобразится страница набора eDiscovery, выберите **создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.
    
5. На странице "Создать: набор обнаружения" введите псевдоним электронной почты пользователя в поле **Имя набора обнаружения**. Введите **eDiscovery \\ Lync** _ в поле *_Filter** и нажмите кнопку **"Добавить &amp; источники управления".**
    
6. На странице "Добавление источников управления" введите псевдоним электронной почты пользователя в первом текстовом ящике &amp; в **области "Почтовые ящики".** Щелкните значок почтового ящика рядом со значком учебника, чтобы проверить подключение SharePoint к указанному почтовому ящику.
    
7. Нажмите кнопку **ОК**.
    
8. На странице "Набор eDiscovery" нажмите **Сохранить**, чтобы сохранить набор eDiscovery.
    
На этом этапе можно искать в указанном почтовом ящике (kenmyer) и/или включить In-Place так же, как для любого другого контента SharePoint или источника результатов.
  


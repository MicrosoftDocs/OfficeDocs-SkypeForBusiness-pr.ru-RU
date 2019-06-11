---
title: 'Lync Server 2013: Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381db352aae635358dfd62cc1965ea238960bf8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-04_

Одним из основных преимуществ хранения мгновенных сообщений и веб-конференций в Microsoft Exchange Server 2013 вместо Microsoft Lync Server 2013 является тот факт, что хранение данных в одном и том же месте позволяет администраторам использовать один инструмент для поиска. Архивация данных Exchange и архивирование данных сервера Lync. Так как все данные хранятся на одном и том же место (Exchange), любые средства, которые могут выполнять поиск архивных данных Exchange, также могут выполнять поиск архивированных данных сервера Lync.

Одним из средств, позволяющим найти архивные данные, является Microsoft SharePoint Server 2013. Если вы хотите использовать SharePoint для поиска данных сервера Lync, необходимо сначала выполнить все действия, связанные с настройкой архивации Exchange в Lync Server. После успешной интеграции Exchange 2013 и Lync Server 2013 необходимо установить управляемый API веб-служб Exchange версии 2,0 на сервере SharePoint. программу установки для этого API можно скачать в центре загрузки Майкрософт ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)). Загруженный файл (EWSManagedAPI.msi) можно сохранить в любой папке на сервере SharePoint.

По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:

1.  Для открытия командного окна нажмите кнопку **Пуск**, выберите **Все программы**, затем **Стандартные**, щелкните на элементе **Командная строка** правой кнопкой мыши и выберите **Запуск от имени администратора**.

2.  В командном окне с помощью команды **cd** измените текущий каталог, указав папку, в которой сохранен файл EWSManagedAPI.msi. Например, если вы сохранили файл в формате C:\\downloads, введите в окне команд следующую команду и нажмите клавишу ВВОД:
    
        cd C:\Downloads

3.  Чтобы установить API введите следующую команду и нажмите ВВОД:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  После установки API выполните сброс IIS. Для этого введите следующую команду и нажмите ВВОД:
    
        iisreset

После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" между SharePoint Server 2013 и Exchange 2013. Для этого сначала откройте командную консоль SharePoint 2013 и выполните следующий набор команд:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не используйте образец URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.



</div>

После создания поставщика маркера и настройки службы маркеров выполните следующие команды, чтобы заменить URL-адрес сайта SharePoint на пример URL-адреса.http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Чтобы настроить проверку подлинности "сервер-сервер" для Exchange 2013, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и для него используется путь к папке по умолчанию):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS на всех ваших почтовом ящике Exchange и серверах клиентского доступа. Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.

    iisreset atl-exchange-001

Эту команду можно выполнять в командной консоли Exchange или в любом другом окне команд.

Затем выполните следующую команду, которая предоставляет указанному пользователю (в данном примере, кенмер) право на обнаружение в Exchange.

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

После установки проверки подлинности между сервером Exchange и SharePoint необходимо создать сайт обнаружения электронных данных в SharePoint. Это можно сделать, запустив команды, аналогичные указанным в командной консоли SharePoint:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.



</div>

После того как новый сайт будет готов, следующий шаг — настроить Exchange 2013 для использования в качестве источника результатов для SharePoint. Это можно сделать, выполнив описанную ниже процедуру на странице центра администрирования SharePoint 2013.

1.  На странице центра администрирования выберите **Управление приложениями-службами**, затем **Приложение-служба поиска**.

2.  На странице "Приложение-служба поиска: администрирование поиска" выберите **Источники результатов**, затем **Создать источник результата**.

3.  В области **Новый источник результата** введите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите **Exchange** в качестве **протокола**источника результатов, а затем введите URL-адрес источника веб-служб для сервера Exchange в поле **URL-адрес источника данных Exchange** . URL-адрес источника имеет следующий вид:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Убедитесь в том, что не выбран режим **Использовать автоопределение**, затем нажмите **ОК**.

Наконец, создайте новый сценарий обнаружения электронных данных и новый набор eDiscovery, выполнив описанные ниже действия на сайте обнаружения SharePoint (например,https://atl-sharepoint-001/sites/discovery):

1.  На странице "Содержимое сайта" выберите **Создать обращение**.

2.  На странице "Содержимое сайта: новый сайт SharePoint" введите псевдоним пользователя электронной почты (например, **kenmyer**) в поле **Заголовок**, затем добавьте этот URL-адрес в поле **Адрес веб-сайта**. Получается URL-адрес следующего вида:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Нажмите **Создать**.

4.  При появлении страницы набора eDiscovery выберите **Создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.

5.  На странице "Создать: набор обнаружения" введите псевдоним пользователя электронной почты в поле **Имя набора обнаружения**. В поле **Фильтр** введите **Lync\* для обнаружения электронных** данных и нажмите кнопку **Добавить & Управление источниками**.

6.  На странице "Добавление источников и управление ими" введите псевдоним электронной почты в текстовом поле в разделе **Почтовые ящики**. Щелкните на значке почтового ящика рядом со учебником для проверки связи SharePoint с указанным почтовым ящиком.

7.  Нажмите **ОК**.

8.  На странице набора eDiscovery нажмите кнопку **Сохранить** для сохранения нового набора eDiscovery.

На этом этапе вы можете выполнить поиск по указанному почтовому ящику (кенмер) и (или) разрешать на месте, так же, как и в случае с другим контентом или источником результатов SharePoint.

</div>

<span> </span>

</div>

</div>

</div>


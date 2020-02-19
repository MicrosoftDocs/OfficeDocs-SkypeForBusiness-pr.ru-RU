---
title: 'Lync Server 2013: Настройка Microsoft SharePoint Server 2013 для поиска архивных данных Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e9599e0790c3d3468273ba27ea26f28ed3d766
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Настройка Microsoft SharePoint Server 2013 для поиска архивных данных Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-04_

Одним из основных преимуществ хранения сообщений об обмене мгновенными сообщениями и веб-конференций в Microsoft Exchange Server 2013 вместо Microsoft Lync Server 2013 является тот факт, что хранение данных в одном и том же расположении позволяет администраторам использовать одно средство для поиска архивированных данных Exchange и/или архивных данных Lync Server. Так как все данные хранятся на одном месте (Exchange), все средства, которые могут выполнять поиск архивных данных Exchange, также могут выполнять поиск архивных данных Lync Server.

Одним из средств, облегчающим Поиск архивных данных, является Microsoft SharePoint Server 2013. Если вы хотите использовать SharePoint для поиска данных Lync Server, необходимо сначала выполнить все действия, необходимые для настройки архивации Exchange в Lync Server. После успешной интеграции Exchange 2013 и Lync Server 2013 необходимо установить управляемый API веб-служб Exchange версии 2,0 на сервере SharePoint. программу установки для этого API можно скачать в центре загрузки Майкрософт ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)). Загруженный файл (EWSManagedAPI.msi) можно сохранить в любую папку на сервере SharePoint.

По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:

1.  Чтобы открыть командную строку, нажмите **Пуск**, выберите пункт **Все программы**, **Стандартные**, щелкните правой кнопкой мыши **Командная строка** и выберите **Запуск от имени администратора**.

2.  В командной строке введите команду **cd**, чтобы изменить текущий каталог на папку, в которую сохранен файл EWSManagedAPI.msi. Например, если вы сохранили файл в формате C:\\downloads, введите в командной строке следующую команду и нажмите клавишу ВВОД:
    
        cd C:\Downloads

3.  Чтобы установить API введите следующую команду и нажмите ВВОД:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  После установки API выполните сброс IIS. Для этого введите следующую команду и нажмите ВВОД:
    
        iisreset

После установки веб-служб Exchange необходимо настроить межсерверную проверку подлинности между SharePoint Server 2013 и Exchange 2013. Для этого сначала откройте командную консоль SharePoint 2013 и выполните следующий набор команд:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Обязательно используйте универсальный код ресурса (URI) для службы автоопределения. Не используйте пример URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.



</div>

После создания поставщика маркера и настройки службы маркеров выполните указанные ниже команды, заменив URL-адрес сайта SharePoint на пример URL-адреса.http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Чтобы настроить межсерверную проверку подлинности для Exchange 2013, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и использует путь к папке по умолчанию):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на всех серверах почтовых ящиков Exchange и клиентского доступа. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:

    iisreset atl-exchange-001

Эту команду можно выполнить в командной консоли Exchange или в любом другом командном окне.

Затем выполните команду, аналогичную приведенной ниже, которая дает указанному пользователю (в данном примере kenmyer) право на выполнение обнаружения в Exchange:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

После установки проверки подлинности между серверами Exchange и SharePoint необходимо создать сайт обнаружения электронных данных в SharePoint. Для этого выполните указанные ниже команды в командной консоли SharePoint.

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.



</div>

После того как новый сайт будет готов, следующим шагом будет настройка Exchange 2013 для работы в качестве источника результатов для SharePoint. Это можно сделать, выполнив следующую процедуру на странице центра администрирования SharePoint 2013:

1.  На странице Центра администрирования выберите **Управление приложениями-службами**, после чего нажмите **Приложение службы поиска**.

2.  На странице "Приложение службы поиска: администрирование поиска" выберите **Источники результатов** и нажмите **Создать источник результатов**.

3.  В области **Новый источник результатов** укажите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**. Выберите **Exchange** в качестве **протокола**источника результатов, а затем введите URL-адрес источника веб-служб для сервера Exchange в поле **URL-адрес источника Exchange** . Исходный URL-адрес выглядит следующим образом:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Убедитесь в том, что не выбран пункт **Использовать автоопределение**, и нажмите **ОК**.

Наконец, создайте новое дело обнаружения электронных данных и новый набор eDiscovery, выполнив следующую процедуру на сайте обнаружения SharePoint (например,https://atl-sharepoint-001/sites/discovery):

1.  На странице "Содержимое сайта" выберите **Создать обращение**.

2.  На странице "Содержимое сайта: новый сайт SharePoint" укажите псевдоним электронной почты пользователя (например, **kenmyer**) в поле **Заголовок**, после чего добавьте этот URL-адрес в поле **Адрес веб-сайта**. В результате получаем URL-адрес следующего вида:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Нажмите **Создать**.

4.  После того как отобразится страница набора eDiscovery, выберите **создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.

5.  На странице "Создать: набор обнаружения" введите псевдоним электронной почты пользователя в поле **Имя набора обнаружения**. В поле **Фильтр** введите **Lync\* eDiscovery** и нажмите кнопку **Добавить & управления источниками**.

6.  На странице "Добавление и управление источниками" укажите псевдоним электронной почты пользователя в текстовом поле в разделе **Почтовые ящики**. Щелкните значок почтового ящика рядом со значком учебника, чтобы проверить подключение SharePoint к указанному почтовому ящику.

7.  Нажмите кнопку **ОК**.

8.  На странице "Набор eDiscovery" нажмите **Сохранить**, чтобы сохранить набор eDiscovery.

На этом шаге вы можете выполнить поиск в указанном почтовом ящике (kenmyer) и/или включить удержание на месте так же, как и для любого другого контента SharePoint или источника результатов.

</div>

<span> </span>

</div>

</div>

</div>


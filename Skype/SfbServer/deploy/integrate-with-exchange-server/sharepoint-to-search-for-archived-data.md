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
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="33e83-103">Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint</span><span class="sxs-lookup"><span data-stu-id="33e83-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="33e83-104">**Сводка:** Настройка SharePoint Server для поиска данных архивации с Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="33e83-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="33e83-105">Одним из главных преимуществ для хранения обмен мгновенными сообщениями и конференц-связи Web расшифровки в Exchange Server вместо Скайп для Business Server — это, что хранение данных в одном месте позволяет администраторам использовать единый инструмент для поиска архивированных данных Exchange и/или Скайп архивных данных Business Server.</span><span class="sxs-lookup"><span data-stu-id="33e83-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="33e83-106">Так как все, что данные хранятся в одном поместить (Exchange) любое средство, которое можно найти архивированных данных Exchange можно выполнять поиск архивных Скайп для данных Business Server.</span><span class="sxs-lookup"><span data-stu-id="33e83-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="33e83-107">Одно средство, которое облегчает поиск архивных данных является Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33e83-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="33e83-108">Если вы хотите использовать SharePoint для поиска для Скайп данных Business Server, необходимо сначала выполнить все шаги, необходимые для настройки архивации на базе Exchange в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="33e83-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="33e83-109">После Скайп для Business Server и Exchange Server успешно интеграции, затем необходимо установить [Управляемого API веб-служб](https://go.microsoft.com/fwlink/p/?LinkId=258305) Exchange на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33e83-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="33e83-110">Загруженный файл (EWSManagedAPI.msi) можно сохранить в любой папке на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33e83-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="33e83-111">По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:</span><span class="sxs-lookup"><span data-stu-id="33e83-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="33e83-112">Для открытия командного окна нажмите кнопку **Пуск**, выберите **Все программы**, затем **Стандартные**, щелкните на элементе **Командная строка** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="33e83-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="33e83-113">В командном окне с помощью команды cd измените текущий каталог, указав папку, в которой сохранен файл EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="33e83-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="33e83-114">Например если вы сохранили файл C:\Downloads введите следующую команду в командной строке и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="33e83-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="33e83-115">Установка API-интерфейса, введите следующую команду, затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="33e83-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="33e83-116">После установки API сброс служб IIS, введя следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="33e83-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="33e83-117">После установки веб-служб Exchange необходимо затем настроить проверки подлинности сервер сервер между SharePoint Server и Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="33e83-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="33e83-118">Для этого откройте консоль управления SharePoint и выполните следующий набор команд:</span><span class="sxs-lookup"><span data-stu-id="33e83-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="33e83-119">Обязательно используйте универсальный код ресурса (URI) для службы автоопределения.</span><span class="sxs-lookup"><span data-stu-id="33e83-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="33e83-120">Не используйте пример URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="33e83-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="33e83-121">После создания автора маркера и настройки службы маркеров выполните следующие команды, подставив URL-адрес сайта SharePoint для примера URL-адресаhttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="33e83-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="33e83-122">Для настройки проверки подлинности сервер сервер для Exchange Server, откройте командную консоль Exchange и выполните команду следующего вида (предполагается, что Exchange была установлена на диске C: и что он использует путь к папке по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="33e83-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="33e83-123">После настройки партнерского приложения рекомендуется остановите и перезапустите Internet Information Services (IIS) на всех почтовых ящиков и клиентского доступа серверах Exchange.</span><span class="sxs-lookup"><span data-stu-id="33e83-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="33e83-124">Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.</span><span class="sxs-lookup"><span data-stu-id="33e83-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="33e83-125">Эту команду можно выполнить из командной консоли Exchange или из другого командного окна.</span><span class="sxs-lookup"><span data-stu-id="33e83-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="33e83-126">Затем выполните команду, аналогичную следующей, которая предоставляет указанному пользователю (в данном примере kenmyer) право на выполнение обнаружения в Exchange:</span><span class="sxs-lookup"><span data-stu-id="33e83-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="33e83-127">После установки проверки подлинности сервер сервер между Exchange и SharePoint следующим шагом является создание на сайте eDiscovery в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33e83-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="33e83-128">Который можно выполнить с помощью команды следующего вида из консоли управления SharePoint:</span><span class="sxs-lookup"><span data-stu-id="33e83-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="33e83-129">Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.</span><span class="sxs-lookup"><span data-stu-id="33e83-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="33e83-130">Когда новый сайт будет готов, следующим шагом является настройка Exchange Server для действия в результате источника для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33e83-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="33e83-131">Это можно сделать, выполнив следующую процедуру на странице центра администрирования SharePoint:</span><span class="sxs-lookup"><span data-stu-id="33e83-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="33e83-132">На странице центра администрирования выберите **Управление приложениями-службами**, затем **Приложение-служба поиска**.</span><span class="sxs-lookup"><span data-stu-id="33e83-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="33e83-133">На странице "Приложение-служба поиска: администрирование поиска" выберите **Источники результатов**, затем **Создать источник результата**.</span><span class="sxs-lookup"><span data-stu-id="33e83-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="33e83-134">В области **Новый источник результата** введите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="33e83-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="33e83-135">Выберите в качестве источника результатов **протокол** **Exchange** , а затем введите URL-адрес источника web services для сервера Exchange в поле **URL-адрес источника Exchange** .</span><span class="sxs-lookup"><span data-stu-id="33e83-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="33e83-136">URL-адрес источника имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="33e83-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="33e83-137">Убедитесь в том, что не выбран режим **Использовать автоопределение**, затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33e83-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="33e83-138">И, наконец создайте новое обращение eDiscovery и новый набор eDiscovery, выполнив следующую процедуру с сайта SharePoint Discovery (например,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="33e83-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="33e83-139">На странице "Содержимое сайта" выберите **Создать обращение**.</span><span class="sxs-lookup"><span data-stu-id="33e83-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="33e83-p110">На странице "Содержимое сайта: новый сайт SharePoint" введите псевдоним пользователя электронной почты (например, **kenmyer**) в поле **Заголовок**, затем добавьте этот URL-адрес в поле **Адрес веб-сайта**. Получается URL-адрес следующего вида:</span><span class="sxs-lookup"><span data-stu-id="33e83-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="33e83-142">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="33e83-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="33e83-143">При появлении страницы набора eDiscovery выберите **Создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="33e83-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="33e83-144">На странице "Создать: набор обнаружения" введите псевдоним пользователя электронной почты в поле **Имя набора обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="33e83-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="33e83-145">Введите **eDiscovery Lync\\**\* в **Фильтр** и нажмите кнопку **Добавить &amp; Управление источниками**.</span><span class="sxs-lookup"><span data-stu-id="33e83-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="33e83-146">На странице Добавление &amp; Управление источниками введите псевдоним электронной почты пользователя в текстовом поле первой в группе **почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="33e83-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="33e83-147">Щелкните на значке почтового ящика рядом со учебником для проверки связи SharePoint с указанным почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="33e83-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="33e83-148">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="33e83-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="33e83-149">На странице набора eDiscovery нажмите кнопку **Сохранить** для сохранения нового набора eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="33e83-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="33e83-150">На этом этапе можно выполнить поиск указанного почтового ящика (kenmyer) и/или включить на месте хранения так же, как и для любой другой SharePoint содержимого или источника результатов.</span><span class="sxs-lookup"><span data-stu-id="33e83-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  


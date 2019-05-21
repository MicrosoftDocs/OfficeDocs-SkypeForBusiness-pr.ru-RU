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
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="49f76-103">Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint</span><span class="sxs-lookup"><span data-stu-id="49f76-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="49f76-104">**Сводка:** Настройте сервер SharePoint Server для поиска данных, архивированных с помощью Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49f76-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="49f76-105">Одним из основных преимуществ хранения мгновенных сообщений и веб-конференций на сервере Exchange Server, а не в Skype для бизнеса, является хранение данных в одном и том же месте, позволяющее администраторам использовать один инструмент для поиска архивных данных Exchange. и (или) архивированные данные в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49f76-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="49f76-106">Так как все данные хранятся на одном и том же место (Exchange), все средства, которые могут искать архивные данные Exchange, также могут выполнять поиск архивированных данных в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49f76-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="49f76-107">Одним из средств, позволяющим найти архивные данные, является Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49f76-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="49f76-108">Если вы хотите использовать SharePoint для поиска данных сервера Skype для бизнеса, необходимо сначала выполнить все действия, связанные с настройкой архивации Exchange в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49f76-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="49f76-109">После успешной интеграции Exchange Server и Skype для бизнеса Server необходимо установить [управляемый API веб-служб](https://go.microsoft.com/fwlink/p/?LinkId=258305) Exchange на сервер SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49f76-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="49f76-110">Загруженный файл (EWSManagedAPI.msi) можно сохранить в любой папке на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49f76-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="49f76-111">По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:</span><span class="sxs-lookup"><span data-stu-id="49f76-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="49f76-112">Для открытия командного окна нажмите кнопку **Пуск**, выберите **Все программы**, затем **Стандартные**, щелкните на элементе **Командная строка** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="49f76-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="49f76-113">В командном окне с помощью команды cd измените текущий каталог, указав папку, в которой сохранен файл EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="49f76-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="49f76-114">Например, если вы сохранили файл в К:\довнлоадс, введите в окне команд следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="49f76-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="49f76-115">Чтобы установить API-интерфейс, введите указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="49f76-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="49f76-116">После установки API выполните следующую команду и нажмите клавишу ВВОД, чтобы выполнить сброс IIS.</span><span class="sxs-lookup"><span data-stu-id="49f76-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="49f76-117">После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" между SharePoint Server и Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="49f76-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="49f76-118">Для этого сначала откройте командную консоль SharePoint и выполните следующий набор команд:</span><span class="sxs-lookup"><span data-stu-id="49f76-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="49f76-119">Обязательно используйте универсальный код ресурса (URI) для службы автоопределения.</span><span class="sxs-lookup"><span data-stu-id="49f76-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="49f76-120">Не используйте образец URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="49f76-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="49f76-121">После создания поставщика маркера и настройки службы маркеров выполните следующие команды, чтобы заменить URL-адрес сайта SharePoint на пример URL-адреса.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="49f76-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="49f76-122">Чтобы настроить проверку подлинности "сервер-сервер" для Exchange Server, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и для него используется путь к папке по умолчанию):</span><span class="sxs-lookup"><span data-stu-id="49f76-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="49f76-123">После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS на всех ваших почтовом ящике Exchange и серверах клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="49f76-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="49f76-124">Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.</span><span class="sxs-lookup"><span data-stu-id="49f76-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="49f76-125">Эту команду можно выполнять в командной консоли Exchange или в любом другом окне команд.</span><span class="sxs-lookup"><span data-stu-id="49f76-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="49f76-126">Затем выполните следующую команду, которая предоставляет указанному пользователю (в данном примере, кенмер) право на обнаружение в Exchange.</span><span class="sxs-lookup"><span data-stu-id="49f76-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="49f76-127">После установки проверки подлинности между сервером Exchange и SharePoint следующим шагом является создание сайта обнаружения электронных данных в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49f76-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="49f76-128">Это можно сделать, запустив команды, аналогичные указанным в командной консоли SharePoint:</span><span class="sxs-lookup"><span data-stu-id="49f76-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="49f76-129">Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.</span><span class="sxs-lookup"><span data-stu-id="49f76-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="49f76-130">После того как новый сайт будет готов, далее следует настроить сервер Exchange Server для работы в качестве источника результатов для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49f76-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="49f76-131">Это можно сделать, выполнив описанную ниже процедуру на странице центра администрирования SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49f76-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="49f76-132">На странице центра администрирования выберите **Управление приложениями-службами**, затем **Приложение-служба поиска**.</span><span class="sxs-lookup"><span data-stu-id="49f76-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="49f76-133">На странице "Приложение-служба поиска: администрирование поиска" выберите **Источники результатов**, затем **Создать источник результата**.</span><span class="sxs-lookup"><span data-stu-id="49f76-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="49f76-134">В области **Новый источник результата** введите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="49f76-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="49f76-135">Выберите **Exchange** в качестве **протокола**источника результатов, а затем введите URL-адрес источника веб-служб для сервера Exchange в поле **URL-адрес источника данных Exchange** .</span><span class="sxs-lookup"><span data-stu-id="49f76-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="49f76-136">URL-адрес источника имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="49f76-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="49f76-137">Убедитесь в том, что не выбран режим **Использовать автоопределение**, затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49f76-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="49f76-138">Наконец, создайте новый сценарий обнаружения электронных данных и новый набор eDiscovery, выполнив описанные ниже действия на сайте обнаружения SharePoint (например,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="49f76-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="49f76-139">На странице "Содержимое сайта" выберите **Создать обращение**.</span><span class="sxs-lookup"><span data-stu-id="49f76-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="49f76-p110">На странице "Содержимое сайта: новый сайт SharePoint" введите псевдоним пользователя электронной почты (например, **kenmyer**) в поле **Заголовок**, затем добавьте этот URL-адрес в поле **Адрес веб-сайта**. Получается URL-адрес следующего вида:</span><span class="sxs-lookup"><span data-stu-id="49f76-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="49f76-142">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="49f76-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="49f76-143">При появлении страницы набора eDiscovery выберите **Создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="49f76-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="49f76-144">На странице "Создать: набор обнаружения" введите псевдоним пользователя электронной почты в поле **Имя набора обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="49f76-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="49f76-145">Введите \**Lync\\* для обнаружения электронных**данных в поле " **Фильтр** " и нажмите кнопку " \*\* &amp; добавить Управление источниками**".</span><span class="sxs-lookup"><span data-stu-id="49f76-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="49f76-146">На странице Add &amp; Sources in (добавить источники) введите псевдоним электронной почты пользователя в первом поле в разделе Почтовые **ящики**.</span><span class="sxs-lookup"><span data-stu-id="49f76-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="49f76-147">Щелкните на значке почтового ящика рядом со учебником для проверки связи SharePoint с указанным почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="49f76-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="49f76-148">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49f76-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="49f76-149">На странице набора eDiscovery нажмите кнопку **Сохранить** для сохранения нового набора eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="49f76-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="49f76-150">На этом этапе вы можете выполнить поиск по указанному почтовому ящику (кенмер) и (или) разрешать на месте, так же, как и в случае с другим контентом или источником результатов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49f76-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  


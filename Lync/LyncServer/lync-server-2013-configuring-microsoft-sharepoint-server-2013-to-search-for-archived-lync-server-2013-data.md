---
title: 'Lync Server 2013: Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Lync Server 2013'
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
ms.openlocfilehash: 1e000f6116b112b3de9840c22c29510745303035
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="15882-102">Настройка Microsoft SharePoint Server 2013 для поиска архивированных данных Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15882-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15882-103">_**Тема последнего изменения:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="15882-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="15882-104">Одним из основных преимуществ хранения мгновенных сообщений и веб-конференций в Microsoft Exchange Server 2013 вместо Microsoft Lync Server 2013 является тот факт, что хранение данных в одном и том же месте позволяет администраторам использовать один инструмент для поиска архивированных данных Exchange и архивированных данных сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15882-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="15882-105">Так как все данные хранятся на одном и том же место (Exchange), любые средства, которые могут выполнять поиск архивных данных Exchange, также могут выполнять поиск архивированных данных сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="15882-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="15882-106">Одним из средств, позволяющим найти архивные данные, является Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15882-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="15882-107">Если вы хотите использовать SharePoint для поиска данных сервера Lync, необходимо сначала выполнить все действия, связанные с настройкой архивации Exchange в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15882-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="15882-108">После успешной интеграции Exchange 2013 и Lync Server 2013 необходимо установить управляемый API веб-служб Exchange версии 2,0 на сервере SharePoint. программу установки для этого API можно скачать в центре загрузки Майкрософт ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span><span class="sxs-lookup"><span data-stu-id="15882-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="15882-109">Загруженный файл (EWSManagedAPI.msi) можно сохранить в любой папке на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15882-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="15882-110">По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:</span><span class="sxs-lookup"><span data-stu-id="15882-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="15882-111">Для открытия командного окна нажмите кнопку **Пуск**, выберите **Все программы**, затем **Стандартные**, щелкните на элементе **Командная строка** правой кнопкой мыши и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="15882-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="15882-112">В командном окне с помощью команды **cd** измените текущий каталог, указав папку, в которой сохранен файл EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="15882-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="15882-113">Например, если вы сохранили файл в формате C:\\downloads, введите в окне команд следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="15882-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="15882-114">Чтобы установить API введите следующую команду и нажмите ВВОД:</span><span class="sxs-lookup"><span data-stu-id="15882-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="15882-115">После установки API выполните сброс IIS. Для этого введите следующую команду и нажмите ВВОД:</span><span class="sxs-lookup"><span data-stu-id="15882-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="15882-116">После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" между SharePoint Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="15882-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="15882-117">Для этого сначала откройте командную консоль SharePoint 2013 и выполните следующий набор команд:</span><span class="sxs-lookup"><span data-stu-id="15882-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="15882-118">Обязательно используйте универсальный код ресурса (URI) для службы автоопределения.</span><span class="sxs-lookup"><span data-stu-id="15882-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="15882-119">Не используйте образец URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="15882-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="15882-120">После создания поставщика маркера и настройки службы маркеров выполните следующие команды, чтобы заменить URL-адрес сайта SharePoint на пример URL-адреса.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="15882-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="15882-121">Чтобы настроить проверку подлинности "сервер-сервер" для Exchange 2013, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и для него используется путь к папке по умолчанию):</span><span class="sxs-lookup"><span data-stu-id="15882-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="15882-122">После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS на всех ваших почтовом ящике Exchange и серверах клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="15882-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="15882-123">Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.</span><span class="sxs-lookup"><span data-stu-id="15882-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="15882-124">Эту команду можно выполнять в командной консоли Exchange или в любом другом окне команд.</span><span class="sxs-lookup"><span data-stu-id="15882-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="15882-125">Затем выполните следующую команду, которая предоставляет указанному пользователю (в данном примере, кенмер) право на обнаружение в Exchange.</span><span class="sxs-lookup"><span data-stu-id="15882-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="15882-126">После установки проверки подлинности между сервером Exchange и SharePoint необходимо создать сайт обнаружения электронных данных в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15882-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="15882-127">Это можно сделать, запустив команды, аналогичные указанным в командной консоли SharePoint:</span><span class="sxs-lookup"><span data-stu-id="15882-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="15882-128">Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.</span><span class="sxs-lookup"><span data-stu-id="15882-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="15882-129">После того как новый сайт будет готов, следующий шаг — настроить Exchange 2013 для использования в качестве источника результатов для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15882-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="15882-130">Это можно сделать, выполнив описанную ниже процедуру на странице центра администрирования SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="15882-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="15882-131">На странице центра администрирования выберите **Управление приложениями-службами**, затем **Приложение-служба поиска**.</span><span class="sxs-lookup"><span data-stu-id="15882-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="15882-132">На странице "Приложение-служба поиска: администрирование поиска" выберите **Источники результатов**, затем **Создать источник результата**.</span><span class="sxs-lookup"><span data-stu-id="15882-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="15882-133">В области **Новый источник результата** введите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="15882-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="15882-134">Выберите **Exchange** в качестве **протокола**источника результатов, а затем введите URL-адрес источника веб-служб для сервера Exchange в поле **URL-адрес источника данных Exchange** .</span><span class="sxs-lookup"><span data-stu-id="15882-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="15882-135">URL-адрес источника имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="15882-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="15882-136">Убедитесь в том, что не выбран режим **Использовать автоопределение**, затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15882-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="15882-137">Наконец, создайте новый сценарий обнаружения электронных данных и новый набор eDiscovery, выполнив описанные ниже действия на сайте обнаружения SharePoint (например,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="15882-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="15882-138">На странице "Содержимое сайта" выберите **Создать обращение**.</span><span class="sxs-lookup"><span data-stu-id="15882-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="15882-p110">На странице "Содержимое сайта: новый сайт SharePoint" введите псевдоним пользователя электронной почты (например, **kenmyer**) в поле **Заголовок**, затем добавьте этот URL-адрес в поле **Адрес веб-сайта**. Получается URL-адрес следующего вида:</span><span class="sxs-lookup"><span data-stu-id="15882-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="15882-141">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="15882-141">Click **Create**.</span></span>

4.  <span data-ttu-id="15882-142">При появлении страницы набора eDiscovery выберите **Создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="15882-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="15882-143">На странице "Создать: набор обнаружения" введите псевдоним пользователя электронной почты в поле **Имя набора обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="15882-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="15882-144">В поле **Фильтр** введите **\* Lync для обнаружения электронных** данных и нажмите кнопку **Добавить & Управление источниками**.</span><span class="sxs-lookup"><span data-stu-id="15882-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="15882-p112">На странице "Добавление источников и управление ими" введите псевдоним электронной почты в текстовом поле в разделе **Почтовые ящики**. Щелкните на значке почтового ящика рядом со учебником для проверки связи SharePoint с указанным почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="15882-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="15882-147">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="15882-147">Click **OK**.</span></span>

8.  <span data-ttu-id="15882-148">На странице набора eDiscovery нажмите кнопку **Сохранить** для сохранения нового набора eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15882-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="15882-149">На этом этапе вы можете выполнить поиск по указанному почтовому ящику (кенмер) и (или) разрешать на месте, так же, как и в случае с другим контентом или источником результатов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="15882-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


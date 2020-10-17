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
ms.openlocfilehash: 7d831638cf25df4f9c1b792c34815e8bed8c15e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525876"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="216e7-102">Настройка Microsoft SharePoint Server 2013 для поиска архивных данных Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="216e7-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="216e7-103">_**Последнее изменение темы:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="216e7-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="216e7-104">Одним из основных преимуществ хранения сообщений об обмене мгновенными сообщениями и веб-конференций в Microsoft Exchange Server 2013 вместо Microsoft Lync Server 2013 является тот факт, что хранение данных в одном и том же расположении позволяет администраторам использовать одно средство для поиска архивированных данных Exchange и/или архивных данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="216e7-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="216e7-105">Так как все данные хранятся на одном месте (Exchange), все средства, которые могут выполнять поиск архивных данных Exchange, также могут выполнять поиск архивных данных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="216e7-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="216e7-106">Одним из средств, облегчающим Поиск архивных данных, является Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="216e7-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="216e7-107">Если вы хотите использовать SharePoint для поиска данных Lync Server, необходимо сначала выполнить все действия, необходимые для настройки архивации Exchange в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="216e7-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="216e7-108">После успешной интеграции Exchange 2013 и Lync Server 2013 необходимо установить управляемый API веб-служб Exchange версии 2,0 на сервере SharePoint. программу установки для этого API можно скачать в центре загрузки Майкрософт ( [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) ).</span><span class="sxs-lookup"><span data-stu-id="216e7-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="216e7-109">Загруженный файл (EWSManagedAPI.msi) можно сохранить в любую папку на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="216e7-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="216e7-110">По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:</span><span class="sxs-lookup"><span data-stu-id="216e7-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="216e7-111">Чтобы открыть командную строку, нажмите **Пуск**, выберите пункт **Все программы**, **Стандартные**, щелкните правой кнопкой мыши **Командная строка** и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="216e7-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="216e7-112">В командной строке введите команду **cd**, чтобы изменить текущий каталог на папку, в которую сохранен файл EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="216e7-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="216e7-113">Например, если вы сохранили файл в формате C: \\ downloads, введите в командной строке следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="216e7-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="216e7-114">Чтобы установить API введите следующую команду и нажмите ВВОД:</span><span class="sxs-lookup"><span data-stu-id="216e7-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="216e7-115">После установки API выполните сброс IIS. Для этого введите следующую команду и нажмите ВВОД:</span><span class="sxs-lookup"><span data-stu-id="216e7-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="216e7-116">После установки веб-служб Exchange необходимо настроить межсерверную проверку подлинности между SharePoint Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="216e7-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="216e7-117">Для этого сначала откройте командную консоль SharePoint 2013 и выполните следующий набор команд:</span><span class="sxs-lookup"><span data-stu-id="216e7-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="216e7-118">Обязательно используйте универсальный код ресурса (URI) для службы автоопределения.</span><span class="sxs-lookup"><span data-stu-id="216e7-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="216e7-119">Не используйте пример URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 .</span><span class="sxs-lookup"><span data-stu-id="216e7-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="216e7-120">После создания поставщика маркера и настройки службы маркеров выполните указанные ниже команды, заменив URL-адрес сайта SharePoint на пример URL-адреса. http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="216e7-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="216e7-121">Чтобы настроить межсерверную проверку подлинности для Exchange 2013, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и использует путь к папке по умолчанию):</span><span class="sxs-lookup"><span data-stu-id="216e7-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="216e7-122">После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на всех серверах почтовых ящиков Exchange и клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="216e7-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="216e7-123">Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="216e7-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="216e7-124">Эту команду можно выполнить в командной консоли Exchange или в любом другом командном окне.</span><span class="sxs-lookup"><span data-stu-id="216e7-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="216e7-125">Затем выполните команду, аналогичную приведенной ниже, которая дает указанному пользователю (в данном примере kenmyer) право на выполнение обнаружения в Exchange:</span><span class="sxs-lookup"><span data-stu-id="216e7-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="216e7-126">После установки проверки подлинности между серверами Exchange и SharePoint необходимо создать сайт обнаружения электронных данных в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="216e7-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="216e7-127">Для этого выполните указанные ниже команды в командной консоли SharePoint.</span><span class="sxs-lookup"><span data-stu-id="216e7-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="216e7-128">Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.</span><span class="sxs-lookup"><span data-stu-id="216e7-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="216e7-129">После того как новый сайт будет готов, следующим шагом будет настройка Exchange 2013 для работы в качестве источника результатов для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="216e7-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="216e7-130">Это можно сделать, выполнив следующую процедуру на странице центра администрирования SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="216e7-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="216e7-131">На странице Центра администрирования выберите **Управление приложениями-службами**, после чего нажмите **Приложение службы поиска**.</span><span class="sxs-lookup"><span data-stu-id="216e7-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="216e7-132">На странице "Приложение службы поиска: администрирование поиска" выберите **Источники результатов** и нажмите **Создать источник результатов**.</span><span class="sxs-lookup"><span data-stu-id="216e7-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="216e7-133">В области **Новый источник результатов** укажите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="216e7-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="216e7-134">Выберите **Exchange** в качестве **протокола**источника результатов, а затем введите URL-адрес источника веб-служб для сервера Exchange в поле **URL-адрес источника Exchange** .</span><span class="sxs-lookup"><span data-stu-id="216e7-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="216e7-135">Исходный URL-адрес выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="216e7-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="216e7-136">Убедитесь в том, что не выбран пункт **Использовать автоопределение**, и нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="216e7-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="216e7-137">Наконец, создайте новое дело обнаружения электронных данных и новый набор eDiscovery, выполнив следующую процедуру на сайте обнаружения SharePoint (например, https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="216e7-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="216e7-138">На странице "Содержимое сайта" выберите **Создать обращение**.</span><span class="sxs-lookup"><span data-stu-id="216e7-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="216e7-p110">На странице "Содержимое сайта: новый сайт SharePoint" укажите псевдоним электронной почты пользователя (например, **kenmyer**) в поле **Заголовок**, после чего добавьте этот URL-адрес в поле **Адрес веб-сайта**. В результате получаем URL-адрес следующего вида:</span><span class="sxs-lookup"><span data-stu-id="216e7-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="216e7-141">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="216e7-141">Click **Create**.</span></span>

4.  <span data-ttu-id="216e7-142">После того как отобразится страница набора eDiscovery, выберите **создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="216e7-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="216e7-143">На странице "Создать: набор обнаружения" введите псевдоним электронной почты пользователя в поле **Имя набора обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="216e7-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="216e7-144">В поле **Фильтр** введите **Lync \* EDiscovery** и нажмите кнопку **Добавить & управления источниками**.</span><span class="sxs-lookup"><span data-stu-id="216e7-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="216e7-p112">На странице "Добавление и управление источниками" укажите псевдоним электронной почты пользователя в текстовом поле в разделе **Почтовые ящики**. Щелкните значок почтового ящика рядом со значком учебника, чтобы проверить подключение SharePoint к указанному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="216e7-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="216e7-147">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="216e7-147">Click **OK**.</span></span>

8.  <span data-ttu-id="216e7-148">На странице "Набор eDiscovery" нажмите **Сохранить**, чтобы сохранить набор eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="216e7-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="216e7-149">На этом шаге вы можете выполнить поиск в указанном почтовом ящике (kenmyer) и/или включить In-Place хранения аналогично любому другому контенту или источнику результатов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="216e7-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


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
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="b22c9-103">Настройка SharePoint Server для поиска архивных данных Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b22c9-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="b22c9-104">**Сводка:** Настройте SharePoint Server для поиска данных, архивируемых Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b22c9-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="b22c9-105">Одно из основных преимуществ хранения расшифровок мгновенных сообщений и веб-конференций в Exchange Server вместо Skype для бизнеса Server заключается в том, что хранение данных в одном расположении позволяет администраторам использовать одно средство для поиска архивных данных Exchange и/или архивных данных Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b22c9-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="b22c9-106">Так как все данные хранятся в одном месте (Exchange), любое средство, которое может искать архивные данные Exchange, также может искать архивные данные Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b22c9-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="b22c9-107">Одним из средств, упрощая поиск архивных данных, является Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b22c9-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="b22c9-108">Если вы хотите использовать SharePoint для поиска данных Skype для бизнеса Server, сначала необходимо выполнить все действия по настройке архива exchange в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b22c9-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="b22c9-109">После Exchange Server интеграции Skype для бизнеса Server необходимо установить управляемый [API](https://go.microsoft.com/fwlink/p/?LinkId=258305) веб-служб Exchange на сервере SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="b22c9-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="b22c9-110">Загруженный файл (EWSManagedAPI.msi) можно сохранить в любую папку на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b22c9-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="b22c9-111">По завершении загрузки файла выполните следующую процедуру на сервере SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b22c9-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="b22c9-112">Чтобы открыть командную строку, нажмите **Пуск**, выберите пункт **Все программы**, **Стандартные**, щелкните правой кнопкой мыши **Командная строка** и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="b22c9-113">В командной строке введите команду cd, чтобы изменить текущий каталог на папку, в которую сохранен файл EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="b22c9-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="b22c9-114">Например, если файл сохранен в папке C:\Downloads, введите в командном окне следующую команду и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="b22c9-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```console
   cd C:\Downloads
   ```

3. <span data-ttu-id="b22c9-115">Чтобы установить API, введите следующую команду и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="b22c9-115">To install the API, type the following command then press Enter:</span></span>
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="b22c9-116">После установки API сбросить IIS, введя следующую команду и нажав ввод:</span><span class="sxs-lookup"><span data-stu-id="b22c9-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```console
   iisreset
   ```

<span data-ttu-id="b22c9-117">После установки веб-служб Exchange необходимо настроить проверку подлинности "сервер-сервер" между SharePoint Server и Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b22c9-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="b22c9-118">Для этого сначала откройте командную оболочку SharePoint и запустите следующий набор команд:</span><span class="sxs-lookup"><span data-stu-id="b22c9-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="b22c9-119">Обязательно используйте универсальный код ресурса (URI) для службы автоопределения.</span><span class="sxs-lookup"><span data-stu-id="b22c9-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="b22c9-120">Не используйте пример https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 URI.</span><span class="sxs-lookup"><span data-stu-id="b22c9-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="b22c9-121">После создания и настройки службы маркеров запустите эти команды, заменив URL-адрес сайта SharePoint на пример URL-адреса http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="b22c9-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="b22c9-122">Чтобы настроить проверку подлинности "сервер-сервер" для Exchange Server, откройте командную Exchange Server Exchange и запустите команду, аналогичную этой (предполагается, что Exchange установлен на диске C: и использует путь к папке по умолчанию):</span><span class="sxs-lookup"><span data-stu-id="b22c9-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="b22c9-123">После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на всех серверах почтовых ящиков и клиентского доступа Exchange.</span><span class="sxs-lookup"><span data-stu-id="b22c9-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="b22c9-124">Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="b22c9-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="b22c9-125">Эту команду можно выполнить из командной оболочки Exchange или из любого другого командного окна.</span><span class="sxs-lookup"><span data-stu-id="b22c9-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="b22c9-126">Затем запустите команду, аналогичную следующей, которая предоставляет указанному пользователю (в данном примере kenmyer) право на обнаружение в Exchange:</span><span class="sxs-lookup"><span data-stu-id="b22c9-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="b22c9-127">После проверки подлинности "сервер-сервер" между Exchange и SharePoint необходимо создать сайт eDiscovery в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b22c9-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="b22c9-128">Для этого можно использовать команды, аналогичные указанным в командной оболочке SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b22c9-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="b22c9-129">Термин "eDiscovery" используется в качестве краткого варианта для термина "обнаружение электронных данных" и, как правило, относится к процедуре поиска в архивах электронных данных элементов, которые можно "обоснованно вычислить в целях предоставления допустимого доказательства" в суде общей юрисдикции.</span><span class="sxs-lookup"><span data-stu-id="b22c9-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="b22c9-130">Когда новый сайт будет готов, необходимо настроить Exchange Server в качестве источника результатов для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b22c9-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="b22c9-131">Это можно сделать, выполив следующую процедуру на странице центра администрирования SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b22c9-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="b22c9-132">На странице Центра администрирования выберите **Управление приложениями-службами**, после чего нажмите **Приложение службы поиска**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="b22c9-133">На странице "Приложение службы поиска: администрирование поиска" выберите **Источники результатов** и нажмите **Создать источник результатов**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="b22c9-134">В области **Новый источник результатов** укажите имя нового источника результатов (например, **Microsoft Exchange**) в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="b22c9-135">Выберите Exchange в качестве протокола источника результатов, а затем введите URL-адрес источника веб-служб для сервера **Exchange** в поле **"URL-адрес источника Exchange".**</span><span class="sxs-lookup"><span data-stu-id="b22c9-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="b22c9-136">Исходный URL-адрес выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b22c9-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="b22c9-137">Убедитесь в том, что не выбран пункт **Использовать автоопределение**, и нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="b22c9-138">Наконец, создайте новое дело eDiscovery и новый набор eDiscovery, выполнив следующую процедуру на сайте обнаружения SharePoint (например, https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="b22c9-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="b22c9-139">На странице "Содержимое сайта" выберите **Создать обращение**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="b22c9-p110">На странице "Содержимое сайта: новый сайт SharePoint" укажите псевдоним электронной почты пользователя (например, **kenmyer**) в поле **Заголовок**, после чего добавьте этот URL-адрес в поле **Адрес веб-сайта**. В результате получаем URL-адрес следующего вида:</span><span class="sxs-lookup"><span data-stu-id="b22c9-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="b22c9-142">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="b22c9-143">После того как отобразится страница набора eDiscovery, выберите **создать элемент** в разделе **Определить и сохранить: наборы обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="b22c9-144">На странице "Создать: набор обнаружения" введите псевдоним электронной почты пользователя в поле **Имя набора обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="b22c9-145">Введите **eDiscovery \\ Lync** _ в поле *_Filter*\* и нажмите кнопку **"Добавить &amp; источники управления".**</span><span class="sxs-lookup"><span data-stu-id="b22c9-145">Enter **eDiscovery Lync\\** _ in the _ *Filter*\* box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="b22c9-146">На странице "Добавление источников управления" введите псевдоним электронной почты пользователя в первом текстовом ящике &amp; в **области "Почтовые ящики".**</span><span class="sxs-lookup"><span data-stu-id="b22c9-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="b22c9-147">Щелкните значок почтового ящика рядом со значком учебника, чтобы проверить подключение SharePoint к указанному почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="b22c9-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="b22c9-148">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b22c9-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="b22c9-149">На странице "Набор eDiscovery" нажмите **Сохранить**, чтобы сохранить набор eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b22c9-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="b22c9-150">На этом этапе можно искать в указанном почтовом ящике (kenmyer) и/или включить In-Place так же, как для любого другого контента SharePoint или источника результатов.</span><span class="sxs-lookup"><span data-stu-id="b22c9-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  


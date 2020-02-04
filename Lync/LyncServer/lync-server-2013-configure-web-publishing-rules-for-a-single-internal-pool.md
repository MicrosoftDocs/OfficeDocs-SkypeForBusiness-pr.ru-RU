---
title: 'Lync Server 2013: настройка правил веб-публикации для единого внутреннего пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ea798f3d5cefa3b65194eb8afcb6e9b35aaa9c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="72748-102">Настройка правил веб-публикации для единого внутреннего пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72748-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72748-103">_**Тема последнего изменения:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="72748-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="72748-104">Microsoft Forefront Threat Management Gateway 2010 и Internet Information Server Routing (IIS ARR) использует правила веб-публикации для публикации внутренних ресурсов, таких как URL-адрес собрания, для пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="72748-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="72748-105">В дополнение к URL-адресам для виртуальных каталогов необходимо также создать правила публикации для простых URL, URL-адреса LyncDiscover и сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="72748-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="72748-106">Для каждого простого URL-адреса необходимо создать отдельное правило для обратного прокси-сервера, указывающего на этот простой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="72748-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="72748-107">Если вы развертываете мобильность и используете автоматическое обнаружение, вам нужно создать правило публикации для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="72748-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="72748-108">Для автоматического обнаружения также необходимо иметь правила публикации для внешнего URL-адреса служб сервера Lync Server для вашего пула каталогов и внешнего пула.</span><span class="sxs-lookup"><span data-stu-id="72748-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="72748-109">Дополнительные сведения о создании правил веб-публикации для автоматического обнаружения см. [в разделе Настройка обратного прокси-сервера для мобильных устройств в Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="72748-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="72748-110">Чтобы создать правила веб-публикации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="72748-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72748-111">В этой процедуре предполагается, что вы установили стандартный выпуск шлюза Forefront Threat Management Gateway (TMG) 2010 или установили и настроили сервер информационных служб Интернета с помощью расширения маршрутизации запросов приложений (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="72748-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="72748-112">Вы используете либо TMG, либо IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="72748-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="72748-113">Создание правила публикации веб-сервера на компьютере, на котором запущено приложение TMG 2010</span><span class="sxs-lookup"><span data-stu-id="72748-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="72748-114">Нажмите кнопку **Пуск**, выберите пункт **программы**, а затем — **Microsoft FOREFRONT TMG**и выберите **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="72748-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="72748-115">На левой панели разверните узел **ServerName**, щелкните правой кнопкой мыши **политику брандмауэра**, выберите пункт **создать**, а затем — **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="72748-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="72748-116">На странице **Добро пожаловать на новую страницу правила веб-публикации** введите отображаемое имя для правила публикации (например, линксервервебдовнлоадсруле).</span><span class="sxs-lookup"><span data-stu-id="72748-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="72748-117">На странице **Выбор действия правила** выберите пункт **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="72748-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="72748-118">На странице **Тип публикации** выберите **Опубликовать один веб-сайт или подсистему балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="72748-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="72748-119">На странице " **Безопасность подключения сервера** " выберите команду " **использовать SSL" для подключения к опубликованному веб-серверу или ферме серверов**.</span><span class="sxs-lookup"><span data-stu-id="72748-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="72748-120">На странице **Внутренняя публикация** введите полное доменное имя внутренней веб-фермы, в которой размещается содержимое собрания и адресная книга, в поле **внутренний сайт имя** .</span><span class="sxs-lookup"><span data-stu-id="72748-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72748-121">Если внутренний сервер является стандартным сервером выпуска, это полное доменное имя сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72748-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="72748-122">Если внутренний сервер является пулом переднего плана, это полное доменное имя подсистемы балансировки нагрузки для внутренних серверов веб-ферм (VIP).</span><span class="sxs-lookup"><span data-stu-id="72748-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="72748-123">Сервер TMG должен иметь возможность разрешения полного доменного имени на IP-адрес внутреннего веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="72748-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="72748-124">Если сервер TMG не может разрешить полное доменное имя для правильного IP-адреса, вы можете выбрать параметр <STRONG>использовать имя компьютера или IP-адрес для подключения к опубликованному серверу</STRONG>, а затем в поле <STRONG>имя компьютера или</STRONG> <STRONG>IP-адрес</STRONG> введите IP-адрес внутреннего веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="72748-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="72748-125">В этом случае необходимо убедиться, что порт 53 открыт на сервере TMG и что он может подключиться к DNS-серверу, который находится в демилитаризованной зоне.</span><span class="sxs-lookup"><span data-stu-id="72748-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="72748-126">Вы также можете использовать записи в локальном файле hosts, чтобы предоставить разрешение имен.</span><span class="sxs-lookup"><span data-stu-id="72748-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="72748-127">На странице **внутренние сведения о публикации** в поле **путь (необязательно)** введите \*\* / \*\* путь к папке, которую нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="72748-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72748-128">В мастере публикации веб-сайта можно указать только один путь.</span><span class="sxs-lookup"><span data-stu-id="72748-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="72748-129">Дополнительные пути можно добавить, изменив свойства правила.</span><span class="sxs-lookup"><span data-stu-id="72748-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="72748-130">На странице **сведения об общедоступном имени** убедитесь в том, что в разделе **запросы**на получение указано **имя домена** , введите полное доменное имя внешней веб-службы в поле **Public Name** .</span><span class="sxs-lookup"><span data-stu-id="72748-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="72748-131">На странице **выбора веб-прослушивателя** нажмите кнопку **создать** , чтобы открыть мастер создания определения веб-прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="72748-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="72748-132">На странице **Добро пожаловать на страницу мастера создания веб-прослушивателя** введите имя веб-слушателя в поле **имя веб-прослушивателя** (например, линксервервебсерверс).</span><span class="sxs-lookup"><span data-stu-id="72748-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="72748-133">На странице **Безопасность подключения клиента** выберите **требования SSL Secure Connections с клиентами**.</span><span class="sxs-lookup"><span data-stu-id="72748-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="72748-134">На странице **IP-адрес веб-прослушивателя** выберите **внешний**и нажмите кнопку **Выбрать IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="72748-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="72748-135">На странице " **Выбор IP-адреса внешнего прослушивателя** " выберите **указанный IP-адрес на компьютере Forefront TMG в выбранной сети**, выберите соответствующий IP-адрес, а затем нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="72748-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="72748-136">На странице " **SSL Certificates Listener** " выберите **назначение сертификата для каждого IP-адреса**, выберите IP-адрес, связанный с внешним доменным именем, и нажмите кнопку **выбрать сертификат**.</span><span class="sxs-lookup"><span data-stu-id="72748-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="72748-137">На странице " **Выбор сертификата** " выберите сертификат, совпадающий с общедоступными именами, указанными на шаге 9, и нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="72748-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="72748-138">На странице **Параметры проверки подлинности** выберите вариант **без проверки подлинности**.</span><span class="sxs-lookup"><span data-stu-id="72748-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="72748-139">На странице **Параметры единого входа** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="72748-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="72748-140">На странице **Завершение работы мастера веб-прослушивателя** убедитесь, что правильно заданы параметры **веб-прослушивателя** , и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="72748-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="72748-141">На странице **Делегирование проверки подлинности** выберите вариант **без делегирования, но клиент может пройти проверку подлинности напрямую**.</span><span class="sxs-lookup"><span data-stu-id="72748-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="72748-142">На странице **User Set (пользовательский** ) нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="72748-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="72748-143">На странице **завершения мастера создания правила веб-публикации** убедитесь, что параметры правила веб-публикации указаны правильно, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="72748-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="72748-144">В области сведений нажмите кнопку **Применить** , чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="72748-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="72748-145">Создание правила публикации веб-сервера на компьютере с IIS ARR</span><span class="sxs-lookup"><span data-stu-id="72748-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="72748-146">Привяжите сертификат, который будет использоваться для обратного прокси-сервера, к протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72748-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="72748-147">Нажмите кнопку **Пуск**, выберите пункт **программы**, а затем — **Администрирование**, а затем — пункт **Диспетчер информационных служб Интернета (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="72748-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72748-148">Дополнительные сведения, снимки экрана и руководство по развертыванию и настройке служб ARR можно найти в статье NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">с помощью IIS arr в качестве обратного прокси-сервера для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="72748-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="72748-149">Если вы еще не сделали этого, импортируйте сертификат, который будет использоваться для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="72748-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="72748-150">В **диспетчере служб IIS**выберите обратное имя прокси-сервера в левой части консоли.</span><span class="sxs-lookup"><span data-stu-id="72748-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="72748-151">В центре консоли, расположенной в **службах IIS** , найдите пункт **Сертификаты сервера**.</span><span class="sxs-lookup"><span data-stu-id="72748-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="72748-152">Щелкните правой кнопкой мыши **серверные сертификаты** и выберите пункт **открыть компонент**.</span><span class="sxs-lookup"><span data-stu-id="72748-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="72748-153">В правой части консоли щелкните **Импорт...**.</span><span class="sxs-lookup"><span data-stu-id="72748-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="72748-154">Введите путь и имя файла сертификата с расширением либо нажмите кнопку **...**</span><span class="sxs-lookup"><span data-stu-id="72748-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="72748-155">для обзора сертификата.</span><span class="sxs-lookup"><span data-stu-id="72748-155">to browse for the certificate.</span></span> <span data-ttu-id="72748-156">Выберите сертификат и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="72748-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="72748-157">Укажите пароль, используемый для защиты закрытого ключа (если вы назначили пароль при экспорте сертификата и закрытого ключа).</span><span class="sxs-lookup"><span data-stu-id="72748-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="72748-158">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72748-158">Click **OK**.</span></span> <span data-ttu-id="72748-159">Если импорт сертификата прошел успешно, сертификат будет отображаться в центре консоли как запись в **сертификатах сервера**.</span><span class="sxs-lookup"><span data-stu-id="72748-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="72748-160">Назначьте сертификат для использования HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72748-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="72748-161">В левой части консоли выберите **веб-сайт по умолчанию** сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="72748-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="72748-162">В правой части экрана выберите пункт **привязки..**..</span><span class="sxs-lookup"><span data-stu-id="72748-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="72748-163">В диалоговом окне **привязки сайта** нажмите кнопку **Добавить..**..</span><span class="sxs-lookup"><span data-stu-id="72748-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="72748-164">В диалоговом окне **Добавление привязки сайта** в разделе **Тип:** выберите **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="72748-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="72748-165">Выбрав HTTPS, вы сможете выбрать сертификат, который будет использоваться для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72748-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="72748-166">В разделе **SSL-сертификат:** выберите сертификат, который вы импортировали для обратного прокси.</span><span class="sxs-lookup"><span data-stu-id="72748-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="72748-167">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72748-167">Click **OK**.</span></span> <span data-ttu-id="72748-168">Затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="72748-168">Then, click **Close**.</span></span> <span data-ttu-id="72748-169">Теперь сертификат привязан к обратному прокси-серверу для протокола SSL и безопасности транспортного уровня (TLS).</span><span class="sxs-lookup"><span data-stu-id="72748-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72748-170">Если при закрытии диалоговых окон привязки, для которых отсутствуют промежуточные сертификаты, появляется предупреждение, необходимо найти и импортировать сертификат корневого центра сертификации и все промежуточные сертификаты ЦС.</span><span class="sxs-lookup"><span data-stu-id="72748-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="72748-171">Просмотрите инструкции в общедоступном центре сертификации, с которого вы запросили сертификат, и следуйте инструкциям, чтобы запросить и импортировать цепочку сертификатов.</span><span class="sxs-lookup"><span data-stu-id="72748-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="72748-172">Если вы экспортировали сертификат с пограничного сервера, вы можете экспортировать сертификат корневого ЦС и все промежуточные сертификаты ЦС, связанные с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="72748-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="72748-173">Импортируйте сертификат корневого центра сертификации в компьютер (не следует путать с хранилищем пользователей) и промежуточные сертификаты в хранилище промежуточных центров сертификации компьютера.</span><span class="sxs-lookup"><span data-stu-id="72748-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="72748-174">В левой части консоли, расположенной под именем сервера IIS, щелкните правой кнопкой мыши пункт **фермы серверов** и выберите команду **создать ферму сервера..**..</span><span class="sxs-lookup"><span data-stu-id="72748-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72748-175">Если вы не видите узел <STRONG>ферм серверов</STRONG> , вам нужно установить маршрут запросов приложений.</span><span class="sxs-lookup"><span data-stu-id="72748-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="72748-176">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратного прокси-сервера для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="72748-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="72748-177">В диалоговом окне **Создание фермы серверов** в **поле имя фермы серверов**введите имя и фамилию (это может быть понятное имя для целей идентификации) для первого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="72748-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="72748-178">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="72748-178">Click **Next**.</span></span>

6.  <span data-ttu-id="72748-179">В диалоговом окне **Добавление сервера** в **адресе сервера**введите полное доменное имя (FQDN) внешних веб-служб на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="72748-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="72748-180">Имена, которые будут использоваться в качестве примера, такие же, как и в разделе Планирование для обратного прокси-сервера, [сведения о сертификате — обратный прокси-сервер в Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="72748-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="72748-181">При обращении к обратному планированию прокси-сервера `webext.contoso.com`мы будем вводить полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="72748-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="72748-182">Убедитесь, что установлен флажок рядом с параметром "в **сети** ".</span><span class="sxs-lookup"><span data-stu-id="72748-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="72748-183">Нажмите кнопку **Добавить** , чтобы добавить сервер в пул веб-серверов для этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="72748-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="72748-184">Lync Server использует подсистемы балансировки нагрузки оборудования для директоров пула и серверных интерфейсов для трафика HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72748-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="72748-185">При добавлении сервера в ферму серверов IIS ARR вы будете использовать только одно полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="72748-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="72748-186">Полное доменное имя будет сервером или режиссером в конфигурациях серверов без пула или с помощью полного доменного имени настроенного аппаратного балансировщика балансировки нагрузки для пулов серверов.</span><span class="sxs-lookup"><span data-stu-id="72748-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="72748-187">Трафик HTTP и HTTPS поддерживается только в том случае, если вы используете аппаратную подсистему балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="72748-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="72748-188">В диалоговом окне **Добавление сервера** нажмите кнопку **Дополнительные параметры..**..</span><span class="sxs-lookup"><span data-stu-id="72748-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="72748-189">Откроется диалоговое окно, в котором можно задать маршрутизацию запросов приложений для запросов к настроенному полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="72748-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="72748-190">Цель — переопределение порта, используемого при обработке запроса службой IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="72748-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="72748-191">По умолчанию конечный HTTP-порт должен быть определен как 8080.</span><span class="sxs-lookup"><span data-stu-id="72748-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="72748-192">Нажмите кнопку рядом с текущим **хттппорт 80** и установите значение **8080**.</span><span class="sxs-lookup"><span data-stu-id="72748-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="72748-193">Нажмите кнопку рядом с текущим **хттпспорт 443** и установите значение **4443**.</span><span class="sxs-lookup"><span data-stu-id="72748-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="72748-194">Оставьте параметр **веса** в 100.</span><span class="sxs-lookup"><span data-stu-id="72748-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="72748-195">При необходимости вы можете переопределить весовые коэффициенты для определенного правила, когда будет определена базовая статистика.</span><span class="sxs-lookup"><span data-stu-id="72748-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="72748-196">Нажмите кнопку **Готово** , чтобы завершить настройку правила.</span><span class="sxs-lookup"><span data-stu-id="72748-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="72748-197">В диалоговом окне могут появляться правила повторной записи, в которых сообщается о том, что диспетчер IIS может создать правило перезаписи URL-адресов, чтобы автоматически маршрутизировать все входящие запросы на ферму сервера.</span><span class="sxs-lookup"><span data-stu-id="72748-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="72748-198">Нажмите **Да**.</span><span class="sxs-lookup"><span data-stu-id="72748-198">Click **Yes**.</span></span> <span data-ttu-id="72748-199">Вы будете настраивать правила вручную, но при нажатии кнопки Да задается первоначальная настройка...</span><span class="sxs-lookup"><span data-stu-id="72748-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="72748-200">Щелкните имя фермы серверов, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="72748-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="72748-201">В разделе **ферма серверов** в представлении функции IIS Manager дважды щелкните **кэширование**.</span><span class="sxs-lookup"><span data-stu-id="72748-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="72748-202">Снимите флажок **включить кэш на диске**.</span><span class="sxs-lookup"><span data-stu-id="72748-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="72748-203">Щелкните **Apply (применить** ) в правой части экрана.</span><span class="sxs-lookup"><span data-stu-id="72748-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="72748-204">Щелкните имя фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="72748-204">Click the name of the server farm.</span></span> <span data-ttu-id="72748-205">В разделе **ферма серверов** в представлении функции IIS Manager дважды щелкните **прокси-сервер**.</span><span class="sxs-lookup"><span data-stu-id="72748-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="72748-206">На странице Параметры прокси-сервера измените значение для параметра **время ожидания (в секундах)** на значение, подходящее для вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="72748-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="72748-207">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="72748-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72748-208">Значение времени ожидания прокси-сервера — число, которое будет отличаться в зависимости от развертывания до развертывания.</span><span class="sxs-lookup"><span data-stu-id="72748-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="72748-209">Необходимо следить за развертыванием и изменять значение для оптимальной работы клиентов.</span><span class="sxs-lookup"><span data-stu-id="72748-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="72748-210">Вы можете установить значение как минимум 200.</span><span class="sxs-lookup"><span data-stu-id="72748-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="72748-211">Если вы поддерживаете мобильные клиенты Lync в своей среде, необходимо установить для этого параметра значение 960, чтобы разрешить получение push-уведомлений из Office 365 с тайм-аутм, равным 900.</span><span class="sxs-lookup"><span data-stu-id="72748-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="72748-212">Возможно, вам потребуется увеличить время ожидания, чтобы избежать отключения клиента, если значение слишком низкое, либо уменьшить номер, если все подключения через прокси-сервер не отключаются и не удаляются долго после отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="72748-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="72748-213">Наблюдение и структурирование. что обычно является нормальным для вашей среды – единственный способ определить, где именно это значение задано.</span><span class="sxs-lookup"><span data-stu-id="72748-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="72748-214">Щелкните имя фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="72748-214">Click the name of the server farm.</span></span> <span data-ttu-id="72748-215">В разделе **ферма серверов** в представлении функции IIS Manager дважды щелкните **правила маршрутизации**.</span><span class="sxs-lookup"><span data-stu-id="72748-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="72748-216">В диалоговом окне Правила маршрутизации в разделе Маршрутизация снимите флажок включить разгрузку SSL.</span><span class="sxs-lookup"><span data-stu-id="72748-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="72748-217">Если возможность снять флажок недоступна, установите флажок **использовать функцию перезаписи URL-адресов для проверки входящих запросов**.</span><span class="sxs-lookup"><span data-stu-id="72748-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="72748-218">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="72748-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="72748-219">Разгрузка SSL с помощью обратного прокси-сервера не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72748-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="72748-220">Повторите шаги 5-11 для каждого URL-адреса, который должен пройти через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="72748-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="72748-221">Общий список может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72748-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="72748-222">Веб-службы сервера переднего плана внешние: webext.contoso.com (уже настроена первоначальная пошаговая проверка)</span><span class="sxs-lookup"><span data-stu-id="72748-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="72748-223">Веб-службы, внешние для Director: webdirext.contoso.com (необязательно, если режиссер развернут)</span><span class="sxs-lookup"><span data-stu-id="72748-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="72748-224">Простое соответствие URL-адресу: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72748-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="72748-225">URL-адрес простого набора: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72748-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="72748-226">URL-адрес автообнаружения Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72748-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="72748-227">URL-адрес сервера Office Web Apps: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72748-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="72748-228">URL-адрес сервера Office Web Apps будет использовать другой адрес Хттпспорт.</span><span class="sxs-lookup"><span data-stu-id="72748-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="72748-229">На шаге 7 вы определяете <STRONG>хттпспорт</STRONG> как <STRONG>443</STRONG> и <STRONG>хттппорт</STRONG> как порт <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="72748-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="72748-230">Все остальные параметры конфигурации одинаковы.</span><span class="sxs-lookup"><span data-stu-id="72748-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="72748-231">В левой части консоли щелкните имя сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="72748-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="72748-232">В центре консоли найдите **URL-адрес для перезаписи** в **службах IIS**.</span><span class="sxs-lookup"><span data-stu-id="72748-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="72748-233">Дважды щелкните элемент URL-адрес для перезаписи, чтобы открыть конфигурацию правил для перезаписи URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="72748-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="72748-234">Для каждой фермы серверов, созданной на предыдущих шагах, должны отобразиться правила.</span><span class="sxs-lookup"><span data-stu-id="72748-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="72748-235">В противном случае подтвердите, что вы щелкаем по имени **сервера IIS** сразу под узлом **Начальная страница** консоли диспетчера сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="72748-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="72748-236">В диалоговом окне **перезаписи URL-адреса** с использованием webext.contoso.com в качестве примера полное имя правила, которое отображается, — это **arr\_webext.contoso.com\_лоадбаланце\_SSL**.</span><span class="sxs-lookup"><span data-stu-id="72748-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="72748-237">Дважды щелкните правило, чтобы открыть диалоговое окно **Изменение правила для входящих подключений** .</span><span class="sxs-lookup"><span data-stu-id="72748-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="72748-238">Нажмите кнопку **Добавить...**</span><span class="sxs-lookup"><span data-stu-id="72748-238">Click **Add…**</span></span> <span data-ttu-id="72748-239">в диалоговом окне **условия** .</span><span class="sxs-lookup"><span data-stu-id="72748-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="72748-240">В поле " **Добавить** условие **" на входе условия** введите **{\_HTTP Host}**.</span><span class="sxs-lookup"><span data-stu-id="72748-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="72748-241">(По мере ввода появится диалоговое окно, в котором вы сможете выбрать условие).</span><span class="sxs-lookup"><span data-stu-id="72748-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="72748-242">в разделе **Проверка наличия строки ввода:** SELECT **соответствует шаблону**.</span><span class="sxs-lookup"><span data-stu-id="72748-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="72748-243">В **\*** типе **ввода "шаблон** ".</span><span class="sxs-lookup"><span data-stu-id="72748-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="72748-244">Флажок **игнорировать регистр** должен быть установлен.</span><span class="sxs-lookup"><span data-stu-id="72748-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="72748-245">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72748-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="72748-246">Прокрутите страницу вниз в диалоговом окне **Изменение правила для входящих** сообщений, чтобы перейти к диалоговому окну **действия** .</span><span class="sxs-lookup"><span data-stu-id="72748-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="72748-247">**Тип действия:** должен быть настроен для **маршрутизации на ферму сервера**, **Схема:** установлен на **https://**, **ферму сервера:** укажите URL-адрес, к которому применяется данное правило.</span><span class="sxs-lookup"><span data-stu-id="72748-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="72748-248">В этом примере для этого примера должно быть установлено значение **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="72748-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="72748-249">**Путь:** задано значение **/{р: 0}**</span><span class="sxs-lookup"><span data-stu-id="72748-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="72748-250">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="72748-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="72748-251">Нажмите кнопку **назад,** чтобы вернуться к разделу правила для перезаписи URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="72748-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="72748-252">Повторите процедуру, определенную на шаге 14, для каждого определенного правила повторной записи SSL, для каждого из которых указан URL-адрес фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="72748-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="72748-253">По умолчанию правила HTTP также создаются и обозначаются аналогичным именованию правил SSL.</span><span class="sxs-lookup"><span data-stu-id="72748-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="72748-254">Для нашего текущего примера правило HTTP будет называться <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="72748-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="72748-255">Эти правила не требуют никаких изменений, и их можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="72748-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="72748-256">Изменение свойств правила веб-публикации в TMG 2010</span><span class="sxs-lookup"><span data-stu-id="72748-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="72748-257">Нажмите кнопку **Пуск**, наведите указатель мыши на пункт **программы**, выберите **Microsoft FOREFRONT TMG**и щелкните **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="72748-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="72748-258">На левой панели разверните узел **ServerName**и выберите пункт **Политика брандмауэра**.</span><span class="sxs-lookup"><span data-stu-id="72748-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="72748-259">В области сведений щелкните правой кнопкой мыши правило публикации веб-сервера, созданное в предыдущей процедуре (например, Линксерверекстерналруле), и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="72748-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="72748-260">На странице " **Свойства** " на вкладке " **от** " выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="72748-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="72748-261">В **этом правиле применяется к трафику из списка источников** , выберите в **любом месте**и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="72748-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="72748-262">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="72748-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="72748-263">В диалоговом окне **Добавление сетевых объектов**разверните элемент **сети**, выберите элемент **Внешние**, нажмите кнопку **Добавить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="72748-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="72748-264">На вкладке " **на** " убедитесь, что **вместо фактического установлен флажок переадресовать первоначальный заголовок узла** .</span><span class="sxs-lookup"><span data-stu-id="72748-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="72748-265">На вкладке **мост** установите флажок **перенаправить на порт SSL** и укажите порт **4443**.</span><span class="sxs-lookup"><span data-stu-id="72748-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="72748-266">На вкладке **общедоступное имя** добавьте простые URL-адреса (например, meet.contoso.com и Dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="72748-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="72748-267">Нажмите кнопку **Применить** , чтобы сохранить изменения, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="72748-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="72748-268">В области сведений нажмите кнопку **Применить** , чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="72748-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="72748-269">Изменение свойств правила веб-публикации в службах IIS ARR</span><span class="sxs-lookup"><span data-stu-id="72748-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="72748-270">Нажмите кнопку **Пуск**, выберите пункт **программы**, а затем — **Администрирование**, а затем — пункт **Диспетчер информационных служб Интернета (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="72748-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="72748-271">В левой части консоли щелкните имя сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="72748-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="72748-272">В центре консоли найдите **URL-адрес для перезаписи** в **службах IIS**.</span><span class="sxs-lookup"><span data-stu-id="72748-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="72748-273">Дважды щелкните элемент URL-адрес для перезаписи, чтобы открыть конфигурацию правил для перезаписи URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="72748-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="72748-274">Дважды щелкните правило, которое необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="72748-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="72748-275">Внесите необходимые изменения в **соответствии с URL-адресом**, **условиями**, **серверными переменными** или **действием**.</span><span class="sxs-lookup"><span data-stu-id="72748-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="72748-276">Нажмите кнопку **Применить** , чтобы зафиксировать изменения.</span><span class="sxs-lookup"><span data-stu-id="72748-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="72748-277">Нажмите кнопку " **назад к правилам** ", чтобы изменить другие правила, или закройте консоль **диспетчера IIS** , если вы закончите вносить изменения.</span><span class="sxs-lookup"><span data-stu-id="72748-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


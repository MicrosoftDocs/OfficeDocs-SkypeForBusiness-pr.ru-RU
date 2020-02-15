---
title: 'Lync Server 2013: Настройка правил веб-публикации для отдельного внутреннего пула'
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
ms.openlocfilehash: 8d87e0096ee71fb08da396188d419e918f66e125
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="3a1e4-102">Настройка правил веб-публикации для отдельного внутреннего пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a1e4-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a1e4-103">_**Последнее изменение темы:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="3a1e4-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="3a1e4-104">Microsoft Forefront Threat Management Gateway 2010 и Internet Information Server Routing Server (IIS ARR) использует правила веб-публикации для публикации внутренних ресурсов, таких как URL-адрес собрания, пользователям в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="3a1e4-105">Помимо URL-адресов веб-служб для виртуальных каталогов, необходимо также создать правила публикации для простых URL-адресов, URL-адреса LyncDiscover и сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="3a1e4-106">Для каждого простого URL-адреса необходимо создать отдельное правило на обратном прокси-сервере, указывающее на этот адрес.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="3a1e4-107">Если вы развертываете службу мобильности и используете автоматическое обнаружение, вам необходимо создать правило публикации для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="3a1e4-108">Для автоматического обнаружения также необходимы правила публикации для внешнего URL-адреса веб-служб Lync Server для пула директоров и интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="3a1e4-109">Дополнительные сведения о создании правил веб-публикации для автоматического обнаружения приведены [в статье Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="3a1e4-110">Чтобы создать правила веб-публикации, используйте следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a1e4-111">В этих процедурах предполагается, что вы установили стандартный выпуск Forefront Threat Management Gateway (TMG) 2010 или установили и настроили сервер Internet Information Server с расширением маршрутизации запросов приложений (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="3a1e4-112">Вы используете либо TMG, либо IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="3a1e4-113">Создание правила публикации веб-сервера на компьютере с TMG 2010</span><span class="sxs-lookup"><span data-stu-id="3a1e4-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="3a1e4-114">В меню **Пуск** последовательно выберите пункты **Программы**, **Microsoft Forefront TMG** и **Управление Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="3a1e4-115">В области слева разверните узел **Имя сервера**, щелкните правой кнопкой мыши пункт **Политика брандмауэра**, выберите пункт **Создать** и щелкните **Правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="3a1e4-116">На странице **Новое правило веб-публикации** введите отображаемое имя правила публикации (например, LyncServerWebDownloadsRule).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="3a1e4-117">На странице **Выбрать действие правила** выберите пункт **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="3a1e4-118">На странице **Тип публикации** выберите пункт **Опубликовать один веб-сайт или систему балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="3a1e4-119">На странице **Безопасность подключения к серверу** выберите пункт **Использовать SSL для подключения к опубликованному веб-серверу или ферме серверов**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="3a1e4-120">На странице **Внутренние сведения публикации** в поле **Внутреннее имя сайта** введите полное доменное имя внутренней веб-фермы, в которой размещается содержимое собраний и адресной книги.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a1e4-121">Если внутренний сервер представляет собой сервер Standard Edition, необходимо ввести его полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="3a1e4-122">Если внутренний сервер является интерфейсным пулом, в качестве полного доменного имени следует указать виртуальный IP-адрес аппаратного балансировщика нагрузки, который распределяет нагрузку на веб-серверы внутренней фермы.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="3a1e4-123">Сервер TMG должен иметь возможность разрешать полное доменное имя в IP-адрес внутреннего веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="3a1e4-124">Если сервер TMG не может разрешить полное доменное имя по правильному IP-адресу, можно выбрать параметр <STRONG>использовать имя компьютера или IP-адрес для подключения к опубликованному серверу</STRONG>, а затем в поле <STRONG>имя компьютера или</STRONG> <STRONG>IP-адрес</STRONG> введите IP-адрес внутреннего веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="3a1e4-125">В этом случае следует убедиться в том, что на сервере TMG открыт порт 53 и что этот сервер может связаться с сервером DNS, находящимся в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="3a1e4-126">Вы также можете обеспечить разрешение имен с помощью записей в файле локальных узлов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="3a1e4-127">На странице **внутренние сведения публикации** в поле **путь (необязательно)** введите \*\* / \*\* путь к папке, которую нужно опубликовать.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a1e4-p105">В мастере публикации веб-сайта можно указать только один путь. Дополнительные пути можно добавить путем изменения свойств правила.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="3a1e4-130">На странице **Параметры внешнего имени** убедитесь в том, что в разделе **Принимать запросы для** выбран пункт **Это имя домена**, и введите полное доменное имя внешних веб-служб в поле **Внешнее имя**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="3a1e4-131">На странице **Выбрать веб-прослушиватель** нажмите кнопку **Создать**, чтобы открыть мастер определения нового веб-прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="3a1e4-132">На странице **Мастер создания веб-прослушивателя** в поле **Имя веб-прослушивателя** введите имя веб-прослушивателя (например, LyncServerWebServers).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="3a1e4-133">На странице **Безопасность клиентских подключений** выберите пункт **Требовать безопасного подключения SSL для клиентов**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="3a1e4-134">На странице **IP-адрес веб-прослушивателя** выберите пункт **Внешний** и нажмите кнопку **Выбрать IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="3a1e4-135">На странице **Выбор внешнего IP-адреса прослушивателя** выберите пункт **Указанный IP-адрес на компьютере Forefront TMG в выбранной сети**, выберите нужный IP-адрес и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="3a1e4-136">На странице **SSL-сертификаты прослушивателя** выберите пункт **Назначить сертификат для каждого IP-адреса**, выберите IP-адрес, связанный с полным доменным именем внешнего веб-сервера, и нажмите кнопку **Выбрать сертификат**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="3a1e4-137">На странице **Выбор сертификата** выберите сертификат, который соответствует внешним именам, указанным в шаге 9, и нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="3a1e4-138">На странице **Параметр проверки подлинности** выберите пункт **Без проверки подлинности**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="3a1e4-139">На странице **Параметр единого входа** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="3a1e4-140">На странице **Завершение работы мастера определения веб-прослушивателя** проверьте, верны ли параметры **веб-прослушивателя**, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="3a1e4-141">На странице **Делегирование проверки подлинности** выберите пункт **Без делегирования, но клиент может выполнять проверку подлинности напрямую**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="3a1e4-142">На странице **Набор учетных записей** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="3a1e4-143">На странице **Завершение работы мастера создания правила веб-публикации** проверьте, верны ли параметры правила веб-публикации, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="3a1e4-144">В области сведений нажмите кнопку **Применить**, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="3a1e4-145">Создание правила публикации веб-сервера на компьютере, на котором выполняется служба IIS ARR</span><span class="sxs-lookup"><span data-stu-id="3a1e4-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="3a1e4-146">Привяжите сертификат, который будет использоваться для обратного прокси-сервера, к протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="3a1e4-147">Нажмите кнопку **Пуск**, выберите пункт **программы**, **Администрирование**, а затем щелкните **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a1e4-148">Дополнительная справка, снимки экрана и рекомендации по развертыванию и настройке службы IIS ARR можно найти в статье NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">с использованием IIS arr в качестве обратного прокси-сервера для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="3a1e4-149">Если вы еще не сделали это, импортируйте сертификат, который будет использоваться для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="3a1e4-150">В **диспетчере служб IIS**щелкните имя обратного прокси-сервера в левой части консоли.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="3a1e4-151">В центре консоли в **службах IIS** найдите пункт **Сертификаты сервера**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="3a1e4-152">Щелкните правой кнопкой мыши пункт **Сертификаты сервера** и выберите пункт **открыть компонент**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="3a1e4-153">В правой части консоли щелкните **Импорт...**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="3a1e4-154">Введите путь и имя файла сертификата с расширением или нажмите кнопку **...**</span><span class="sxs-lookup"><span data-stu-id="3a1e4-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="3a1e4-155">, чтобы найти сертификат.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-155">to browse for the certificate.</span></span> <span data-ttu-id="3a1e4-156">Выберите сертификат и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="3a1e4-157">Укажите пароль, используемый для защиты закрытого ключа (если вы назначили пароль при экспорте сертификата и закрытого ключа).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="3a1e4-158">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-158">Click **OK**.</span></span> <span data-ttu-id="3a1e4-159">Если импорт сертификата был успешным, сертификат будет отображаться в качестве записи в середине консоли как запись в **сертификатах сервера**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="3a1e4-160">Назначьте сертификат для использования протоколом HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="3a1e4-161">В левой части консоли выберите **веб-сайт по умолчанию** сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="3a1e4-162">В правой части нажмите кнопку **привязки...**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="3a1e4-163">В диалоговом окне **привязки сайта** нажмите кнопку **Добавить..**..</span><span class="sxs-lookup"><span data-stu-id="3a1e4-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="3a1e4-164">В диалоговом окне **Добавление привязки сайта** в разделе **Тип:** выберите **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="3a1e4-165">Выбор протокола HTTPS позволяет выбрать сертификат, который будет использоваться для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="3a1e4-166">В разделе **SSL-сертификат:** выберите сертификат, импортированный для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="3a1e4-167">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-167">Click **OK**.</span></span> <span data-ttu-id="3a1e4-168">Затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-168">Then, click **Close**.</span></span> <span data-ttu-id="3a1e4-169">Теперь сертификат связан с обратным прокси-сервером для протокола SSL и протоколом TLS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3a1e4-170">Если при закрытии диалоговых окон привязки, которые отсутствуют в промежуточных сертификатах, отображается предупреждение, необходимо найти и импортировать сертификат корневого центра сертификации и сертификаты промежуточного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="3a1e4-171">Ознакомьтесь с инструкциями в общедоступном центре сертификации, с которого вы запросили сертификат, и следуйте инструкциям по запросу и импорту цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="3a1e4-172">Если вы экспортировали сертификат с пограничного сервера, вы можете экспортировать сертификат корневого центра сертификации и все сертификаты промежуточного ЦС, связанные с пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="3a1e4-173">Импортируйте сертификат корневого центра сертификации в компьютер (не следует путать с хранилищем доверенных корневых центров сертификации и промежуточными сертификатами в промежуточном хранилище центров сертификации компьютера).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="3a1e4-174">В левой части консоли под именем сервера IIS щелкните правой кнопкой **фермы серверов** и выберите команду **создать ферму сервера..**..</span><span class="sxs-lookup"><span data-stu-id="3a1e4-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a1e4-175">Если узел <STRONG>фермы серверов</STRONG> не отображается, необходимо установить маршрутизацию запросов приложений.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="3a1e4-176">Дополнительные сведения см. в статье <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="3a1e4-177">В диалоговом окне **Создание фермы серверов** в **поле имя фермы серверов**введите имя (это может быть понятное имя для целей идентификации) для первого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="3a1e4-178">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-178">Click **Next**.</span></span>

6.  <span data-ttu-id="3a1e4-179">В диалоговом окне **Добавление сервера** в поле **адрес сервера**введите полное доменное имя (FQDN) внешних веб-служб на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="3a1e4-180">Имена, которые будут использоваться в качестве примера для примера, совпадают с используемыми в разделе Планирование для обратного прокси-сервера, [Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="3a1e4-181">При обращении к обратному планированию прокси-сервера `webext.contoso.com`необходимо ввести полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="3a1e4-182">Убедитесь, что установлен флажок рядом с параметром **Online** .</span><span class="sxs-lookup"><span data-stu-id="3a1e4-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="3a1e4-183">Нажмите кнопку **Добавить** , чтобы добавить сервер в пул веб-серверов для этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3a1e4-184">Lync Server использует аппаратные средства балансировки нагрузки для директоров пула и серверов переднего плана для трафика HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="3a1e4-185">При добавлении сервера в ферму серверов IIS ARR вы будете предоставлять только одно полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="3a1e4-186">Полное доменное имя будет сервером переднего плана или режиссером в конфигурациях серверов без пула или полным доменным именем настроенного аппаратного балансировщика нагрузки для пулов серверов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="3a1e4-187">Единственным поддерживаемым методом для балансировки нагрузки на трафик HTTP и HTTPS является использование аппаратных подсистем балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="3a1e4-188">В диалоговом окне **Добавление сервера** нажмите **Дополнительные параметры..**..</span><span class="sxs-lookup"><span data-stu-id="3a1e4-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="3a1e4-189">Откроется диалоговое окно для определения маршрутизации запросов приложений для запросов к настроенному полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="3a1e4-190">Цель состоит в том, чтобы переопределить порт, используемый при обработке запроса службой IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="3a1e4-191">По умолчанию конечный HTTP-порт должен быть определен как 8080.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="3a1e4-192">Нажмите кнопку Далее рядом с текущим **httpPort 80** и установите значение **8080**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="3a1e4-193">Нажмите кнопку Далее рядом с текущим **хттпспорт 443** и установите значение **4443**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="3a1e4-194">Оставьте значение параметра **Weight** равное 100.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="3a1e4-195">При необходимости вы можете переопределить весовые коэффициенты для данного правила, когда у вас будет базовая статистика.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="3a1e4-196">Нажмите кнопку **Готово** , чтобы завершить эту часть конфигурации правила.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="3a1e4-197">В диалоговом окне могут отображаться правила перезаписи, которые информирует вас о том, что диспетчер IIS может создать правило перезаписи URL-адресов, чтобы автоматически маршрутизировать все входящие запросы на ферму серверов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="3a1e4-198">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-198">Click **Yes**.</span></span> <span data-ttu-id="3a1e4-199">Правила будут настраиваться вручную, но при нажатии кнопки Да задается начальная конфигурация...</span><span class="sxs-lookup"><span data-stu-id="3a1e4-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="3a1e4-200">Щелкните имя только что созданной фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="3a1e4-201">В разделе **ферма серверов** в представлении функций диспетчера IIS дважды щелкните **кэширование**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="3a1e4-202">Снимите флажок **включить кэш диска**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="3a1e4-203">Нажмите кнопку **Применить** на правой стороне.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="3a1e4-204">Щелкните имя фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-204">Click the name of the server farm.</span></span> <span data-ttu-id="3a1e4-205">В разделе **ферма серверов** в представлении функций диспетчера IIS дважды щелкните **прокси-сервер**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="3a1e4-206">На странице "Параметры прокси-сервера" измените значение для параметра **время ожидания (в секундах)** на значение, соответствующее вашему развертыванию.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="3a1e4-207">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3a1e4-208">Значение времени ожидания прокси-сервера — это число, которое будет отличаться от развертывания до развертывания.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="3a1e4-209">Необходимо следить за развертыванием и изменять значение для лучшего взаимодействия с клиентами.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="3a1e4-210">Вы можете задать значение, равное 200.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="3a1e4-211">Если вы поддерживаете мобильные клиенты Lync в вашей среде, установите для этого параметра значение 960, чтобы разрешить время ожидания push-уведомлений от Office 365, у которых значение времени ожидания равно 900.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="3a1e4-212">Очень вероятно, что вам потребуется увеличить значение времени ожидания, чтобы избежать отключения клиента, когда значение слишком мало или не будет превышать число подключений через прокси-сервер, а затем очистить после отключения клиента.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="3a1e4-213">Наблюдение и структурирование для базовой среды — единственный способ определить, где именно это значение подходит для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="3a1e4-214">Щелкните имя фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-214">Click the name of the server farm.</span></span> <span data-ttu-id="3a1e4-215">В разделе **ферма серверов** в представлении функций диспетчера IIS дважды щелкните **правила маршрутизации**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="3a1e4-216">В диалоговом окне Правила маршрутизации в разделе Маршрутизация снимите флажок включить разгрузку SSL.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="3a1e4-217">Если возможность снять флажок недоступна, установите флажок **использовать переопределение URL-адресов для проверки входящих запросов**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="3a1e4-218">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3a1e4-219">Разгрузка SSL с помощью обратного прокси-сервера не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="3a1e4-220">Повторите шаги 5-11 для каждого URL-адреса, который должен пройти через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="3a1e4-221">Общий список будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a1e4-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="3a1e4-222">Внешние веб-службы сервера переднего плана: webext.contoso.com (уже настроено с помощью начального прохода)</span><span class="sxs-lookup"><span data-stu-id="3a1e4-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="3a1e4-223">Внешние веб-службы Director для директора: webdirext.contoso.com (необязательно, если директор развернут)</span><span class="sxs-lookup"><span data-stu-id="3a1e4-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="3a1e4-224">Соответствие простым URL-адресом: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a1e4-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="3a1e4-225">Набор простых URL-адресов: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a1e4-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="3a1e4-226">URL-адрес автообнаружения Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a1e4-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="3a1e4-227">URL-адрес сервера Office Web Apps: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a1e4-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="3a1e4-228">URL-адрес для сервера Office Web Apps будет использовать другой адрес Хттпспорт.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="3a1e4-229">В шаге 7 Определите <STRONG>хттпспорт</STRONG> как <STRONG>443</STRONG> и <STRONG>httpPort</STRONG> в качестве порта <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="3a1e4-230">Все остальные параметры конфигурации одинаковы.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="3a1e4-231">В левой части консоли щелкните имя сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="3a1e4-232">В центре консоли найдите параметр **Перезапись URL-адресов** в **службах IIS**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="3a1e4-233">Дважды щелкните элемент URL-адрес для перезаписи, чтобы открыть конфигурацию правил перезаписи URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="3a1e4-234">Должны отобразиться правила для каждой фермы серверов, созданной на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="3a1e4-235">В противном случае подтвердите, что вы щелкните имя **сервера IIS** сразу под узлом **начальной страницы** в консоли диспетчера сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="3a1e4-236">В диалоговом окне **перезаписи URL-адреса** с использованием webext.contoso.com в качестве примера полное имя правила, как отображается, **—\_arr\_webext.contoso.com\_лоадбаланце SSL**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="3a1e4-237">Дважды щелкните правило, чтобы открыть диалоговое окно **Изменение правила для входящих подключений** .</span><span class="sxs-lookup"><span data-stu-id="3a1e4-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="3a1e4-238">Нажмите кнопку **Добавить...**</span><span class="sxs-lookup"><span data-stu-id="3a1e4-238">Click **Add…**</span></span> <span data-ttu-id="3a1e4-239">в диалоговом окне " **условия** ".</span><span class="sxs-lookup"><span data-stu-id="3a1e4-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="3a1e4-240">В поле **Добавить условие** при **входе условия:** введите **{HTTP\_Host}**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="3a1e4-241">(При вводе будет открыто диалоговое окно, в котором можно выбрать условие).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="3a1e4-242">в разделе **проверить, если входная строка:** SELECT **соответствует шаблону**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="3a1e4-243">В **\*** типе **входных данных шаблона** .</span><span class="sxs-lookup"><span data-stu-id="3a1e4-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="3a1e4-244">Флажок **игнорировать регистр** должен быть установлен.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="3a1e4-245">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="3a1e4-246">Прокрутите вниз в диалоговом окне **Изменение правила для входящих подключений** , чтобы перейти к диалоговому окну **действие** .</span><span class="sxs-lookup"><span data-stu-id="3a1e4-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="3a1e4-247">**Тип действия:** должен быть установлен для **маршрутизации к ферме серверов**, **схема:** задано значение **https://**, **ферма серверов:** указать URL-адрес, к которому применяется это правило.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="3a1e4-248">В этом примере должно быть задано значение **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="3a1e4-249">**Путь:** задано значение **/{р: 0}**</span><span class="sxs-lookup"><span data-stu-id="3a1e4-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="3a1e4-250">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="3a1e4-251">Нажмите кнопку **назад,** чтобы вернуться к правилам перезаписи URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="3a1e4-252">Повторите процедуру, описанную в шаге 14, для каждого определенного правила перезаписи SSL, по одному URL-адресу фермы серверов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3a1e4-253">По умолчанию правила HTTP также создаются и обозначаются похожим именем для правил SSL.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="3a1e4-254">Для нашего текущего примера правило HTTP будет называться <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="3a1e4-255">Эти правила не требуют изменений, и их можно спокойно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="3a1e4-256">Изменение свойств правила веб-публикации в TMG 2010</span><span class="sxs-lookup"><span data-stu-id="3a1e4-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="3a1e4-257">Нажмите кнопку **Пуск**, последовательно выберите пункты **программы**, **Microsoft FOREFRONT TMG**и **Управление Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="3a1e4-258">В области слева разверните узел **Имя сервера** и щелкните пункт **Политика брандмауэра**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="3a1e4-259">В области сведений щелкните правой кнопкой мыши созданное ранее правило публикации веб-сервера (например, LyncServerExternalRule) и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="3a1e4-260">На странице **Свойства** на вкладке **Откуда** сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="3a1e4-261">В списке **Это правило применяется к трафику от следующих источников** выберите пункт **Везде** и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="3a1e4-262">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="3a1e4-263">На странице **Добавление сетевых сущностей** разверните узел **Сети**, щелкните **Внешние**, нажмите кнопку **Добавить**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="3a1e4-264">На вкладке **Куда** убедитесь в том, что установлен флажок **Пересылать исходный заголовок узла вместо действительного**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="3a1e4-265">На вкладке **Использование моста** установите флажок **Пересылать запрос на порт SSL** и укажите порт **4443**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="3a1e4-266">На вкладке **Внешнее имя** добавьте простые URL-адреса (например, meet.contoso.com и dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3a1e4-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="3a1e4-267">Нажмите кнопку **Применить**, чтобы сохранить изменения, после чего нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="3a1e4-268">В области сведений нажмите кнопку **Применить**, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="3a1e4-269">Изменение свойств правила веб-публикации в службах IIS ARR</span><span class="sxs-lookup"><span data-stu-id="3a1e4-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="3a1e4-270">Нажмите кнопку **Пуск**, выберите пункт **программы**, **Администрирование**, а затем щелкните **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="3a1e4-271">В левой части консоли щелкните имя сервера IIS.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="3a1e4-272">В центре консоли найдите параметр **Перезапись URL-адресов** в **службах IIS**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="3a1e4-273">Дважды щелкните элемент URL-адрес для перезаписи, чтобы открыть конфигурацию правил перезаписи URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="3a1e4-274">Дважды щелкните правило, которое необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="3a1e4-275">Внесите необходимые изменения в **соответствии с URL-адресом**, **условиями**, **серверными переменными** или **действием**.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="3a1e4-276">Нажмите кнопку **Применить** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="3a1e4-277">Нажмите кнопку **назад, чтобы** изменить другие правила, или закройте консоль **диспетчера IIS** , если вы закончите внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="3a1e4-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


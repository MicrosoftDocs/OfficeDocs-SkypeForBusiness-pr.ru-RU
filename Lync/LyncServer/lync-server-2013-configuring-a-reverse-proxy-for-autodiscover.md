---
title: 'Lync Server 2013: Настройка обратного прокси для автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5445a9ce81835863b610ef32ecc51ccac5331c3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d5ca5-102">Настройка обратного прокси-сервера для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5ca5-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5ca5-103">_**Тема последнего изменения:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="d5ca5-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="d5ca5-104">Служба автообнаружения и поддержка для клиентов, использующих функцию автообнаружения, требуют изменения существующего правила веб-публикации или создания нового правила веб-публикации для обратного прокси.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="d5ca5-105">Изменение или создание нового правила публикации не зависит от того, какое решение требуется обновить или не следует обновлять списки альтернативных имен субъектов в сертификатах обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="d5ca5-106">Если вы решили использовать HTTPS для первоначальных запросов службы автообнаружения Lync Server 2013 и обновите списки альтернативных имен для субъектов в обратных сертификатах прокси-сервера, вам нужно назначить обновленный общедоступный сертификат для прослушивания SSL (Secure Sockets Layer) на обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="d5ca5-107">Требуемое обновление для внешнего (общего) сертификата будет включать запись в поле "альтернативное имя субъекта (SAN)" для lyncdiscover. \<доменное\>имя.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="d5ca5-108">Затем необходимо изменить существующий прослушиватель для внешних веб-служб или создать новое правило веб-публикации для внешнего URL-адреса службы автообнаружения (например, **lyncdiscover.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="d5ca5-109">Если у вас еще нет правила веб-публикации для внешнего URL-адреса внешней службы Lync Server 2013 для своего пула и пула (если вы разработали директоры), вам также потребуется опубликовать правило для этого.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5ca5-110">Правила и прослушиватель обратной публикации прокси-сервера могут обслуживать как внешние веб-службы, так и службу автообнаружения, если сертификат, назначенный прослушивателю, включает в себя необходимые имя субъекта и альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="d5ca5-111">Подробнее о конфигурации веб-прослушивателей и правил публикации по умолчанию можно найти в разделе <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратного прокси-серверов для Lync Server 2013</A> для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="d5ca5-112">Если вы решили использовать HTTP для первоначальных запросов на обслуживание автообнаружения, так что вам не нужно обновлять альтернативные имена субъектов для обратного прокси-сервера, вам нужно создать или изменить правило веб-публикации для порта 80.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="d5ca5-113">В этой статье описано, как создавать и изменять правила веб-публикации в Microsoft Forefront Threat Management Gateway 2010 для автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5ca5-114">В этой процедуре предполагается, что вы установили стандартный выпуск шлюза Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-114">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="d5ca5-115">Если вы используете другой обратный прокси-сервер, процедуры будут похожи, но необходимо будет сопоставлены с документацией для стороннего продукта.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-115">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="d5ca5-116">Создание правила веб-публикации для внешнего URL-адреса службы автообнаружения</span><span class="sxs-lookup"><span data-stu-id="d5ca5-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="d5ca5-117">Нажмите кнопку **Пуск**, наведите указатель мыши на пункт **программы**, выберите **Microsoft FOREFRONT TMG**и щелкните **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d5ca5-118">На левой панели разверните узел **ServerName**, щелкните **политику брандмауэра**правой кнопкой мыши, наведите указатель на пункт **создать**и выберите **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d5ca5-119">На странице **Добро пожаловать на новую страницу правила веб-публикации** введите отображаемое имя для нового правила публикации (например, линкдисковерюрл).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="d5ca5-120">На странице **Выбор действия правила** выберите пункт **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="d5ca5-121">На странице **Тип публикации** выберите **Опубликовать один веб-сайт или подсистему балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="d5ca5-122">На странице " **Безопасность подключения сервера** " выберите команду " **использовать SSL" для подключения к опубликованному веб-серверу или ферме серверов**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="d5ca5-123">На странице **Внутренняя публикация подробных сведений** в поле **имя внутреннего сайта**введите полное доменное имя (FQDN) своего пула (например, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="d5ca5-124">Если вы создаете правило для URL-адреса внешней веб-службы в пуле переднего плана, введите полное доменное имя пула переднего плана (например, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="d5ca5-125">На странице **Внутренняя публикация подробных сведений** в поле **путь**введите \*\* / \*\* путь к папке, которую нужно опубликовать, а затем выберите пункт переадресовать **исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="d5ca5-126">На странице **сведения об общедоступном имени** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="d5ca5-127">В разделе **запросы на**получение выберите **это доменное имя**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="d5ca5-128">В **общедоступном имени**введите **lyncdiscover.** \<сипдомаин\> (внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="d5ca5-129">Если вы создаете правило для URL-адреса внешней веб-службы в пуле переднего плана, введите полное доменное имя для внешних веб-служб в пуле переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="d5ca5-130">В списке **путь**введите \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="d5ca5-131">На странице " **Выбор веб-прослушивателя** " в **веб-прослушивателе**выберите существующий прослушиватель SSL с обновленным общедоступным сертификатом.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="d5ca5-132">На странице **Делегирование проверки** подлинности выберите вариант **без делегирования, но клиент может пройти проверку подлинности напрямую**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="d5ca5-133">На странице **User Set (пользовательский** ) выберите " **все пользователи**".</span><span class="sxs-lookup"><span data-stu-id="d5ca5-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="d5ca5-134">На странице **завершения мастера создания правила веб-публикации** убедитесь, что параметры правила веб-публикации указаны правильно, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="d5ca5-135">В списке правил веб-публикации Forefront TMG дважды щелкните новое правило, которое вы только что добавили, чтобы открыть **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="d5ca5-136">На вкладке **на** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="d5ca5-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="d5ca5-137">Выберите **переадресовать первоначальный заголовок узла вместо фактического**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="d5ca5-138">**Запросы на выборку будут приходить с компьютера FOREFRONT TMG**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="d5ca5-139">На вкладке **мосты** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d5ca5-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="d5ca5-140">Выберите **веб-сервер**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="d5ca5-141">Выберите параметр **перенаправлять запросы на HTTP-порт**и введите **8080** для номера порта.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="d5ca5-142">Выберите параметр перенаправить **запросы на порт SSL**и введите **4443** для номера порта.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="d5ca5-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-143">Click **OK**.</span></span>

18. <span data-ttu-id="d5ca5-144">В области сведений нажмите кнопку **Применить** , чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="d5ca5-145">Нажмите кнопку **проверочное правило** , чтобы проверить, правильно ли настроено новое правило.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="d5ca5-146">Изменение существующего правила веб-публикации для добавления внешней сети хранения данных автообнаружения и URL-адреса</span><span class="sxs-lookup"><span data-stu-id="d5ca5-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="d5ca5-147">Нажмите кнопку **Пуск**, наведите указатель мыши на пункт **программы**, выберите **Microsoft FOREFRONT TMG**и щелкните **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5ca5-148">Вы будете повторять изменения для каждого правила публикации и его прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="d5ca5-149">Как правило, это будет одно правило и прослушиватель для пулов переднего плана и один для дополнительных режиссеров или пулов, если вы их развернут.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="d5ca5-150">На левой панели разверните узел **ServerName**, щелкните правой кнопкой мыши **политику брандмауэра**и выберите соответствующее правило.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-150">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="d5ca5-151">На вкладке **задачи** щелкните **изменить выбранное правило**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-151">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="d5ca5-152">На вкладке **общедоступное имя** в **этом правиле применяются к**запросам на выборку **для указанных ниже веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="d5ca5-153">Нажмите кнопку **Добавить**, введите имя нового сайта автообнаружения (например, "lyncdiscover.contoso.com"), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="d5ca5-154">На вкладке **прослушиватель** нажмите кнопку **выбрать сертификат** и назначьте новый сертификат дополнительным записям в сети хранения данных для службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-154">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="d5ca5-155">Закройте диалоговое окно "свойства прослушивателя и веб-публикации".</span><span class="sxs-lookup"><span data-stu-id="d5ca5-155">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="d5ca5-156">В области сведений нажмите кнопку **Применить** , чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="d5ca5-157">Нажмите кнопку **проверочное правило** , чтобы проверить, правильно ли настроено новое правило.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="d5ca5-158">Создание правила веб-публикации для порта 80</span><span class="sxs-lookup"><span data-stu-id="d5ca5-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="d5ca5-159">Нажмите кнопку **Пуск**, наведите указатель мыши на пункт **программы**, выберите **Microsoft FOREFRONT TMG**и щелкните **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d5ca5-160">На левой панели разверните узел **ServerName**, щелкните **политику брандмауэра**правой кнопкой мыши, наведите указатель на пункт **создать**и выберите **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d5ca5-161">На странице **Добро пожаловать на новую страницу правила веб-публикации** введите отображаемое имя для нового правила публикации (например, Lync АВТООБНАРУЖЕНИЯ (http)).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="d5ca5-162">На странице **Выбор действия правила** выберите пункт **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="d5ca5-163">На странице **Тип публикации** выберите **Опубликовать один веб-сайт или подсистему балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="d5ca5-164">На странице **Безопасность подключения к серверу** выберите **использование незащищенных подключений для подключения к опубликованному веб-серверу или ферме серверов**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="d5ca5-165">На странице **Внутренняя публикация подробных сведений** в поле **внутренний адрес сайта**введите полное доменное имя внутренних веб-служб для пула переднего плана (например, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="d5ca5-166">На странице **внутренние сведения о публикации** в поле **путь**введите \*\* / \*\* путь к папке, которую нужно опубликовать, а затем выберите параметр переадресовать первоначальный \*\*заголовок узла вместо того, который указан в полях внутреннее имя сайта. \*\*.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="d5ca5-167">На странице **сведения об общедоступном имени** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="d5ca5-168">В разделе **запросы на**получение выберите **это доменное имя**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="d5ca5-169">В **общедоступном имени**введите **lyncdiscover.** \<сипдомаин\> (внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="d5ca5-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="d5ca5-170">В списке **путь**введите \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="d5ca5-171">На странице " **Выбор веб-прослушивателя** " в **веб-прослушивателе**выберите веб-прослушиватель или создайте новый с помощью мастера создания определений веб-прослушивателей.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="d5ca5-172">На странице **Делегирование проверки** подлинности выберите вариант **нет делегирования, и клиент не может выполнить проверку подлинности напрямую**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="d5ca5-173">На странице **User Set (пользовательский** ) выберите " **все пользователи**".</span><span class="sxs-lookup"><span data-stu-id="d5ca5-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="d5ca5-174">На странице **завершения мастера создания правила веб-публикации** убедитесь, что параметры правила веб-публикации указаны правильно, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="d5ca5-175">В списке правил веб-публикации Forefront TMG дважды щелкните новое правило, которое вы только что добавили, чтобы открыть **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="d5ca5-176">На вкладке **мосты** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d5ca5-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="d5ca5-177">Выберите **веб-сервер**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="d5ca5-178">Выберите параметр **перенаправлять запросы на HTTP-порт**и введите **8080** для номера порта.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="d5ca5-179">Убедитесь, что **запросы на перенаправление на порт SSL** не выбраны.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="d5ca5-180">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-180">Click **OK**.</span></span>

17. <span data-ttu-id="d5ca5-181">В области сведений нажмите кнопку **Применить** , чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="d5ca5-182">Нажмите кнопку **проверочное правило** , чтобы проверить, правильно ли настроено новое правило.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="d5ca5-183">Убедитесь, что URL-адрес службы внешнего автообнаружения не определен в других правилах веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="d5ca5-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5ca5-184">См. также</span><span class="sxs-lookup"><span data-stu-id="d5ca5-184">See Also</span></span>


[<span data-ttu-id="d5ca5-185">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5ca5-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


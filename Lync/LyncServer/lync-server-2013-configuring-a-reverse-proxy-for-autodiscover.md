---
title: 'Lync Server 2013: Настройка обратного прокси-сервера для службы автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 712dbc4e3bc9acf083f540520968953115ffc699
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="e01e2-102">Настройка обратного прокси-сервера для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e01e2-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e01e2-103">_**Последнее изменение темы:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="e01e2-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="e01e2-104">Служба автообнаружения и поддержка для клиентов, использующих службу автообнаружения, требуют изменения существующего правила веб-публикации или создания нового правила веб-публикации для обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e01e2-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="e01e2-105">Изменение или создание нового правила публикации не зависит от решения о том, как обновить или не обновить списки альтернативных имен субъектов в сертификатах обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="e01e2-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="e01e2-106">Если вы решили использовать HTTPS для начального запроса службы автообнаружения Lync Server 2013 и обновить списки альтернативных имен субъектов в сертификатах обратного прокси-сервера, вам необходимо назначить обновленный общедоступный сертификат для прослушивателя SSL (Secure Sockets Layer) на обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e01e2-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="e01e2-107">Требуемое обновление для внешнего (общедоступного) сертификата будет включать запись "альтернативное имя субъекта" (SAN) для lyncdiscover. \<доменное\>имя.</span><span class="sxs-lookup"><span data-stu-id="e01e2-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="e01e2-108">Затем необходимо изменить существующий прослушиватель для внешних веб-служб или создать новое правило веб-публикации для внешнего URL-адреса службы автообнаружения, например **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="e01e2-109">Если у вас еще нет правила веб-публикации для внешнего URL-адреса веб-служб Lync Server 2013 для пула переднего плана и пула директоров (если вы развернули директоров), вам также нужно опубликовать правило для этого.</span><span class="sxs-lookup"><span data-stu-id="e01e2-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e01e2-110">Правило публикации и прослушиватель обратного прокси-сервера могут обслуживать как внешние веб-службы, так и служба автообнаружения при условии, что назначенный прослушивателю сертификат содержит необходимое имя субъекта и альтернативные имена субъектов для обоих этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="e01e2-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="e01e2-111">Дополнительные сведения о конфигурации по умолчанию для веб-прослушивателя и правила публикации приведены в статье <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync Server 2013</A> для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="e01e2-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="e01e2-112">Если вы решили использовать HTTP для исходных запросов службы автообнаружения, чтобы вам не требовалось обновлять альтернативные имена субъектов для обратного прокси-сервера, вам необходимо создать или изменить правило веб-публикации для порта 80.</span><span class="sxs-lookup"><span data-stu-id="e01e2-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="e01e2-113">В процедурах этого раздела описывается создание и изменение правил веб-публикации в Microsoft Forefront Threat Management Gateway 2010 для реализации автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e01e2-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e01e2-p104">В этих процедурах предполагается, что вы установили выпуск Standard Edition продукта Forefront Threat Management Gateway (TMG) 2010. Если вы используете другой обратный прокси-сервер, выполняются аналогичные процедуры, однако их требуется привести в соответствие с документацией по этому стороннему продукту.</span><span class="sxs-lookup"><span data-stu-id="e01e2-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="e01e2-116">Создание правила веб-публикации для внешнего URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="e01e2-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="e01e2-117">Нажмите кнопку **Пуск**, выберите **Программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="e01e2-118">В левой области разверните узел **ServerName**, щелкните правой кнопкой мыши пункт **Политика брандмауэра**, выберите пункт **создать**, а затем — **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="e01e2-119">На странице **Welcome to the New Web Publishing Rule** (Новое правило веб-публикации) введите отображаемое имя для нового правила публикации (например, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="e01e2-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="e01e2-120">На странице **Выбрать действие правила** выберите пункт **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="e01e2-121">На странице **Тип публикации** выберите пункт **Опубликовать один веб-сайт или систему балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="e01e2-122">На странице **Безопасность подключения к серверу** выберите пункт **Использовать SSL для подключения к опубликованному веб-серверу или ферме серверов**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="e01e2-123">На странице **внутренние сведения публикации** в поле **имя внутреннего сайта**введите полное доменное имя (FQDN) пула директоров (например, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e01e2-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="e01e2-124">Если вы создаете правило для URL-адреса внешних веб-служб в пуле переднего плана, введите полное доменное имя интерфейсного пула (например, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e01e2-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="e01e2-125">На странице **внутренние сведения публикации** в поле **путь (необязательно)** введите \*\* / \*\* путь к папке, которая должна быть опубликована, а затем выберите пункт **переслать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="e01e2-126">На странице **Public Name Details** (Параметры общедоступного имени) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e01e2-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="e01e2-127">В области **Accept Requests for** (Принимать запросы для) выберите **This domain name** (Имя этого домена).</span><span class="sxs-lookup"><span data-stu-id="e01e2-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="e01e2-128">В **общедоступном имени**введите **lyncdiscover.** \<sipdomain\> (внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="e01e2-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="e01e2-129">Если вы создаете правило для URL-адреса внешних веб-служб в интерфейсном пуле, введите полное доменное имя внешних веб-служб в пуле переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e01e2-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="e01e2-130">В списке **путь**введите \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="e01e2-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="e01e2-131">На странице **Select Web Listener** (Выбрать веб-прослушиватель) в области **Web Listener** (Веб-прослушиватель) выберите существующий прослушиватель SSL с обновленным общим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="e01e2-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="e01e2-132">На странице **Authentication Delegation** (Делегирование проверки подлинности) выберите **No delegation, but client may authenticate directly** (Без делегирования, но клиент может выполнять проверку подлинности напрямую).</span><span class="sxs-lookup"><span data-stu-id="e01e2-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="e01e2-133">На странице **User Set** (Пользовательский набор) выберите **All Users** (Все пользователи).</span><span class="sxs-lookup"><span data-stu-id="e01e2-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="e01e2-134">На странице **Completing the New Web Publishing Rule Wizard** (Завершение работы мастера создания правила веб-публикации) проверьте правильность параметров правила веб-публикации, а затем нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="e01e2-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="e01e2-135">В списке правил веб-публикации Forefront TMG дважды щелкните недавно добавленное новое правило, чтобы открыть окно **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="e01e2-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="e01e2-136">На вкладке **To** (Куда) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e01e2-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="e01e2-137">Выберите **Forward the original host header instead of the actual one** (Пересылать исходный заголовок узла вместо действительного).</span><span class="sxs-lookup"><span data-stu-id="e01e2-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="e01e2-138">Выберите **Requests appear to come from the Forefront TMG computer** (Запросы поступили от компьютера Forefront TMG).</span><span class="sxs-lookup"><span data-stu-id="e01e2-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="e01e2-139">На вкладке **Bridging** (Использование моста) настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="e01e2-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="e01e2-140">Выберите **Web server** (Веб-сервер).</span><span class="sxs-lookup"><span data-stu-id="e01e2-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="e01e2-141">Выберите **Redirect requests to HTTP port** (Перенаправлять запросы на HTTP-порт) и введите **8080** в качестве номера порта.</span><span class="sxs-lookup"><span data-stu-id="e01e2-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="e01e2-142">Выберите **Redirect requests to SSL port** (Перенаправлять запросы на SSL-порт) и введите **4443** в качестве номера порта.</span><span class="sxs-lookup"><span data-stu-id="e01e2-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="e01e2-143">Нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="e01e2-143">Click **OK**.</span></span>

18. <span data-ttu-id="e01e2-144">Нажмите кнопку **Apply** (Применить) в области сведений, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e01e2-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="e01e2-145">Нажмите кнопку **Test Rule** (Тест правила) чтобы убедиться, что новое правило настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="e01e2-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="e01e2-146">Изменение существующего правила веб-публикации для добавления внешних альтернативного имени субъекта и URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="e01e2-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="e01e2-147">Нажмите кнопку **Пуск**, выберите **Программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e01e2-148">Вы будете повторять это изменение для каждого используемого правила публикации и прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="e01e2-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="e01e2-149">Как правило, это будет одно правило и прослушиватель для интерфейсных пулов и один для дополнительных директоров или пулов директоров, если вы их развернули.</span><span class="sxs-lookup"><span data-stu-id="e01e2-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="e01e2-p108">На левой панели разверните **ServerName** (Имя сервера) щелкните правой кнопкой мыши элемент **Firewall Policy** (Политика брандмауэра) и выберите нужное правило. На вкладке **Tasks** (Задачи) щелкните элемент **Edit Selected rule** (Изменить выбранное правило).</span><span class="sxs-lookup"><span data-stu-id="e01e2-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="e01e2-152">На вкладке **Public Name** (Общедоступное имя) в области **This rule applies to** (Это правило применяется к) выберите значение **Requests for the following Web sites** (Запросы к следующим веб-сайтам).</span><span class="sxs-lookup"><span data-stu-id="e01e2-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="e01e2-153">Нажмите кнопку **Add** (Добавить), введите имя нового сайта автообнаружения (например, «lyncdiscover.contoso.com») и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="e01e2-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="e01e2-p109">На вкладке **Listener** (Прослушиватель) щелкните элемент **Select Certificate** (Выбрать сертификат) и назначьте новый сертификат с добавленными записями альтернативного имени субъекта автообнаружения. Закройте свойства прослушивателя и веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="e01e2-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="e01e2-156">Нажмите кнопку **Apply** (Применить) в области сведений, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e01e2-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="e01e2-157">Нажмите кнопку **Test Rule** (Тест правила) чтобы убедиться, что новое правило настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="e01e2-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="e01e2-158">Создание правила веб-публикации для порта 80</span><span class="sxs-lookup"><span data-stu-id="e01e2-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="e01e2-159">Нажмите кнопку **Пуск**, выберите **Программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="e01e2-160">В левой области разверните узел **ServerName**, щелкните правой кнопкой мыши пункт **Политика брандмауэра**, выберите пункт **создать**, а затем — **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="e01e2-161">На странице **Welcome to the New Web Publishing Rule** (Новое правило веб-публикации) введите отображаемое имя для нового правила публикации (например, Lync Autodiscover (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="e01e2-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="e01e2-162">На странице **Select Rule Action** (Выбор действия правила) выберите элемент **Allow** (Разрешить).</span><span class="sxs-lookup"><span data-stu-id="e01e2-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="e01e2-163">На странице **Publishing Type** (Тип публикации) выберите **Publish a single Web site or load balancer** (Опубликовать один веб-сайт или подсистему балансировки нагрузки).</span><span class="sxs-lookup"><span data-stu-id="e01e2-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="e01e2-164">На странице **Server Connection Security** (Безопасность подключения к серверу) выберите **Use non-secured connections to connect to the published Web server or server farm** (Использовать SSL для подключения к опубликованному веб-серверу или ферме серверов).</span><span class="sxs-lookup"><span data-stu-id="e01e2-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="e01e2-165">На странице **внутренние сведения публикации** в поле **имя внутреннего сайта**введите полное доменное имя внутренних веб-служб для пула переднего плана (например, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e01e2-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="e01e2-166">На странице **внутренние сведения публикации** в поле **путь (необязательно)** введите \*\* / \*\* путь к папке, которую нужно опубликовать, а затем выберите **переадресовать исходный заголовок узла вместо того, который указан в поле внутреннее имя сайта**.</span><span class="sxs-lookup"><span data-stu-id="e01e2-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="e01e2-167">На странице **Public Name Details** (Параметры общедоступного имени) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e01e2-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="e01e2-168">В области **Accept Requests for** (Принимать запросы для) выберите **This domain name** (Имя этого домена).</span><span class="sxs-lookup"><span data-stu-id="e01e2-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="e01e2-169">В **общедоступном имени**введите **lyncdiscover.** \<sipdomain\> (внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="e01e2-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="e01e2-170">В списке **путь**введите \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="e01e2-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="e01e2-171">На странице **Select Web Listener** (Выбрать веб-прослушиватель) в области **Web Listener** (Веб-прослушиватель) выберите веб-прослушиватель или создайте новый с помощью мастера определения нового веб-прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="e01e2-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="e01e2-172">На странице **Authentication Delegation** (Делегирование проверки подлинности) выберите **No delegation, and client cannot authenticate directly** (Без делегирования, клиент не может выполнять проверку подлинности напрямую).</span><span class="sxs-lookup"><span data-stu-id="e01e2-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="e01e2-173">На странице **User Set** (Пользовательский набор) выберите **All Users** (Все пользователи).</span><span class="sxs-lookup"><span data-stu-id="e01e2-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="e01e2-174">На странице **Completing the New Web Publishing Rule Wizard** (Завершение работы мастера создания правила веб-публикации) проверьте правильность параметров правила веб-публикации, а затем нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="e01e2-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="e01e2-175">В списке правил веб-публикации Forefront TMG дважды щелкните недавно добавленное новое правило, чтобы открыть окно **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="e01e2-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="e01e2-176">На вкладке **Bridging** (Использование моста) настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="e01e2-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="e01e2-177">Выберите **Web server** (Веб-сервер).</span><span class="sxs-lookup"><span data-stu-id="e01e2-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="e01e2-178">Выберите **Redirect requests to HTTP port** (Перенаправлять запросы на HTTP-порт) и введите **8080** в качестве номера порта.</span><span class="sxs-lookup"><span data-stu-id="e01e2-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="e01e2-179">Убедитесь, что параметр **Redirect requests to SSL port** (Перенаправлять запросы на SSL-порт) не выбран.</span><span class="sxs-lookup"><span data-stu-id="e01e2-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="e01e2-180">Нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="e01e2-180">Click **OK**.</span></span>

17. <span data-ttu-id="e01e2-181">Нажмите кнопку **Apply** (Применить) в области сведений, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e01e2-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="e01e2-182">Нажмите кнопку **Test Rule** (Тест правила) чтобы убедиться, что новое правило настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="e01e2-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="e01e2-183">Убедитесь, что ни для одного из других правил веб-публикации не определен внешний URL-адрес службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="e01e2-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e01e2-184">См. также</span><span class="sxs-lookup"><span data-stu-id="e01e2-184">See Also</span></span>


[<span data-ttu-id="e01e2-185">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e01e2-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Настройка обратного прокси-сервера для мобильной работы'
description: 'Lync Server 2013: Настройка обратного прокси-сервера для мобильной работы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4e1a71f97bc1737299d54cc0f4c56f0f5981bef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544185"
---
# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="598d1-103">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="598d1-103">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="598d1-104">_**Последнее изменение темы:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="598d1-104">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="598d1-105">Если вы хотите использовать автоматическое обнаружение для клиентов мобильных устройств, вам необходимо изменить существующее или создать новое правило веб-публикации для обратного прокси-сервера независимо от того, обновляете ли вы списки альтернативных имен субъектов в сертификатах обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="598d1-105">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="598d1-106">Если вы решили использовать HTTPS для начального запроса службы автообнаружения Lync Server 2013 и обновить списки альтернативных имен субъектов в сертификатах обратного прокси-сервера, необходимо назначить обновленный общедоступный сертификат прослушивателю SSL на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="598d1-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="598d1-107">Дополнительные сведения о записях, необходимых для альтернативного имени субъекта, приведены [в статье технические требования для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="598d1-107">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="598d1-108">После этого вам требуется изменить существующий прослушиватель для внешних веб-служб или создать новое правило веб-публикации для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="598d1-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="598d1-109">Если у вас еще нет правила веб-публикации для внешнего URL-адреса веб-служб Lync Server 2013 для пула переднего плана, необходимо также опубликовать правило для этого.</span><span class="sxs-lookup"><span data-stu-id="598d1-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="598d1-110">Правило публикации и прослушиватель обратного прокси-сервера могут обслуживать как внешние веб-службы, так и служба автообнаружения при условии, что назначенный прослушивателю сертификат содержит необходимое имя субъекта и альтернативные имена субъектов для обоих этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="598d1-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="598d1-111">Дополнительные сведения о конфигурации по умолчанию для веб-прослушивателя и правила публикации приведены в статье <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Настройка обратных прокси-серверов для Lync Server 2013</A> для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="598d1-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="598d1-112">Если вы решили использовать HTTP для исходных запросов службы автообнаружения, чтобы вам не требовалось обновлять альтернативные имена субъектов для обратного прокси-сервера, вам необходимо создать или изменить правило веб-публикации для порта 80.</span><span class="sxs-lookup"><span data-stu-id="598d1-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="598d1-113">В процедурах этого раздела описывается создание и изменение правил веб-публикации в Microsoft Forefront Threat Management Gateway 2010 для реализации автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="598d1-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="598d1-p103">В этих процедурах предполагается, что вы установили выпуск Standard Edition продукта Forefront Threat Management Gateway (TMG) 2010. Если вы используете другой обратный прокси-сервер, выполняются аналогичные процедуры, однако их требуется привести в соответствие с документацией по этому стороннему продукту.</span><span class="sxs-lookup"><span data-stu-id="598d1-p103">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="598d1-116">Создание правила веб-публикации для внешнего URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="598d1-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="598d1-117">Нажмите кнопку **Пуск**, выберите **Программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="598d1-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="598d1-118">В левой области разверните узел **ServerName**, щелкните правой кнопкой мыши пункт **Политика брандмауэра**, выберите пункт **создать**, а затем — **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="598d1-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="598d1-119">На странице **Welcome to the New Web Publishing Rule** (Новое правило веб-публикации) введите отображаемое имя для нового правила публикации (например, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="598d1-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="598d1-120">На странице **Select Rule Action** (Выбор действия правила) выберите элемент **Allow** (Разрешить).</span><span class="sxs-lookup"><span data-stu-id="598d1-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="598d1-121">На странице **Тип публикации** выберите пункт **Опубликовать один веб-сайт или систему балансировки нагрузки**.</span><span class="sxs-lookup"><span data-stu-id="598d1-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="598d1-122">На странице **Безопасность подключения к серверу** выберите пункт **Использовать SSL для подключения к опубликованному веб-серверу или ферме серверов**.</span><span class="sxs-lookup"><span data-stu-id="598d1-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="598d1-123">На странице **внутренние сведения публикации** в поле **имя внутреннего сайта**введите полное доменное имя (FQDN) пула директоров (например, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="598d1-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="598d1-124">Если вы создаете правило для URL-адреса внешних веб-служб в пуле переднего плана, введите виртуальный IP-адрес аппаратного балансировщика нагрузки (HLB) перед интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="598d1-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="598d1-125">На странице **внутренние сведения публикации** в поле **путь (необязательно)** введите **/\*** путь к папке, которая должна быть опубликована, а затем выберите пункт **переслать исходный заголовок узла**.</span><span class="sxs-lookup"><span data-stu-id="598d1-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="598d1-126">На странице **Public Name Details** (Параметры общедоступного имени) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="598d1-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="598d1-127">В области **Accept Requests for** (Принимать запросы для) выберите **This domain name** (Имя этого домена).</span><span class="sxs-lookup"><span data-stu-id="598d1-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="598d1-128">В **общедоступном имени**введите **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="598d1-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="598d1-129">(внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="598d1-129">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="598d1-130">Если вы создаете правило для URL-адреса внешних веб-служб в интерфейсном пуле, введите полное доменное имя внешних веб-служб в пуле переднего плана (например, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="598d1-130">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="598d1-131">В списке **путь**введите **/\*** .</span><span class="sxs-lookup"><span data-stu-id="598d1-131">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="598d1-132">На странице **Select Web Listener** (Выбрать веб-прослушиватель) в области **Web Listener** (Веб-прослушиватель) выберите существующий прослушиватель SSL с обновленным общим сертификатом.</span><span class="sxs-lookup"><span data-stu-id="598d1-132">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="598d1-133">На странице **Authentication Delegation** (Делегирование проверки подлинности) выберите **No delegation, but client may authenticate directly** (Без делегирования, но клиент может выполнять проверку подлинности напрямую).</span><span class="sxs-lookup"><span data-stu-id="598d1-133">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="598d1-134">На странице **User Set** (Пользовательский набор) выберите **All Users** (Все пользователи).</span><span class="sxs-lookup"><span data-stu-id="598d1-134">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="598d1-135">На странице **Completing the New Web Publishing Rule Wizard** (Завершение работы мастера создания правила веб-публикации) проверьте правильность параметров правила веб-публикации, а затем нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="598d1-135">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="598d1-136">В списке правил веб-публикации Forefront TMG дважды щелкните недавно добавленное новое правило, чтобы открыть окно **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="598d1-136">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="598d1-137">На вкладке **To** (Куда) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="598d1-137">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="598d1-138">Выберите **Forward the original host header instead of the actual one** (Пересылать исходный заголовок узла вместо действительного).</span><span class="sxs-lookup"><span data-stu-id="598d1-138">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="598d1-139">Выберите **Requests appear to come from the Forefront TMG computer** (Запросы поступили от компьютера Forefront TMG).</span><span class="sxs-lookup"><span data-stu-id="598d1-139">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="598d1-140">На вкладке **Bridging** (Использование моста) настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="598d1-140">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="598d1-141">Выберите **Web server** (Веб-сервер).</span><span class="sxs-lookup"><span data-stu-id="598d1-141">Select **Web server**.</span></span>
    
      - <span data-ttu-id="598d1-142">Выберите **Redirect requests to HTTP port** (Перенаправлять запросы на HTTP-порт) и введите **8080** в качестве номера порта.</span><span class="sxs-lookup"><span data-stu-id="598d1-142">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="598d1-143">Выберите **Redirect requests to SSL port** (Перенаправлять запросы на SSL-порт) и введите **4443** в качестве номера порта.</span><span class="sxs-lookup"><span data-stu-id="598d1-143">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="598d1-144">Нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="598d1-144">Click **OK**.</span></span>

18. <span data-ttu-id="598d1-145">Нажмите кнопку **Apply** (Применить) в области сведений, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="598d1-145">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="598d1-146">Нажмите кнопку **Test Rule** (Тест правила) чтобы убедиться, что новое правило настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="598d1-146">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="598d1-147">Изменение существующего правила веб-публикации для добавления внешних альтернативного имени субъекта и URL-адреса автообнаружения</span><span class="sxs-lookup"><span data-stu-id="598d1-147">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="598d1-148">Нажмите кнопку **Пуск**, выберите **Программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="598d1-148">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="598d1-149">Вы будете повторять это изменение для каждого используемого правила публикации и прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="598d1-149">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="598d1-150">Как правило, это будет одно правило и прослушиватель для интерфейсных пулов и один для дополнительных директоров или пулов директоров, если вы их развернули.</span><span class="sxs-lookup"><span data-stu-id="598d1-150">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="598d1-p107">На левой панели разверните **ServerName** (Имя сервера) щелкните правой кнопкой мыши элемент **Firewall Policy** (Политика брандмауэра) и выберите нужное правило. На вкладке **Tasks** (Задачи) щелкните элемент **Edit Selected rule** (Изменить выбранное правило).</span><span class="sxs-lookup"><span data-stu-id="598d1-p107">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="598d1-153">На вкладке **Public Name** (Общедоступное имя) в области **This rule applies to** (Это правило применяется к) выберите значение **Requests for the following Web sites** (Запросы к следующим веб-сайтам).</span><span class="sxs-lookup"><span data-stu-id="598d1-153">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="598d1-154">Нажмите кнопку **Add** (Добавить), введите имя нового сайта автообнаружения (например, «lyncdiscover.contoso.com») и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="598d1-154">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="598d1-p108">На вкладке **Listener** (Прослушиватель) щелкните элемент **Select Certificate** (Выбрать сертификат) и назначьте новый сертификат с добавленными записями альтернативного имени субъекта автообнаружения. Закройте свойства прослушивателя и веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="598d1-p108">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="598d1-157">Нажмите кнопку **Apply** (Применить) в области сведений, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="598d1-157">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="598d1-158">Нажмите кнопку **Test Rule** (Тест правила) чтобы убедиться, что новое правило настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="598d1-158">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="598d1-159">Создание правила веб-публикации для порта 80</span><span class="sxs-lookup"><span data-stu-id="598d1-159">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="598d1-160">Нажмите кнопку **Пуск**, выберите **Программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="598d1-160">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="598d1-161">В левой области разверните узел **ServerName**, щелкните правой кнопкой мыши пункт **Политика брандмауэра**, выберите пункт **создать**, а затем — **правило публикации веб-сайта**.</span><span class="sxs-lookup"><span data-stu-id="598d1-161">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="598d1-162">На странице **Welcome to the New Web Publishing Rule** (Новое правило веб-публикации) введите отображаемое имя для нового правила публикации (например, Lync Autodiscover (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="598d1-162">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="598d1-163">На странице **Select Rule Action** (Выбор действия правила) выберите элемент **Allow** (Разрешить).</span><span class="sxs-lookup"><span data-stu-id="598d1-163">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="598d1-164">На странице **Publishing Type** (Тип публикации) выберите **Publish a single Web site or load balancer** (Опубликовать один веб-сайт или подсистему балансировки нагрузки).</span><span class="sxs-lookup"><span data-stu-id="598d1-164">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="598d1-165">На странице **Server Connection Security** (Безопасность подключения к серверу) выберите **Use non-secured connections to connect to the published Web server or server farm** (Использовать SSL для подключения к опубликованному веб-серверу или ферме серверов).</span><span class="sxs-lookup"><span data-stu-id="598d1-165">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="598d1-166">На странице **внутренние сведения публикации** в поле **внутренний адрес сайта**введите виртуальный IP-адрес аппаратной подсистемы балансировки нагрузки (HLB) перед интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="598d1-166">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="598d1-167">На странице **внутренние сведения публикации** в поле **путь (необязательно)** введите **/\*** путь к папке, которую нужно опубликовать, а затем выберите **переадресовать исходный заголовок узла вместо того, который указан в поле внутреннее имя сайта**.</span><span class="sxs-lookup"><span data-stu-id="598d1-167">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="598d1-168">На странице **Public Name Details** (Параметры общедоступного имени) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="598d1-168">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="598d1-169">В области **Accept Requests for** (Принимать запросы для) выберите **This domain name** (Имя этого домена).</span><span class="sxs-lookup"><span data-stu-id="598d1-169">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="598d1-170">В **общедоступном имени**введите **lyncdiscover.**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="598d1-170">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="598d1-171">(внешний URL-адрес службы автообнаружения).</span><span class="sxs-lookup"><span data-stu-id="598d1-171">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="598d1-172">В списке **путь**введите **/\*** .</span><span class="sxs-lookup"><span data-stu-id="598d1-172">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="598d1-173">На странице **Select Web Listener** (Выбрать веб-прослушиватель) в области **Web Listener** (Веб-прослушиватель) выберите веб-прослушиватель или создайте новый с помощью мастера определения нового веб-прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="598d1-173">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="598d1-174">На странице **Authentication Delegation** (Делегирование проверки подлинности) выберите **No delegation, and client cannot authenticate directly** (Без делегирования, клиент не может выполнять проверку подлинности напрямую).</span><span class="sxs-lookup"><span data-stu-id="598d1-174">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="598d1-175">На странице **User Set** (Пользовательский набор) выберите **All Users** (Все пользователи).</span><span class="sxs-lookup"><span data-stu-id="598d1-175">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="598d1-176">На странице **Completing the New Web Publishing Rule Wizard** (Завершение работы мастера создания правила веб-публикации) проверьте правильность параметров правила веб-публикации, а затем нажмите кнопку **Finish** (Готово).</span><span class="sxs-lookup"><span data-stu-id="598d1-176">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="598d1-177">В списке правил веб-публикации Forefront TMG дважды щелкните недавно добавленное новое правило, чтобы открыть окно **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="598d1-177">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="598d1-178">На вкладке **Bridging** (Использование моста) настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="598d1-178">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="598d1-179">Выберите **Web server** (Веб-сервер).</span><span class="sxs-lookup"><span data-stu-id="598d1-179">Select **Web server**.</span></span>
    
      - <span data-ttu-id="598d1-180">Выберите **Redirect requests to HTTP port** (Перенаправлять запросы на HTTP-порт) и введите **8080** в качестве номера порта.</span><span class="sxs-lookup"><span data-stu-id="598d1-180">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="598d1-181">Убедитесь, что параметр **Redirect requests to SSL port** (Перенаправлять запросы на SSL-порт) не выбран.</span><span class="sxs-lookup"><span data-stu-id="598d1-181">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="598d1-182">Нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="598d1-182">Click **OK**.</span></span>

17. <span data-ttu-id="598d1-183">Нажмите кнопку **Apply** (Применить) в области сведений, чтобы сохранить изменения и обновить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="598d1-183">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="598d1-184">Нажмите кнопку **Test Rule** (Тест правила) чтобы убедиться, что новое правило настроено правильно.</span><span class="sxs-lookup"><span data-stu-id="598d1-184">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="598d1-185">Убедитесь, что ни для одного из других правил веб-публикации не определен внешний URL-адрес службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="598d1-185">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="598d1-186">См. также</span><span class="sxs-lookup"><span data-stu-id="598d1-186">See Also</span></span>


[<span data-ttu-id="598d1-187">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="598d1-187">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="598d1-188">Технические требования для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="598d1-188">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


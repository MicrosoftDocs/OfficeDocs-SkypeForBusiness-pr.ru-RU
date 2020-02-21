---
title: Публикация сервера Office Web Apps с помощью обратного прокси-сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9a2bc53d306b51bd6aa681ccb4aa6747f38eac7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="09a3d-102">Публикация сервера Office Web Apps в Lync Server 2013 с помощью обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="09a3d-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09a3d-103">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="09a3d-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="09a3d-104">Если вы хотите, чтобы внешние пользователи (то есть те, которые выполняют вход извне брандмауэра вашей организации) имели доступ к презентациям PowerPoint сервера Office Web Apps, то вам потребуется использовать сервер Office Web Apps и обратный прокси-сервер, такой как Microsoft Forefront Threat Management Gateway.</span><span class="sxs-lookup"><span data-stu-id="09a3d-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="09a3d-105">Это также означает, что необходимо создать и настроить правило публикации веб-сайта; Это правило гарантирует, что пользователи смогут подключаться к серверу.</span><span class="sxs-lookup"><span data-stu-id="09a3d-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="09a3d-106">Если вы не хотите предоставлять доступ внешним пользователям, то настраивать правило публикации веб-сайтов не требуется.</span><span class="sxs-lookup"><span data-stu-id="09a3d-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="09a3d-107">Чтобы настроить правило публикации веб-сайтов в Forefront Threat Management Gateway, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="09a3d-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="09a3d-108">Нажмите кнопку **Пуск**, выберите **Все программы**, **Microsoft Forefront TMG** и затем **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="09a3d-109">В Forefront TMG щелкните правой кнопкой мыши элемент **Политика брандмауэра**, выберите пункт **Создать** и затем щелкните **Правило публикации веб-сайтов**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="09a3d-110">На странице **Мастер создания правила веб-публикации** введите имя для нового правила в поле **Имя правила веб-публикации** (например, **Правило сервера Office Web Apps**), а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="09a3d-111">На странице **Задание действия правила** выберите **Разрешить** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="09a3d-112">На странице **Тип публикации** выберите **Опубликовать один веб-сайт или подсистему балансировки нагрузки** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="09a3d-113">На странице **Безопасность подключения к серверу** выберите **Использовать SSL для подключения к опубликованному веб-серверу или ферме серверов** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="09a3d-p102">На странице **Сведения о внутренней публикации** введите полное доменное имя своего сервера Office Web Apps (например, **officewebapps01.contoso.com**) в поле **Имя внутреннего сайта** и нажмите кнопку **Далее**. Имя, введенное в поле **Имя внутреннего сайта**, должно появиться в поле "Субъект" или в поле "Альтернативное имя субъекта" сертификата, назначенного серверу Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="09a3d-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="09a3d-116">На странице **сведения о внутренней публикации** введите \*\* / \*\* в поле **путь (необязательно)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="09a3d-117">Синтаксис/\* синтаксис гарантирует, что все папки и вложенные папки сайта будут опубликованы.</span><span class="sxs-lookup"><span data-stu-id="09a3d-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="09a3d-118">На странице **Сведения об общедоступном имени** выберите пункт **Имя этого домена (ввести ниже)** в раскрывающемся списке **Принимать запросы для**, а затем введите полное имя для сервера Office Web Apps в поле "Общедоступное имя".</span><span class="sxs-lookup"><span data-stu-id="09a3d-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="09a3d-119">Это имя должно быть именем, используемым для доступа к вашему веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="09a3d-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="09a3d-120">Например, если доступ к сайту осуществляется по URL-адресу http://officewebapps01.contoso.com , введите **officewebapps01.contoso.com** в поле **общедоступное имя** .</span><span class="sxs-lookup"><span data-stu-id="09a3d-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="09a3d-121">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-121">Click **Next**.</span></span>

11. <span data-ttu-id="09a3d-122">На странице **Выбрать веб-прослушиватель** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="09a3d-123">В мастере определения нового веб-прослушивателя введите имя для нового веб-прослушивателя (например, **SSL**) в поле **Имя веб-прослушивателя** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="09a3d-124">На странице **Безопасность клиентских подключений** выберите **Требовать безопасного подключения SSL для клиентов** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="09a3d-125">На странице **IP-адреса веб-прослушивателя** последовательно выберите **Внешний**, **Внутренний** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="09a3d-126">На странице **SSL-сертификаты прослушивателя** выберите **Использовать единый сертификат для данного веб-прослушивателя** и щелкните элемент **Выбор сертификата**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="09a3d-127">В диалоговом окне **Выбор сертификата** выберите сертификат, который требуется использовать для веб-прослушивателя, и нажмите кнопку **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="09a3d-128">На странице **SSL-сертификаты прослушивателя** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="09a3d-129">На странице **Параметры проверки подлинности** выберите пункт **Без проверки подлинности** в раскрывающемся списке **Выбор порядка предоставления учетных данных для Forefront TMG** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="09a3d-130">На странице **Параметры единого входа** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="09a3d-p105">На странице **Завершение работы мастера создания веб-прослушивателя** просмотрите сводку выбранных вариантов конфигурации. Когда закончите просмотр, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="09a3d-133">На странице **Выбрать веб-прослушиватель** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="09a3d-134">На странице **Делегирование проверки подлинности** выберите **Без делегирования, но клиент может выполнять проверку подлинности напрямую** в раскрывающемся списке **Выберите метод для использования Forefront TMG при проверки подлинности на опубликованном веб-сервере** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="09a3d-p106">На странице **Наборы пользователей** подтвердите, что подходящие наборы пользователей содержатся в списке. По умолчанию это набор пользователей **Все пользователи**. Нажмите кнопку **Добавить**, чтобы добавить другие наборы пользователей, которые возможно определены вами. После завершения добавления нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="09a3d-139">На странице **Завершение работы мастера создания правила веб-публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="09a3d-p107">Обратите внимание на то, что нажатие кнопки **Готово** не означает завершение процесса, то есть такое нажатие не обеспечивает автоматическое применение и включение нового правила. Для этого вам потребуется нажать кнопку **Применить**, которая появится в пользовательском интерфейсе Forefront TMG. При нажатии кнопки **Применить** отображается диалоговое окно **Описание изменений конфигурации**. Нажмите кнопку **Применить** в этом диалоговом окне, чтобы включить новое правило публикации.</span><span class="sxs-lookup"><span data-stu-id="09a3d-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="09a3d-144">После применения нового правила необходимо внести некоторые небольшие изменения в правило, чтобы пользователи могли использовать новые возможности презентации PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="09a3d-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="09a3d-145">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="09a3d-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="09a3d-146">В Forefront TMG щелкните имя нового правила публикации правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="09a3d-147">В диалоговом окне **Свойства** на вкладке **Кому** выберите параметр **Пересылать исходный заголовок узла вместо действительного**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="09a3d-148">На вкладке **Трафик** щелкните элемент **Фильтрация** и затем элемент **Настроить HTTP**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="09a3d-149">В диалоговом окне **Настройка HTTP-политики для правила** снимите флажок **Проверить нормализацию** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="09a3d-150">В диалоговом окне **Свойства** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="09a3d-p109">В Forefront TMG нажмите кнопку **Применить**, чтобы разрешить внесение изменений. При отображении диалогового окна **Описание изменений конфигурации** нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="09a3d-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="09a3d-153">После завершения установки вы можете протестировать сервер Office Web Apps с помощью процедур, описанных в разделе [Проверка конфигурации сервера Office Web Apps в Lync server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="09a3d-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


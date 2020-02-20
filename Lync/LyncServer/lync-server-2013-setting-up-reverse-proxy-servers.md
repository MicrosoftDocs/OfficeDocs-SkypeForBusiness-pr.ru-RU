---
title: 'Lync Server 2013: Настройка обратных прокси-серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d00b30100b9203c82df0a2fc8ed8c4c593dfb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="804f2-102">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="804f2-103">_**Последнее изменение темы:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="804f2-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="804f2-104">Для развертываний пограничных серверов Microsoft Lync Server 2013 с помощью обратного прокси-сервера HTTPS в сети периметра необходимы внешние клиенты для доступа к веб-службам Lync Server 2013 (называемым *веб-компонентами* в Office Communications Server) в директоре и домашнем пуле пользователя.</span><span class="sxs-lookup"><span data-stu-id="804f2-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="804f2-105">Некоторые возможности, требующие внешнего доступа через обратный прокси-сервер, включают в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="804f2-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="804f2-106">Предоставление внешним пользователям возможности загружать содержимое собраний.</span><span class="sxs-lookup"><span data-stu-id="804f2-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="804f2-107">Предоставление внешним пользователям возможности расширять группы рассылки.</span><span class="sxs-lookup"><span data-stu-id="804f2-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="804f2-108">Предоставление удаленным пользователям возможности загружать файлы из службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="804f2-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="804f2-109">Доступ к клиенту Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="804f2-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="804f2-110">Доступ к веб-странице «Параметры конференц-связи с телефонным подключением».</span><span class="sxs-lookup"><span data-stu-id="804f2-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="804f2-111">Предоставление внешним устройствам возможности подключаться к веб-службе обновления устройств и получать обновления.</span><span class="sxs-lookup"><span data-stu-id="804f2-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="804f2-112">Включение мобильных приложений для автоматического обнаружения и использования URL-адресов мобильности (MCX) из Интернета.</span><span class="sxs-lookup"><span data-stu-id="804f2-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="804f2-113">Включение клиента Lync 2013, приложения Lync Windows Store и мобильного клиента Lync 2013 для поиска URL-адресов обнаружения Lync (автообнаружения) и использования веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="804f2-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="804f2-114">Мы рекомендуем вам настроить обратный прокси-сервер HTTP для публикации всех веб-служб во всех пулах.</span><span class="sxs-lookup"><span data-stu-id="804f2-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="804f2-115">Publishing https://Екстерналфкдн\* /публикует все виртуальные каталоги IIS для пула.</span><span class="sxs-lookup"><span data-stu-id="804f2-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="804f2-116">Вам необходимо одно правило публикации для каждого сервера Standard Edition, интерфейсного пула, Директора или пула директоров в организации.</span><span class="sxs-lookup"><span data-stu-id="804f2-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="804f2-117">Кроме того, вам необходимо опубликовать простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="804f2-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="804f2-118">Если в организации есть Директор или пул директоров, обратный прокси-сервер HTTP прослушивает запросы HTTP/HTTPS для простых URL-адресов и выступает для них прокси-сервером, ведущим к виртуальному каталогу внешних веб-служб в Директоре или пуле директоров.</span><span class="sxs-lookup"><span data-stu-id="804f2-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="804f2-119">Если вы не выполнили развертывание Директора, вам требуется выделить один пул для обработки запросов на простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="804f2-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="804f2-120">(Если это не домашний пул пользователя, он будет перенаправлять их к веб-службам в домашнем пуле пользователя).</span><span class="sxs-lookup"><span data-stu-id="804f2-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="804f2-121">Простые URL-адреса могут обрабатываться выделенным правилом веб-публикации, либо вы можете добавить такой адрес в общедоступные имена правила веб-публикации для Директора.</span><span class="sxs-lookup"><span data-stu-id="804f2-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="804f2-122">Кроме того, необходимо опубликовать внешний URL-адрес службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="804f2-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="804f2-123">Вы можете использовать Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 (ISA) Server с пакетом обновления 1 (SP1) или Internet Information Server 7,0, 7,5 или 8,0 с маршрутизацией запросов приложений (IIS ARR) в качестве обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="804f2-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="804f2-124">В данном разделе подробно описано, как настраивать Forefront Threat Management Gateway 2010, а настройка ISA Server 2006 осуществляется практически аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="804f2-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="804f2-125">Кроме того, для службы IIS ARR предоставляется руководство.</span><span class="sxs-lookup"><span data-stu-id="804f2-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="804f2-126">Если вы используете другой обратный прокси-сервер, обратитесь к документации по данному продукту и сопоставьте требования, приведенные здесь с соответствующими возможностями других обратных прокси-серверов.</span><span class="sxs-lookup"><span data-stu-id="804f2-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="804f2-127">Маршрутизация запросов приложений сервера IIS (IIS ARR) это полностью протестированный и поддерживаемый вариант для реализации обратного прокси-сервера для Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="804f2-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="804f2-128">В ноябре 2012 Корпорация Майкрософт перестала работать с лицензиями ForeFront Threat Management Gateway 2010 или TMG.</span><span class="sxs-lookup"><span data-stu-id="804f2-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="804f2-129">TMG по-прежнему является полностью поддерживаемым продуктом и по-прежнему доступен для продажи на устройствах, продаваемых третьими сторонами.</span><span class="sxs-lookup"><span data-stu-id="804f2-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="804f2-130">Кроме того, многие сторонние системы балансировки нагрузки и брандмауэры обеспечивают поддержку обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="804f2-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="804f2-131">Для аппаратных подсистем балансировки нагрузки и брандмауэров, обеспечивающих функции обратного прокси-сервера, обратитесь к поставщику за инструкциями по настройке продукта для обеспечения поддержки обратного прокси-сервера для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="804f2-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="804f2-132">Вы также можете просмотреть третьи лица, которые отправили документацию на продукт корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="804f2-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="804f2-133">Поддержка обеспечивается третьей стороной для своего решения.</span><span class="sxs-lookup"><span data-stu-id="804f2-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="804f2-134">Для просмотра третьих сторон, активных для предоставления решений, ознакомьтесь со статьей <A href="https://go.microsoft.com/fwlink/?linkid=268730">инфраструктура, квалифицированная для Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="804f2-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="804f2-135">В следующих разделах и процедурах используется Forefront Threat Management Gateway 2010 и IIS ARR в качестве основы для процедур развертывания и настройки.</span><span class="sxs-lookup"><span data-stu-id="804f2-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="804f2-136">Настройка полных доменных имен веб-ферм для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="804f2-137">Настройка сетевых адаптеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="804f2-138">Запрос и Настройка сертификата для обратного HTTP-прокси-сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="804f2-139">Настройка правил веб-публикации для отдельного внутреннего пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="804f2-140">Проверка и Настройка проверки подлинности и сертификации в виртуальных каталогах IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="804f2-141">Создание записей DNS для обратных прокси-серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="804f2-142">Проверка доступа через обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="804f2-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="804f2-143">Подготовительный этап</span><span class="sxs-lookup"><span data-stu-id="804f2-143">Before You Begin</span></span>

<span data-ttu-id="804f2-144">Для успешного развертывания Forefront Threat Management Gateway 2010 в качестве обратного прокси-сервера вам необходимо установить и настроить сервер, используя необходимые условия и требования к оборудованию, определенные в документации по Forefront Threat Management Gateway 2010.</span><span class="sxs-lookup"><span data-stu-id="804f2-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="804f2-145">В следующих разделах описано, как правильно настроить оборудование и установить Forefront Threat Management Gateway 2010 на сервере перед продолжением.</span><span class="sxs-lookup"><span data-stu-id="804f2-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="804f2-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="804f2-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="804f2-147">Рекомендации по оборудованию Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="804f2-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="804f2-148">Чтобы успешно развернуть IIS ARR в качестве обратного прокси-сервера, ознакомьтесь со следующими статьями, чтобы настроить оборудование и необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="804f2-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="804f2-149">Установка служб IIS в Windows Server 2008 или Windows Server 2008 R2 приведена в статье [Установка служб IIS 7 в Windows server 2008 или Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="804f2-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="804f2-150">Установка служб IIS в Windows Server 2012 приведена в статье [Установка служб IIS 8 в Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="804f2-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="804f2-151">Установка служб IIS в Windows Server 2012 R2 приведена в статье [Установка служб iis 8,5 на Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="804f2-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="804f2-152">Чтобы скачать расширение маршрутизации запросов приложений для IIS, следуйте инструкциям в статье [Загрузка маршрута запроса приложения версии 2.5](https://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="804f2-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="804f2-153">Чтобы установить ARR, для получения инструкций по [установке маршрутизации запросов приложения версии 2](https://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="804f2-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="804f2-154">В настоящее время опубликованы инструкции для ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="804f2-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="804f2-155">Для установки расширения не существует разницы между двумя версиями.</span><span class="sxs-lookup"><span data-stu-id="804f2-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


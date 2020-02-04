---
title: 'Lync Server 2013: планирование гибридных развертываний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="248b7-102">Планирование гибридных развертываний Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="248b7-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="248b7-103">_**Тема последнего изменения:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="248b7-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="248b7-104">При планировании гибридного развертывания необходимо принимать во требования к следующим требованиям пользователей и инфраструктуры сети.</span><span class="sxs-lookup"><span data-stu-id="248b7-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="248b7-105">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="248b7-105">Infrastructure Requirements</span></span>

<span data-ttu-id="248b7-106">Для реализации и развертывания гибридного развертывания необходимо настроить в вашей среде указанные ниже настройки.</span><span class="sxs-lookup"><span data-stu-id="248b7-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="248b7-107">Клиент Microsoft Office 365 с поддержкой Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="248b7-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="248b7-108">Обратите внимание, что для гибридной конфигурации с локальным развертыванием можно использовать только один клиент.</span><span class="sxs-lookup"><span data-stu-id="248b7-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="248b7-109">Единая локальная версия (инфраструктура) сервера Skype для бизнеса Server или Lync Server, развернутая в поддерживаемой топологии.</span><span class="sxs-lookup"><span data-stu-id="248b7-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="248b7-110">Ознакомьтесь с требованиями к топологии.</span><span class="sxs-lookup"><span data-stu-id="248b7-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="248b7-111">Сведения о настройке развертывания Lync Server 2013 или Lync Server 2010 для гибридной среды можно найти в разделе [Настройка гибридных развертываний Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="248b7-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="248b7-112">Администрирование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="248b7-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="248b7-113">Если вы используете Lync Server 2013 или Lync Server 2010, вы можете использовать средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b7-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="248b7-114">Для поддержки единого входа в Office 365, чтобы пользователи могли использовать те же учетные данные для входа в Office, поскольку они являются локальными, вы можете использовать функции синхронизации паролей в Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="248b7-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="248b7-115">Для единого входа в Office 365 можно также пользоваться службой федерации Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="248b7-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="248b7-116">Дополнительные сведения можно найти [в разделе Интеграция локальных удостоверений с Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="248b7-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="248b7-117">Единое решение для синхронизации каталогов, которое синхронизирует локальные и сетевые объекты Active Directory.</span><span class="sxs-lookup"><span data-stu-id="248b7-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="248b7-118">Подробнее об синхронизации каталогов можно узнать в разделе [средства интеграции каталогов](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="248b7-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="248b7-119">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="248b7-119">Lync Client Support</span></span>

<span data-ttu-id="248b7-120">Существуют некоторые отличия функций, поддерживаемых в клиентах Lync, а также возможности, доступные в локальных и онлайновых средах.</span><span class="sxs-lookup"><span data-stu-id="248b7-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="248b7-121">Прежде чем вы решите, где вы хотите использовать домашние пользователи в вашей организации, вы можете просмотреть поддержку клиентов для различных конфигураций сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="248b7-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="248b7-122">Следующие клиенты поддерживаются в Skype для бизнеса Online в гибридном развертывании Lync:</span><span class="sxs-lookup"><span data-stu-id="248b7-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="248b7-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="248b7-123">Lync 2010</span></span>

  - <span data-ttu-id="248b7-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="248b7-124">Lync 2013</span></span>

  - <span data-ttu-id="248b7-125">Приложение Lync из Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="248b7-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="248b7-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="248b7-126">Lync Web App</span></span>

  - <span data-ttu-id="248b7-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="248b7-127">Lync Mobile</span></span>

  - <span data-ttu-id="248b7-128">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="248b7-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="248b7-129">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="248b7-129">Lync Room System</span></span>

  - <span data-ttu-id="248b7-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="248b7-130">Lync Basic 2013</span></span>

<span data-ttu-id="248b7-131">Подробные сведения о поддержке клиентов можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="248b7-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="248b7-132">Клиенты Lync Online</span><span class="sxs-lookup"><span data-stu-id="248b7-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="248b7-133">Таблица сравнения клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="248b7-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="248b7-134">Таблицы сравнения мобильных клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="248b7-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="248b7-135">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="248b7-135">Topology Requirements</span></span>

<span data-ttu-id="248b7-136">Чтобы настроить развертывание для гибридной работы с помощью Skype для бизнеса Online, необходимо иметь одну из следующих поддерживаемых топологий.</span><span class="sxs-lookup"><span data-stu-id="248b7-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="248b7-137">Развертывание Skype для бизнеса Server 2015 со всеми серверами, работающими под управлением Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="248b7-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="248b7-138">Развертывание Lync Server 2013 со всеми серверами с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="248b7-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="248b7-139">Развертывание Lync Server 2010 со всеми серверами, на которых запущен Lync Server 2010 с самыми последними накопительными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="248b7-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="248b7-140">На пограничном сервере федерации и сервере следующего прыжка на пограничном сервере федерации должно быть запущено приложение Lync Server 2010 с последними накопительными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="248b7-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="248b7-141">Административные инструменты для Skype для бизнеса Server 2015 или Lync Server 2013 должны устанавливаться хотя бы на один сервер или рабочую станцию для управления.</span><span class="sxs-lookup"><span data-stu-id="248b7-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="248b7-142">Смешанный сервер Lync Server 2013 и Skype для бизнеса Server 2015 со следующими ролями сервера — хотя бы на одном сайте, на котором работает Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="248b7-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="248b7-143">как минимум один пул серверов Enterprise Edition или Standard Edition; </span><span class="sxs-lookup"><span data-stu-id="248b7-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="248b7-144">пул директоров, связанный с федерацией SIP (при наличии);</span><span class="sxs-lookup"><span data-stu-id="248b7-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="248b7-145">пул пограничных серверов, связанный с федерацией SIP.</span><span class="sxs-lookup"><span data-stu-id="248b7-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="248b7-146">Смешанное развертывание сервера Lync Server 2010 и Skype для бизнеса Server 2015 со следующими ролями серверов в Skype для бизнеса Server 2015, как минимум, на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="248b7-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="248b7-147">как минимум один пул серверов Enterprise Edition или Standard Edition; </span><span class="sxs-lookup"><span data-stu-id="248b7-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="248b7-148">пул директоров, связанный с федерацией SIP (при наличии);</span><span class="sxs-lookup"><span data-stu-id="248b7-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="248b7-149">пул пограничных серверов, связанный с федерацией SIP для сайта.</span><span class="sxs-lookup"><span data-stu-id="248b7-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="248b7-150">Смешанное развертывание Lync Server 2010 и Lync Server 2013 со следующими ролями сервера на сайте Lync Server 2013, как минимум, для одного из них:</span><span class="sxs-lookup"><span data-stu-id="248b7-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="248b7-151">как минимум один пул серверов Enterprise Edition или Standard Edition на сайте;</span><span class="sxs-lookup"><span data-stu-id="248b7-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="248b7-152">пул директоров, связанный с федерацией SIP (при наличии на сайте);</span><span class="sxs-lookup"><span data-stu-id="248b7-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="248b7-153">пул пограничных серверов, связанный с федерацией SIP для сайта.</span><span class="sxs-lookup"><span data-stu-id="248b7-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="248b7-154">Все функции управления пользователями, в том числе пользовательские перемещения между локальными и UNRESOLVED_TOKEN_VAL (skypeforbusiness) Online, должны быть выполнены с помощью последней установленной версии средств администрирования.</span><span class="sxs-lookup"><span data-stu-id="248b7-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="248b7-155">Средства администрирования должны быть установлены на отдельном сервере, который имеет доступ к подключению к существующему локальному развертыванию и Интернету.</span><span class="sxs-lookup"><span data-stu-id="248b7-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="248b7-156">Командлет <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> для перемещения пользователей из локального развертывания в UNRESOLVED_TOKEN_VAL (skype16_online) необходимо запускать из средств администрирования, подключенных к локальному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="248b7-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="248b7-157">Дополнительные сведения о поддерживаемых топологиях приведены в разделе [Поддерживаемые топологии в Lync server 2013](lync-server-2013-supported-topologies.md)и [Справочники по топологии Lync Server 2013 для корпоративных гибридных развертываний](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="248b7-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="248b7-158">Сведения об устранении неполадок, возникающих при развертывании и подключении PowerShell к Lync Online, можно найти в [Lync Online: Lync PowerShell и гибридное устранение неполадок](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="248b7-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="248b7-159">Требования для списков разрешенных и заблокированных Федерации</span><span class="sxs-lookup"><span data-stu-id="248b7-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="248b7-p108">В список разрешенных доменов включены домены, для которых задано полное доменное имя пограничного сервера-партнера. Иногда они также называются *разрешенными серверами-партнерами* или *прямыми партнерами федерации*. Следует понимать различие между открытой и закрытой федерацией, которые в локальных развертываниях также называются соответственно *обнаружением партнера* и *списком разрешенных доменов-партнеров*.</span><span class="sxs-lookup"><span data-stu-id="248b7-p108">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured. These are sometimes referred to as *allowed partner servers* or *direct federation partners*. You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="248b7-163">Для успешного настройки гибридного развертывания необходимо соблюдение следующих требований:</span><span class="sxs-lookup"><span data-stu-id="248b7-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="248b7-p109">Для локального развертывания и клиента Office 365 должно быть настроено одинаковое соответствие доменов. Если в локальном развертывании включено обнаружение партнеров, для интерактивного клиента должна быть настроена открытая федерация. Если обнаружение партнеров отключено, для интерактивного клиента должна быть настроена закрытая федерация.</span><span class="sxs-lookup"><span data-stu-id="248b7-p109">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="248b7-167">Список заблокированных доменов в локальном развертывании должен полностью совпадать со списком заблокированных доменов для интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="248b7-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="248b7-168">Список разрешенных доменов в локальном развертывании должен полностью совпадать со списком разрешенных доменов для интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="248b7-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="248b7-169">Для работы с внешними связями в Интернет-клиенте, которые настроены с помощью панели управления Lync Online, должна быть включена Федерация.</span><span class="sxs-lookup"><span data-stu-id="248b7-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="248b7-170">Параметры DNS</span><span class="sxs-lookup"><span data-stu-id="248b7-170">DNS Settings</span></span>

<span data-ttu-id="248b7-171">При создании записей DNS для гибридных развертываний все внешние записи DNS Lync должны указывать на локальную инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="248b7-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="248b7-172">Для получения подробных сведений о необходимых DNS-записях ознакомьтесь с [требованиями к системе доменных имен (DNS) для Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="248b7-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="248b7-173">Кроме того, обязательно убедитесь, что описанное в таблице ниже разрешение DNS работает в вашем локальном развертывании.</span><span class="sxs-lookup"><span data-stu-id="248b7-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="248b7-174">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="248b7-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="248b7-175">Кем разрешено</span><span class="sxs-lookup"><span data-stu-id="248b7-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="248b7-176">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="248b7-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="248b7-177">DNS SRV-запись для _sipfederationtls. _tcp. &lt;sipdomain.com&gt; для всех поддерживаемых доменов SIP с разрешениями на доступ к внешним IP-адресам пограничного сервера (s)</span><span class="sxs-lookup"><span data-stu-id="248b7-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="248b7-178">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="248b7-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="248b7-p111">Включите федеративное подключение в гибридной конфигурации. Пограничному серверу необходимо знать, куда направлять федеративный трафик для домена SIP, который разделяется на локальный и сетевой.</span><span class="sxs-lookup"><span data-stu-id="248b7-p111">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="248b7-181">Записи DNS A для полного доменного имени пограничной службы веб-конференций, например, webcon.contoso.com, разрешается во внешние IP-адреса пограничного сервера веб-конференций</span><span class="sxs-lookup"><span data-stu-id="248b7-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="248b7-182">Компьютеры пользователей, подключенные к внутренней корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="248b7-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="248b7-p112">Включите для пользователей в сети возможность представлять или просматривать содержимое во время собраний, которые проводятся локально. К содержимому относятся файлы PowerPoint, доски, опросы и общие заметки. </span><span class="sxs-lookup"><span data-stu-id="248b7-p112">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="248b7-185">В зависимости от настройки DNS в вашей организации может потребоваться добавить эти записи во внутреннюю зону DNS, чтобы соответствующие домены SIP предоставляли внутреннее разрешение DNS для этих записей.</span><span class="sxs-lookup"><span data-stu-id="248b7-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="248b7-186">Вопросы применения брандмауэра</span><span class="sxs-lookup"><span data-stu-id="248b7-186">Firewall Considerations</span></span>

<span data-ttu-id="248b7-p113">Компьютеры в сети должны поддерживать выполнение стандартных уточняющих интернет-запросов DNS. Если эти компьютеры могут осуществлять доступ к стандартным интернет-сайтам, сеть отвечает этому требованию.</span><span class="sxs-lookup"><span data-stu-id="248b7-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="248b7-189">В зависимости от расположения центра обработки данных Microsoft Online Services необходимо также настроить сетевые брандмауэры для приема подключений на основе доменных имен с подстановочными знаками (например, весь трафик от \*. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="248b7-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="248b7-190">Если брандмауэры организации не поддерживают конфигурации с подстановочными именами, необходимо вручную определить диапазоны IP-адресов, которые необходимо разрешить, и указанные порты.</span><span class="sxs-lookup"><span data-stu-id="248b7-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="248b7-191">Ознакомьтесь с разделом Справка [Office 365 URL-адреса и диапазоны IP-адресов](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="248b7-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="248b7-192">Требования к портам и протоколу</span><span class="sxs-lookup"><span data-stu-id="248b7-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="248b7-193">В дополнение к требованиям к портам для внутренней связи Lync Server 2013 необходимо также настроить указанные ниже порты.</span><span class="sxs-lookup"><span data-stu-id="248b7-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="248b7-194">Протокол и порт</span><span class="sxs-lookup"><span data-stu-id="248b7-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="248b7-195">Приложения</span><span class="sxs-lookup"><span data-stu-id="248b7-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="248b7-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="248b7-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="248b7-197">Открыть входящее</span><span class="sxs-lookup"><span data-stu-id="248b7-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="248b7-198">Службы федерации Active Directory (роль сервера федерации)</span><span class="sxs-lookup"><span data-stu-id="248b7-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="248b7-199">Дополнительные сведения можно найти в разделе <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Общее представление о службах РОЛЕЙ AD FS</a>.</span><span class="sxs-lookup"><span data-stu-id="248b7-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="248b7-200">Службы федерации Active Directory (роль прокси-сервера)</span><span class="sxs-lookup"><span data-stu-id="248b7-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="248b7-201">Портал Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="248b7-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="248b7-202">Мой корпоративный портал</span><span class="sxs-lookup"><span data-stu-id="248b7-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="248b7-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="248b7-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="248b7-204">Клиент Lync (связь с Lync Online из локального сервера Lync Server)</span><span class="sxs-lookup"><span data-stu-id="248b7-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="248b7-205">TCP 80 и 443</span><span class="sxs-lookup"><span data-stu-id="248b7-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="248b7-206">Открыть входящее</span><span class="sxs-lookup"><span data-stu-id="248b7-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="248b7-207">Средство синхронизации каталогов Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="248b7-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="248b7-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="248b7-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="248b7-209">Открытие входящего и исходящего трафика на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="248b7-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="248b7-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="248b7-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="248b7-211">Открытие сеансов совместного использования данных для входящих и исходящих сообщений</span><span class="sxs-lookup"><span data-stu-id="248b7-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="248b7-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="248b7-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="248b7-213">Открытие входящего и исходящего трафика для сеансов совместного использования звука, видео и приложений</span><span class="sxs-lookup"><span data-stu-id="248b7-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="248b7-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="248b7-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="248b7-215">Открытие входящего и исходящего трафика для сеансов голосовой связи и видеозвонков</span><span class="sxs-lookup"><span data-stu-id="248b7-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="248b7-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="248b7-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="248b7-217">Открыть "Исходящие" для сеансов аудио и видео</span><span class="sxs-lookup"><span data-stu-id="248b7-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="248b7-218">Учетные записи пользователей и данные</span><span class="sxs-lookup"><span data-stu-id="248b7-218">User Accounts and Data</span></span>

<span data-ttu-id="248b7-219">В гибридном развертывании Lync Server 2013 любой пользователь, который вы хотите дома в Lync Online, необходимо сначала создать в локальном развертывании, чтобы создать учетную запись пользователя в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="248b7-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="248b7-220">Затем вы можете переместить пользователя в Skype для бизнеса Online, который будет перемещать список контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="248b7-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="248b7-221">При синхронизации учетных записей пользователей между локальными развертываниями Lync Online и службами AD FS и DirSync необходимо синхронизировать учетные записи рекламных объявлений для всех пользователей Lync в Организации между локальными и Интернет-развертываниями Lync, даже если пользователи не переносятся в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="248b7-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="248b7-222">Если не все пользователи синхронизированы, связь между локальными и сетевыми пользователи в организации может функционировать неправильно.</span><span class="sxs-lookup"><span data-stu-id="248b7-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="248b7-223">Если пользователь создается с помощью веб-портала для Office 365, учетная запись пользователя не синхронизируется с локальной службой Active Directory, и пользователь не будет находиться в локальной службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="248b7-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="248b7-224">Если вы уже создали пользователей в Lync Online и хотите настроить гибридную среду с помощью локального сервера Lync, ознакомьтесь с разрешениями в разделе <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальное приложение Lync в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="248b7-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="248b7-225">Следует также принять во внимание следующие моменты, касающиеся пользователя, при планировании гибридного развертывания.</span><span class="sxs-lookup"><span data-stu-id="248b7-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="248b7-226">**Контакты пользователей.**   предельное число контактов для пользователей Lync Online — 250.</span><span class="sxs-lookup"><span data-stu-id="248b7-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="248b7-227">Все контакты, превышающие это количество, удаляются из списка контактов пользователя при перемещении учетной записи в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="248b7-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="248b7-228">**Обмен мгновенными сообщениями и**   списки контактов пользователей, группы и списки управления доступом (ACL) переносятся вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="248b7-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="248b7-229">**Данные конференций, содержимое собраний и запланированные собрания**   это содержимое не переносится вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="248b7-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="248b7-230">После переноса учетных записей пользователей в Lync Online они должны заново запланировать собрания.</span><span class="sxs-lookup"><span data-stu-id="248b7-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="248b7-231">Политики и функции пользователей</span><span class="sxs-lookup"><span data-stu-id="248b7-231">User Policies and Features</span></span>

  - <span data-ttu-id="248b7-232">В гибридной среде Lync Server 2013 пользователи могут обмениваться мгновенными сообщениями, голосами и собраниями локально или в сети, но не обоими одновременно.</span><span class="sxs-lookup"><span data-stu-id="248b7-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="248b7-233">**Клиент Lync для**     некоторых пользователей может потребоваться новая версия клиента при перемещении в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="248b7-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="248b7-234">Для Office Communications Server 2007 R2 пользователи должны переноситься в пул Lync Server 2013 перед переходом на Lync Online.</span><span class="sxs-lookup"><span data-stu-id="248b7-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="248b7-235">Дополнительные сведения о поддержке клиентов можно найти в разделе [клиенты для Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) и [Поддерживаемые клиенты Lync и конфигурации сетевого порта](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="248b7-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="248b7-236">**Локальные политики и конфигурация (не пользовательская)**   в Интернете и локальных политиках требуют отдельной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="248b7-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="248b7-237">Невозможно задать глобальные политики, применимые к обеим средам.</span><span class="sxs-lookup"><span data-stu-id="248b7-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


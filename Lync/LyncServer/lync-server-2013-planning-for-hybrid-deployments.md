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
ms.openlocfilehash: 4b0efc4a6a9e9f195705801969b8459c17855388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="2b7d1-102">Планирование гибридных развертываний Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b7d1-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b7d1-103">_**Последнее изменение темы:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="2b7d1-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="2b7d1-104">При планировании гибридного развертывания следует учитывать следующие требования для пользователей и сетевой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="2b7d1-105">Требования к инфраструктуре</span><span class="sxs-lookup"><span data-stu-id="2b7d1-105">Infrastructure Requirements</span></span>

<span data-ttu-id="2b7d1-106">Для реализации и развертывания гибридного развертывания в вашей среде необходимо настроить следующие настройки.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="2b7d1-107">Клиент Microsoft Office 365 со Skype для бизнеса Online включен.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="2b7d1-108">Обратите внимание, что для гибридной конфигурации с локальным развертыванием можно использовать только один клиент.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="2b7d1-109">Одно локальное развертывание (инфраструктура) Skype для бизнеса Server или Lync Server, развернутое в поддерживаемой топологии.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="2b7d1-110">См. требования к топологии.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="2b7d1-111">Сведения о настройке развертывания Lync Server 2013 или Lync Server 2010 для гибридной среды приведены в статье [Настройка Lync server 2013 гибридных развертываний](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="2b7d1-112">Средства администрирования Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="2b7d1-113">Если вы используете Lync Server 2013 или Lync Server 2010, вы можете использовать средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="2b7d1-114">Для поддержки единого входа в Office 365, чтобы пользователи могли использовать одни и те же учетные данные для входа в Office в локальной среде, вы можете использовать функции синхронизации паролей Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="2b7d1-115">Вы также можете использовать службы федерации Active Directory (AD FS) для единого входа в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="2b7d1-116">Дополнительные сведения см. в статье [Интеграция локальных удостоверений с Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="2b7d1-117">Единое решение синхронизации каталогов для синхронизации локальных и сетевых объектов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="2b7d1-118">Дополнительные сведения о синхронизации службы каталогов содержатся в разделе [средства интеграции каталогов](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="2b7d1-119">Поддержка клиента Lync</span><span class="sxs-lookup"><span data-stu-id="2b7d1-119">Lync Client Support</span></span>

<span data-ttu-id="2b7d1-120">Существуют некоторые различия в функциях, поддерживаемых в клиентах Lync, а также о функциях, доступных в локальных и оперативных средах.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="2b7d1-121">Прежде чем принять решение о том, где вы хотите использовать домашние пользователи в вашей организации, вы можете просмотреть клиентскую поддержку различных конфигураций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="2b7d1-122">Следующие клиенты поддерживаются в Skype для бизнеса Online в гибридном развертывании Lync:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="2b7d1-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2b7d1-123">Lync 2010</span></span>

  - <span data-ttu-id="2b7d1-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2b7d1-124">Lync 2013</span></span>

  - <span data-ttu-id="2b7d1-125">Приложение Lync для Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="2b7d1-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="2b7d1-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2b7d1-126">Lync Web App</span></span>

  - <span data-ttu-id="2b7d1-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="2b7d1-127">Lync Mobile</span></span>

  - <span data-ttu-id="2b7d1-128">Lync для Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2b7d1-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="2b7d1-129">Система комнат Lync</span><span class="sxs-lookup"><span data-stu-id="2b7d1-129">Lync Room System</span></span>

  - <span data-ttu-id="2b7d1-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="2b7d1-130">Lync Basic 2013</span></span>

<span data-ttu-id="2b7d1-131">Подробные сведения о поддержке клиентов можно найти в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="2b7d1-132">Клиенты для Lync Online</span><span class="sxs-lookup"><span data-stu-id="2b7d1-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="2b7d1-133">Таблицы сравнения клиентов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b7d1-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="2b7d1-134">Таблицы сравнения мобильных клиентов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b7d1-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="2b7d1-135">Требования к топологии</span><span class="sxs-lookup"><span data-stu-id="2b7d1-135">Topology Requirements</span></span>

<span data-ttu-id="2b7d1-136">Чтобы настроить развертывание для гибридной среды со Skype для бизнеса Online, необходима одна из следующих поддерживаемых топологий:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="2b7d1-137">Развертывание Skype для бизнеса Server 2015 со всеми серверами, на которых работает Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="2b7d1-138">Развертывание Lync Server 2013 со всеми серверами, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="2b7d1-139">Развертывание Lync Server 2010 со всеми серверами Lync Server 2010 с последними накопительными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="2b7d1-140">Пограничный сервер федерации и сервер следующего прыжка на пограничном сервере федерации должны работать под управлением Lync Server 2010 с последними накопительными обновлениями.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="2b7d1-141">Средства администрирования Skype для бизнеса Server 2015 или Lync Server 2013 должны быть установлены по крайней мере на одном сервере или рабочей станции управления.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="2b7d1-142">Смешанное развертывание Lync Server 2013 и Skype для бизнеса Server 2015 со следующими ролями серверов хотя бы на одном сайте, на котором работает Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="2b7d1-143">По крайней мере один корпоративный пул или сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2b7d1-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="2b7d1-144">Пул директоров, связанный с Федерации SIP, если он существует</span><span class="sxs-lookup"><span data-stu-id="2b7d1-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="2b7d1-145">Пограничный пул, связанный с федерациюм SIP</span><span class="sxs-lookup"><span data-stu-id="2b7d1-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="2b7d1-146">Смешанное развертывание Lync Server 2010 и Skype для бизнеса Server 2015 со следующими ролями серверов хотя бы на одном сайте с Skype для бизнеса Server 2015:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="2b7d1-147">По крайней мере один корпоративный пул или сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2b7d1-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="2b7d1-148">Пул директоров, связанный с Федерации SIP, если он существует</span><span class="sxs-lookup"><span data-stu-id="2b7d1-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="2b7d1-149">Пограничный пул, связанный с федерациям SIP для сайта.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="2b7d1-150">Смешанное развертывание Lync Server 2010 и Lync Server 2013 со следующими ролями сервера по крайней мере на одном сайте, где выполняется Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="2b7d1-151">По крайней мере один корпоративный пул или сервер Standard Edition на сайте</span><span class="sxs-lookup"><span data-stu-id="2b7d1-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="2b7d1-152">Пул директоров, связанный с Федерации SIP, если он существует на сайте</span><span class="sxs-lookup"><span data-stu-id="2b7d1-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="2b7d1-153">Пограничный пул, связанный с федерациям SIP для сайта.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b7d1-154">Все Управление пользователями, включая перемещение пользователей между локальной и UNRESOLVED_TOKEN_VALной (skypeforbusiness) сети, необходимо выполнить с помощью последней установленной версии средств администрирования.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="2b7d1-155">Средства администрирования должны быть установлены на отдельном сервере, который имеет доступ к подключению к существующему локальному развертыванию и Интернету.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="2b7d1-156">Командлет <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> для перемещения пользователей из локального развертывания в UNRESOLVED_TOKEN_VAL (skype16_online) необходимо запускать из средств администрирования, подключенных к локальному развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="2b7d1-157">Дополнительные сведения о поддерживаемых топологиях приведены в статье [Поддерживаемые топологии в Lync server 2013 и в](lync-server-2013-supported-topologies.md) [эталонных топологиях Lync Server 2013 для корпоративных гибридных развертываний](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="2b7d1-158">Сведения об устранении неполадок гибридных развертываний и подключении PowerShell к Lync Online можно найти в [Lync Online: Lync PowerShell и гибридное устранение неполадок](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="2b7d1-159">Требования для разрешенных/заблокированных списках федерации</span><span class="sxs-lookup"><span data-stu-id="2b7d1-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="2b7d1-160">Список разрешенных доменов содержит домены, для которых настроено полное доменное имя (FQDN) пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="2b7d1-161">Иногда их называют *разрешенными серверами* - *посредниками или прямыми партнерами Федерации*.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="2b7d1-162">Вы должны быть знакомы с различиями между открытой Федерация и закрытой Федерации, которая называется списком *партнеров для обнаружения* и *разрешенных партнерских доменов*, соответственно, в локальных развертываниях.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="2b7d1-163">Для успешного настройки гибридного развертывания необходимо соблюдение следующих требований:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="2b7d1-p109">Для локального развертывания и клиента Office 365 должно быть настроено одинаковое соответствие доменов. Если в локальном развертывании включено обнаружение партнеров, для интерактивного клиента должна быть настроена открытая федерация. Если обнаружение партнеров отключено, для интерактивного клиента должна быть настроена закрытая федерация..</span><span class="sxs-lookup"><span data-stu-id="2b7d1-p109">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="2b7d1-167">Список заблокированных доменов в локальном развертывании должен полностью совпадать со списком заблокированных доменов для интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="2b7d1-168">Список разрешенных доменов в локальном развертывании должен полностью совпадать со списком разрешенных доменов для интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="2b7d1-169">Для работы с внешними связями в сетевом клиенте, которая настраивается с помощью панели управления Lync Online, должна быть включена Федерация.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="2b7d1-170">Параметры DNS</span><span class="sxs-lookup"><span data-stu-id="2b7d1-170">DNS Settings</span></span>

<span data-ttu-id="2b7d1-171">При создании записей DNS для гибридных развертываний все внешние записи DNS Lync должны указать на локальную инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="2b7d1-172">Для получения дополнительных сведений о необходимых записях DNS обратитесь к разделу [требования к системе доменных имен (DNS) для Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="2b7d1-173">Кроме того, необходимо убедиться, что разрешение DNS, описанное в следующей таблице, работает в локальном развертывании:</span><span class="sxs-lookup"><span data-stu-id="2b7d1-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b7d1-174">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="2b7d1-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-175">Разрешимо</span><span class="sxs-lookup"><span data-stu-id="2b7d1-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-176">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="2b7d1-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b7d1-177">Запись DNS SRV для _sipfederationtls. _tcp. &lt;sipdomain.com&gt; для всех поддерживаемых доменов SIP, РАЗРЕШАЮЩИХ внешние IP-адреса пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="2b7d1-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-178">Пограничные серверы</span><span class="sxs-lookup"><span data-stu-id="2b7d1-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-179">Включение Федеративной связи в гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="2b7d1-180">Пограничный сервер должен знать, где следует маршрутизировать федеративный трафик для домена SIP, который разделяется между локальным и подключенным.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b7d1-181">Записи A DNS для службы пограничного веб-конференц-связи, например webcon.contoso.com, разрешающие внешние IP-адреса веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-182">Компьютеры пользователей, подключенных к внутренней корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="2b7d1-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-183">Позволяет интерактивным пользователям отображать или просматривать содержимое на локальных размещенных собраниях.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="2b7d1-184">Контент включает файлы PowerPoint, доски, опросы и общие заметки.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2b7d1-185">В зависимости от того, как настроена служба DNS в Организации, может потребоваться добавить эти записи в внутреннюю размещенную зону DNS для соответствующих доменов SIP, чтобы обеспечить внутреннее разрешение DNS для этих записей.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="2b7d1-186">Информация о брандмауэре</span><span class="sxs-lookup"><span data-stu-id="2b7d1-186">Firewall Considerations</span></span>

<span data-ttu-id="2b7d1-p113">Компьютеры в сети должны поддерживать выполнение стандартных уточняющих интернет-запросов DNS. Если эти компьютеры могут осуществлять доступ к стандартным интернет-сайтам, сеть отвечает этому требованию.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="2b7d1-189">В зависимости от расположения центра обработки данных Microsoft Online Services необходимо также настроить сетевые брандмауэры для приема подключений на основе доменных имен с подстановочными знаками (например, весь трафик от \*. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="2b7d1-190">Если брандмауэры организации не поддерживают конфигурации с подстановочными именами, необходимо вручную определить диапазоны IP-адресов, которые необходимо разрешить, и указанные порты.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="2b7d1-191">Обратитесь к разделу Справка [Office 365 URL-адреса и диапазоны IP-адресов](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="2b7d1-192">Требования относительно портов и протоколов</span><span class="sxs-lookup"><span data-stu-id="2b7d1-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="2b7d1-193">Помимо требований к портам для внутренней связи Lync Server 2013, необходимо также настроить следующие порты.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b7d1-194">Протокол/порт</span><span class="sxs-lookup"><span data-stu-id="2b7d1-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="2b7d1-195">Приложения</span><span class="sxs-lookup"><span data-stu-id="2b7d1-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b7d1-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="2b7d1-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-197">Открытый для входящего трафика</span><span class="sxs-lookup"><span data-stu-id="2b7d1-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="2b7d1-198">Службы федерации Active Directory (роли серверов федерации)</span><span class="sxs-lookup"><span data-stu-id="2b7d1-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="2b7d1-199">Более подробную информацию можно узнать в статье <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Общие сведения о службах РОЛЕЙ AD FS</a>.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="2b7d1-200">Службы федерации Active Directory (роли прокси-серверов)</span><span class="sxs-lookup"><span data-stu-id="2b7d1-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="2b7d1-201">Портал Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="2b7d1-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="2b7d1-202">Портал моей организации</span><span class="sxs-lookup"><span data-stu-id="2b7d1-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="2b7d1-203">Веб-приложение Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="2b7d1-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="2b7d1-204">Клиент Lync (связь с Lync Online с локального сервера Lync Server)</span><span class="sxs-lookup"><span data-stu-id="2b7d1-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b7d1-205">TCP 80 и 443</span><span class="sxs-lookup"><span data-stu-id="2b7d1-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-206">Открытый для входящего трафика</span><span class="sxs-lookup"><span data-stu-id="2b7d1-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="2b7d1-207">Средство синхронизации Microsoft Online Services со службой каталогов</span><span class="sxs-lookup"><span data-stu-id="2b7d1-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b7d1-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="2b7d1-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-209">Открытие входящей/исходящей почты на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="2b7d1-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b7d1-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="2b7d1-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-211">Открытие сеансов общего доступа к данным для входящих и исходящих сообщений</span><span class="sxs-lookup"><span data-stu-id="2b7d1-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b7d1-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="2b7d1-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-213">Открытие входящих и исходящих сообщений для аудио-и видеоконференций, сеансов общего доступа к приложениям</span><span class="sxs-lookup"><span data-stu-id="2b7d1-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b7d1-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="2b7d1-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-215">Открытие входящих и исходящих сеансов для аудио-и видеосеансов</span><span class="sxs-lookup"><span data-stu-id="2b7d1-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b7d1-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="2b7d1-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="2b7d1-217">Открыть компонент "исходящий трафик для сеансов аудио и видео"</span><span class="sxs-lookup"><span data-stu-id="2b7d1-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="2b7d1-218">Учетные записи пользователей и данные</span><span class="sxs-lookup"><span data-stu-id="2b7d1-218">User Accounts and Data</span></span>

<span data-ttu-id="2b7d1-219">В гибридном развертывании Lync Server 2013 любой пользователь, который вы хотите дома в Lync Online, сначала должен быть создан в локальном развертывании, чтобы учетная запись пользователя была создана в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="2b7d1-220">Затем вы можете переместить пользователя в Skype для бизнеса Online, который будет перемещать список контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="2b7d1-221">При синхронизации учетных записей пользователей между локальной средой Lync и развертыванием Lync Online с AD FS и DirSync необходимо синхронизировать учетные записи AD для всех пользователей Lync в Организации между локальными и подключенными развертываниями Lync, даже если пользователи не перемещаются в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="2b7d1-222">Если вы не синхронизируете всех пользователей, связь между локальными и сетевыми пользователями в Организации может работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b7d1-223">Если пользователь создается с помощью интернет-портала Office 365, учетная запись пользователя не будет синхронизироваться с локальными службами Active Directory и пользователь не будет существовать в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="2b7d1-224">Если вы уже создали пользователей в Lync Online и хотите настроить гибридную среду с локальным сервером Lync Server, ознакомьтесь со статьей <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальную среду Lync в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2b7d1-225">Следует также принять во внимание следующие моменты, касающиеся пользователя, при планировании гибридного развертывания.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="2b7d1-226">**Контакты пользователей лимит**   контактов для пользователей Lync Online — 250.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="2b7d1-227">Все контакты за пределами этого номера будут удалены из списка контактов пользователя при перемещении учетной записи в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="2b7d1-228">\*\*\*\*   Списки контактов и списки контактов пользователей для обмена мгновенными сообщениями, группы и списки управления доступом (ACL) переносятся вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="2b7d1-229">**Данные конференц-связи, содержимое собраний и запланированные собрания**   . это содержимое не переносится вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="2b7d1-230">Пользователи должны повторно запланировать собрания после переноса учетных записей в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="2b7d1-231">Политики и функции пользователей</span><span class="sxs-lookup"><span data-stu-id="2b7d1-231">User Policies and Features</span></span>

  - <span data-ttu-id="2b7d1-232">В гибридной среде Lync Server 2013 для пользователей можно включить поддержку мгновенных сообщений, голосовых вызовов и собраний в локальной или сетевой среде, но не одновременно.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="2b7d1-233">**Клиент Lync некоторые**     пользователи могут требовать новую версию клиента при перемещении в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="2b7d1-234">Для Office Communications Server 2007 R2 пользователи должны быть перемещены в пул Lync Server 2013 до миграции в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="2b7d1-235">Дополнительные сведения о поддержке клиентов можно найти в статье [клиенты для Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) и [Поддерживаемые клиенты Lync и конфигурации сетевых портов](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="2b7d1-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="2b7d1-236">**Локальные политики и локальная конфигурация (не пользователь)**   в сети и локальных политиках требуют отдельной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="2b7d1-237">Задание глобальных политик невозможно.</span><span class="sxs-lookup"><span data-stu-id="2b7d1-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


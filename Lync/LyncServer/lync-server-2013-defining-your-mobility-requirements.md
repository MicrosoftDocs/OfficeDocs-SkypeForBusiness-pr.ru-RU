---
title: 'Lync Server 2013: определение требований к мобильности'
description: 'Lync Server 2013: определение требований к мобильности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545545"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="58c6e-103">Определение требований к мобильности для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58c6e-103">Defining your mobility requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58c6e-104">_**Последнее изменение темы:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="58c6e-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="58c6e-105">На этапе планирования функции мобильной работы Lync Server 2013 при использовании мобильных клиентов Lync 2010 Mobile и Lync 2013 вы принимаете решения, которые определяют этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="58c6e-105">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="58c6e-106">Ниже приведены решения, которые необходимо принять во внимание.</span><span class="sxs-lookup"><span data-stu-id="58c6e-106">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="58c6e-107">**Хотите ли вы использовать автоматическое обнаружение для мобильных клиентов Lync Mobile?**</span><span class="sxs-lookup"><span data-stu-id="58c6e-107">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="58c6e-108">Если требуется поддержка автоматического обнаружения, необходимо создать новые записи внутренних и внешних доменных имен (DNS), добавить альтернативные имена субъектов в сертификаты на серверах переднего плана, режиссерах и обратном прокси-сервере, а также изменить существующие правила публикации на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="58c6e-108">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="58c6e-109">Дополнительные сведения см [в статье технические требования к мобильности в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="58c6e-109">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="58c6e-110">С помощью автоматического обнаружения пользователи могут автоматически находить веб-службы Lync Server 2013 из любого места внутри или за пределами корпоративной сети, не вводя URL-адреса в параметры мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="58c6e-110">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="58c6e-111">Если вместо автоматического обнаружения используются параметры вручную, мобильные пользователи должны вручную ввести следующие URL-адреса на мобильных устройствах:</span><span class="sxs-lookup"><span data-stu-id="58c6e-111">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="58c6e-112">https:// \<ExtPoolFQDN\> /autodiscover/autodiscoverservice.svc/root для внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="58c6e-112">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="58c6e-113">https:// \<IntPoolFQDN\> /аутодисковер/autodiscoverservice. svc/root для внутреннего доступа</span><span class="sxs-lookup"><span data-stu-id="58c6e-113">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="58c6e-p102">Майкрософт настоятельно рекомендует использовать автоматическое обнаружение. Настройка вручную в основном предназначена для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="58c6e-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="58c6e-116">**Если вы выбрали поддержку автоматического обнаружения, то будете ли вы обновлять альтернативные имена субъектов для каждого домена SIP в сертификатах на обратном-прокси сервере?**</span><span class="sxs-lookup"><span data-stu-id="58c6e-116">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="58c6e-117">Если у вас много доменов SIP, обновление общедоступных сертификатов на обратном прокси-сервере может очень дорого.</span><span class="sxs-lookup"><span data-stu-id="58c6e-117">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="58c6e-118">В этом случае можно выбрать реализацию автоматического обнаружения, чтобы при первоначальном запросе службы автообнаружения использовался HTTP-порт 80, а не HTTPS через порт 443.</span><span class="sxs-lookup"><span data-stu-id="58c6e-118">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="58c6e-119">Однако это не рекомендуемый подход.</span><span class="sxs-lookup"><span data-stu-id="58c6e-119">However, this is not the recommended approach.</span></span> <span data-ttu-id="58c6e-120">Если вы решили выбрать эту альтернативу, вам не нужно обновлять сертификаты на обратном прокси-сервере, но вам нужно создать правило веб-публикации для HTTP в порте 80.</span><span class="sxs-lookup"><span data-stu-id="58c6e-120">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="58c6e-121">Более подробную информацию можно узнать [в статье технические требования к мобильности в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="58c6e-121">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="58c6e-122">**Требуется ли поддержка внутренних и внешних мобильных клиентов Lync или только поддержка внутренних клиентов сети организации?**</span><span class="sxs-lookup"><span data-stu-id="58c6e-122">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="58c6e-p104">Если вы выберите поддержку внутренних и внешних мобильных клиентов, то мобильные устройства смогут получать доступ к функции мобильной связи из любого расположения. По умолчанию поддержка включена как для внутренних, так и для внешних клиентов сети организации.</span><span class="sxs-lookup"><span data-stu-id="58c6e-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="58c6e-125">Несмотря на то, что конфигурация по умолчанию разрешает трафик мобильных клиентов через внешний сайт, вы можете ограничить трафик мобильных клиентов во внутреннюю сеть организации.</span><span class="sxs-lookup"><span data-stu-id="58c6e-125">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="58c6e-126">В этом случае пользователи смогут использовать мобильные приложения Lync на своих устройствах только при нахождении внутри сети.</span><span class="sxs-lookup"><span data-stu-id="58c6e-126">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="58c6e-127">Для развертываний, поддерживающих мобильность с помощью службы Mobility MCX и Lync 2010 Mobile, запускается командлет **Set – CsMcxConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="58c6e-127">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="58c6e-128">Чтобы настроить мобильность только для внутреннего использования, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="58c6e-128">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58c6e-129">Для UCWA не требуются дополнительные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="58c6e-129">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="58c6e-130">UCWA не имеет эквивалентной внутренней конфигурации.</span><span class="sxs-lookup"><span data-stu-id="58c6e-130">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58c6e-131">Если вы используете &nbsp; сервер переднего плана Lync server 2013 или интерфейсный пул, а у <STRONG>вас нет</STRONG> серверов переднего плана Lync Server 2010 &nbsp; или интерфейсных пулов, <STRONG>нет необходимости в сохранении на основе файлов cookie</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="58c6e-131">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="58c6e-132">Если необходимо сохранить все &nbsp; серверы переднего плана Lync server 2010 или внешние пулы, то те же правила применяются в Lync server 2010 для сохраняемости на основе файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="58c6e-132">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="58c6e-133">**Требуется ли поддержка push-уведомлений для устройств компании Apple с ОС iOS и устройств Windows Phone?**</span><span class="sxs-lookup"><span data-stu-id="58c6e-133">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="58c6e-134">Если выбрана поддержка push-уведомлений, то устройства с ОС iOS компании Apple и устройства Windows Phone будут получать уведомления о событиях, произошедших во время отключения мобильного приложения.</span><span class="sxs-lookup"><span data-stu-id="58c6e-134">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="58c6e-135">Необходимо настроить пограничный сервер для связи Федерации с облачной службой push-уведомлений Lync Server, которая находится в центре обработки данных Lync Online, и выполнить командлет для включения push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="58c6e-135">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="58c6e-136">Если вы хотите обеспечить поддержку push-уведомлений по сети Wi-Fi, а также поддержку push-уведомлений по протоколу 3G или сетям данных поставщиков мобильных устройств, необходимо открыть порт 5223 исходящих сообщений в корпоративной сети Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="58c6e-136">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="58c6e-137">Поддержка push-уведомлений через сеть Wi-Fi доступна только мобильным устройствам, которые используют исключительно сеть Wi-Fi, а также мобильным устройствам с плохим приемом сигнала.</span><span class="sxs-lookup"><span data-stu-id="58c6e-137">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58c6e-138">Открыть порт TCP 5223 необходимо только при поддержке устройств Apple, работающих с мобильным клиентом Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="58c6e-138">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="58c6e-139">Если push-уведомления не поддерживаются, пользователи мобильных устройств Apple и Windows Phone не будут получать сведения о событиях, таких как приглашения для обмена мгновенными сообщениями или пропущенные сообщения, которые происходят, когда мобильное приложение неактивно.</span><span class="sxs-lookup"><span data-stu-id="58c6e-139">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58c6e-140">Мобильные клиенты Lync 2013 на устройствах Apple не требуют push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="58c6e-140">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="58c6e-141">Мобильные клиенты Lync 2013 на Windows Phone используют push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="58c6e-141">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="58c6e-142">При планировании push-уведомлений и расчетной палаты push-уведомлений действуют те же расчеты для Lync Mobile на Windows Phone и устройств Apple, которые не могут работать с мобильным клиентом Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="58c6e-142">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="58c6e-143">**Хотите ли вы, чтобы все пользователи могли получать доступ к мобильным возможностям, или вы хотите, чтобы пользователи могли указать, какие пользователи имеют доступ к этим функциям?**</span><span class="sxs-lookup"><span data-stu-id="58c6e-143">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="58c6e-144">В таблице описываются функции, доступные пользователям в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58c6e-144">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="58c6e-145">Параметры по умолчанию позволяют звонить через Work, разрешить голосовую связь по протоколу VoIP и включить мобильность.</span><span class="sxs-lookup"><span data-stu-id="58c6e-145">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="58c6e-146">Ниже приведен полный набор доступных параметров:</span><span class="sxs-lookup"><span data-stu-id="58c6e-146">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="58c6e-147">Имя компонента/параметра/область (имена параметров политики не могут быть одинаковыми)</span><span class="sxs-lookup"><span data-stu-id="58c6e-147">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="58c6e-148">Описание</span><span class="sxs-lookup"><span data-stu-id="58c6e-148">Description</span></span></th>
    <th><span data-ttu-id="58c6e-149">Представлено</span><span class="sxs-lookup"><span data-stu-id="58c6e-149">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="58c6e-150">Включение мобильной работы</span><span class="sxs-lookup"><span data-stu-id="58c6e-150">Enable Mobility</span></span></p>
    <p><span data-ttu-id="58c6e-151">Имя параметра: <code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="58c6e-151">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="58c6e-152">Область: Глобальная/site/User</span><span class="sxs-lookup"><span data-stu-id="58c6e-152">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-153">Административный параметр для управления пользователями в заданной области, в которой установлен Lync Mobile, если для политики задано значение false, пользователь не сможет войти в клиент.</span><span class="sxs-lookup"><span data-stu-id="58c6e-153">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="58c6e-154">Значение по умолчанию — true.</span><span class="sxs-lookup"><span data-stu-id="58c6e-154">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-155">Накопительный пакет обновления для Lync Server 2010: Ноябрь 2011</span><span class="sxs-lookup"><span data-stu-id="58c6e-155">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="58c6e-156">Включение внешнего голоса</span><span class="sxs-lookup"><span data-stu-id="58c6e-156">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="58c6e-157">Имя параметра: <code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="58c6e-157">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="58c6e-158">Область: Глобальная/site/User</span><span class="sxs-lookup"><span data-stu-id="58c6e-158">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-159">Управляет возможностью пользователя использовать функцию "позвонить с рабочего", которая позволяет пользователям совершать и принимать звонки с помощью рабочего номера, а не номера мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="58c6e-159">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="58c6e-160">Если задано значение false, пользователь не сможет совершать или принимать звонки, используя рабочий номер с мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="58c6e-160">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="58c6e-161">Значение по умолчанию — true</span><span class="sxs-lookup"><span data-stu-id="58c6e-161">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-162">Накопительный пакет обновления для Lync Server 2010: Ноябрь 2011</span><span class="sxs-lookup"><span data-stu-id="58c6e-162">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="58c6e-163">Включение IP-аудио и видео</span><span class="sxs-lookup"><span data-stu-id="58c6e-163">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="58c6e-164">Имя параметра: <code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="58c6e-164">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="58c6e-165">Область: Глобальная/site/User</span><span class="sxs-lookup"><span data-stu-id="58c6e-165">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-166">Определяет, может ли пользователь использовать VoIP для создания или приема голосовых или видеовызовов на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="58c6e-166">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="58c6e-167">Если задано значение false, пользователь не сможет совершать или принимать VoIP или видеозвонки на своих устройствах.</span><span class="sxs-lookup"><span data-stu-id="58c6e-167">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="58c6e-168">Значение по умолчанию — true.</span><span class="sxs-lookup"><span data-stu-id="58c6e-168">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-169">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58c6e-169">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="58c6e-170">Требовать WiFi для протокола IP Audio</span><span class="sxs-lookup"><span data-stu-id="58c6e-170">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="58c6e-171">Имя параметра: <code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="58c6e-171">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="58c6e-172">Область: Глобальная/site/User</span><span class="sxs-lookup"><span data-stu-id="58c6e-172">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-173">Этот параметр определяет, должен ли клиент совершать и принимать звонки по протоколу VoIP для Wi-Fi вместо сотовой сети передачи данных.</span><span class="sxs-lookup"><span data-stu-id="58c6e-173">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="58c6e-174">Если задано значение true, то пользователь может выполнять и принимать звонки VoIP только при подключении к сети Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="58c6e-174">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="58c6e-175">Значение по умолчанию: False.</span><span class="sxs-lookup"><span data-stu-id="58c6e-175">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-176">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58c6e-176">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="58c6e-177">Требовать WiFi для IP-видео</span><span class="sxs-lookup"><span data-stu-id="58c6e-177">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="58c6e-178">Имя параметра: <code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="58c6e-178">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="58c6e-179">Область: Глобальная/site/User</span><span class="sxs-lookup"><span data-stu-id="58c6e-179">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-180">Этот параметр определяет, должен ли клиент совершать и принимать видеозвонки на Wi-Fi, а не в сотовой сети передачи данных.</span><span class="sxs-lookup"><span data-stu-id="58c6e-180">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="58c6e-181">Если задано значение true, пользователь может выполнять и принимать видеозвонки только при подключении к сети Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="58c6e-181">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="58c6e-182">Значение по умолчанию: False.</span><span class="sxs-lookup"><span data-stu-id="58c6e-182">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="58c6e-183">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58c6e-183">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="58c6e-184">Описание параметров политики, которые можно настроить, и способов управления этими политиками, приведены в статье [New/CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set – CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get/CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), Grant + [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) и [Remove/CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="58c6e-184">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="58c6e-185">**Требуется ли предоставить пользователям, которые не включены для корпоративной голосовой связи, возможность присоединения к конференциям щелчком мыши?**</span><span class="sxs-lookup"><span data-stu-id="58c6e-185">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="58c6e-186">Чтобы пользователям были доступны функции мобильной связи и функция "Позвонить с рабочего", они должны быть включены для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="58c6e-186">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="58c6e-187">Тем не менее пользователи, не поддерживающие корпоративную голосовую связь, могут присоединяться к конференциям, щелкнув ссылку на мобильном устройстве, если им назначена соответствующая политика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="58c6e-187">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="58c6e-188">Для этих пользователей можно назначить определенную политику голосовой связи или убедиться в том, что существует глобальная политика или политика уровня сайта, применимые к ним.</span><span class="sxs-lookup"><span data-stu-id="58c6e-188">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="58c6e-189">Назначенная политика голосовой связи должна иметь записи и маршруты использования телефонной сети общего пользования (PSTN), определяющие области, к которым пользователи могут звонить для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="58c6e-189">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="58c6e-190">Дополнительные сведения о настройке политики голосовой связи, записей об использовании PSTN и маршрутах приведены [в статье Настройка политик голосовой связи, записей об использовании PSTN и маршрутов голосовой связи в Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="58c6e-190">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58c6e-191">Для пользователей мобильных устройств, которые хотят использовать команду "щелкните, чтобы присоединиться, требуется политика голосовой связи, а также связанные записи использования PSTN и маршруты голосовой связи, так как щелчок ссылки на мобильном устройстве приводит к исходящему вызову из Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58c6e-191">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="58c6e-192">См. также</span><span class="sxs-lookup"><span data-stu-id="58c6e-192">See Also</span></span>


[<span data-ttu-id="58c6e-193">Технические требования для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58c6e-193">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="58c6e-194">Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58c6e-194">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


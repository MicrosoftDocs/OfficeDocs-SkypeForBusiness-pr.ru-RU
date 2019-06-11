---
title: 'Lync Server 2013: определение требований к мобильной работе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="e4adc-102">Определение требований к мобильной работе для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4adc-102">Defining your mobility requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4adc-103">_**Тема последнего изменения:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="e4adc-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="e4adc-104">На этапе планирования для мобильной связи Lync Server 2013 при использовании мобильных клиентов Lync 2010 для мобильных устройств и Lync 2013 вы принимаете решения, которые определяют этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="e4adc-104">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="e4adc-105">Ниже указаны решения, которые необходимо принять во действия.</span><span class="sxs-lookup"><span data-stu-id="e4adc-105">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="e4adc-106">**Вы хотите использовать автоматическое обнаружение для мобильных клиентов Lync?**</span><span class="sxs-lookup"><span data-stu-id="e4adc-106">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="e4adc-107">Если вы хотите поддерживать автоматическое обнаружение, вам нужно создать новые записи внутренних и внешних доменных имен (DNS), добавить альтернативные имена субъектов в сертификаты на серверах переднего плана, режиссерах и обратном прокси и изменить существующие правила публикации. на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="e4adc-107">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="e4adc-108">Подробности можно найти [в разделе Технические требования для мобильных устройств на Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="e4adc-108">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="e4adc-109">С помощью автоматического обнаружения пользователи могут автоматически находить веб-службы Lync Server 2013 с любого места внутри организации или за ее пределами, не вводя URL-адреса в параметры мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="e4adc-109">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="e4adc-110">Если вместо автоматического обнаружения используются параметры вручную, мобильные пользователи должны вручную ввести следующие URL-адреса на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="e4adc-110">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="e4adc-111">https://\<екстпулфкдн\>/аутодисковер/аутодисковерсервице.СВК/Рут для внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="e4adc-111">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="e4adc-112">https://\<интпулфкдн\>/аутодисковер/Аутодисковерсервице. svc/root для внутреннего доступа</span><span class="sxs-lookup"><span data-stu-id="e4adc-112">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="e4adc-113">Настоятельно рекомендуется использовать автоматическое обнаружение.</span><span class="sxs-lookup"><span data-stu-id="e4adc-113">We strongly recommend using automatic discovery.</span></span> <span data-ttu-id="e4adc-114">Основное использование параметров вручную — для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e4adc-114">The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="e4adc-115">**Если вы решите поддерживать автоматическое обнаружение, хотите ли вы обновить сертификаты на обратном прокси с дополнительными именами для каждого домена SIP?**</span><span class="sxs-lookup"><span data-stu-id="e4adc-115">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="e4adc-116">Если у вас много доменов SIP, обновление открытых сертификатов на обратном прокси-сервере может значительно потребовать больших затрат.</span><span class="sxs-lookup"><span data-stu-id="e4adc-116">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="e4adc-117">Если это так, вы можете реализовать автоматическое обнаружение, чтобы первоначальное требование к службе автообнаружения использовало HTTP для порта 80, а не использовать HTTPS для порта 443.</span><span class="sxs-lookup"><span data-stu-id="e4adc-117">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="e4adc-118">Однако это не рекомендуемый подход.</span><span class="sxs-lookup"><span data-stu-id="e4adc-118">However, this is not the recommended approach.</span></span> <span data-ttu-id="e4adc-119">Если вы решили выбрать этот вариант, вам не нужно обновлять сертификаты на обратном прокси-сервере, но вам нужно создать правило веб-публикации для HTTP на порте 80.</span><span class="sxs-lookup"><span data-stu-id="e4adc-119">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="e4adc-120">Дополнительные сведения можно найти [в технических требованиях для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="e4adc-120">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="e4adc-121">**Нужно ли поддерживать мобильные клиенты Lync и внутренние, и внешние по отношению к корпоративной сети, а также поддерживать клиентов только внутри корпоративной сети?**</span><span class="sxs-lookup"><span data-stu-id="e4adc-121">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="e4adc-122">Если вы хотите поддерживать мобильные и внешние клиенты в сети, мобильные устройства смогут получать доступ к мобильным возможностям из любого места.</span><span class="sxs-lookup"><span data-stu-id="e4adc-122">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location.</span></span> <span data-ttu-id="e4adc-123">Конфигурацией по умолчанию является поддержка клиентов как внутренних, так и внешних в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="e4adc-123">The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="e4adc-124">Несмотря на то, что конфигурация по умолчанию обеспечивает трафик мобильных клиентов для прохождения по внешнему сайту, вы можете ограничить трафик мобильных клиентов в внутреннюю корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="e4adc-124">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="e4adc-125">Если вы ограничиваете трафик для внутренней сети, пользователи могут использовать мобильные приложения Lync на мобильных устройствах только в том случае, если они находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="e4adc-125">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="e4adc-126">Для развертываний, поддерживающих мобильность с помощью службы Mobility МККС и Lync 2010 Mobile, вы запускаете командлет **Set-ксмкксконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="e4adc-126">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="e4adc-127">Чтобы настроить мобильность только для внутреннего использования, вы можете использовать команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="e4adc-127">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4adc-128">Дополнительные конфигурации для УКВА не требуются.</span><span class="sxs-lookup"><span data-stu-id="e4adc-128">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="e4adc-129">УКВА не имеет эквивалентной внутренней конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4adc-129">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4adc-130">Если вы используете сервер переднего плана Lync&nbsp;Server 2013 и пулы интерфейсов, но у <STRONG>вас нет</STRONG> каких-либо внешних серверов&nbsp;Lync Server 2010 или интерфейсов переднего плана, <STRONG>для сохранения на основе файлов cookie не требуется</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e4adc-130">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="e4adc-131">Если вам нужно сохранить все серверы переднего плана&nbsp;lync Server 2010 и пулы внешних интерфейсов, эти правила по-прежнему применяются в lync Server 2010 для сохранения данных на основе файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="e4adc-131">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="e4adc-132">**Вы хотите поддерживать push-уведомления для устройств Apple iOS и Windows Phone?**</span><span class="sxs-lookup"><span data-stu-id="e4adc-132">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="e4adc-133">Если вы поддерживает Push-уведомления, Поддерживаемые устройства Apple iOS и телефоны Windows получают уведомление о событиях, происходящих при неактивном мобильном приложении.</span><span class="sxs-lookup"><span data-stu-id="e4adc-133">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="e4adc-134">Необходимо настроить пограничный сервер так, чтобы он имел отношение Федерации с облачной службой push-уведомлений Lync Server, которая находится в центре обработки данных Lync Online, и выполнить командлет для включения push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e4adc-134">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="e4adc-135">Если вы хотите, чтобы в сети Wi-Fi поддерживались извещающие уведомления, а также поддержка push-уведомлений по протоколам 3G или сетей данных поставщиков мобильных устройств, необходимо открыть порт 5223 исходящих в корпоративной сети Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="e4adc-135">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="e4adc-136">Поддержка извещающих уведомлений в сети Wi-Fi поддерживает мобильные устройства, использующие только Wi-Fi и мобильные устройства с низким приемом.</span><span class="sxs-lookup"><span data-stu-id="e4adc-136">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4adc-137">Открытие порта TCP 5223 является обязательным только в том случае, если поддерживаются устройства Apple, работающие на мобильном клиенте Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e4adc-137">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="e4adc-138">Если push-уведомления не поддерживаются, пользователи мобильных устройств Apple и Windows Phone не будут получать сведения о событиях (например, о мгновенных сообщениях или пропущенных сообщениях), которые происходят при неактивном мобильном приложении.</span><span class="sxs-lookup"><span data-stu-id="e4adc-138">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4adc-139">Мобильные клиенты Lync 2013 на устройствах Apple не требуют push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e4adc-139">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="e4adc-140">Мобильные клиенты Lync 2013 на устройствах с Windows Phone используют push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="e4adc-140">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="e4adc-141">Планирование push-уведомлений и расчетную палату для push-уведомлений остаются неизменными для Lync Mobile на устройствах с Windows Phone и Apple, которые не имеют возможности запустить мобильный клиент Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e4adc-141">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="e4adc-142">**Вы хотите, чтобы все пользователи имели доступ к мобильным возможностям, или вы хотите предоставить пользователям доступ к этим функциям?**</span><span class="sxs-lookup"><span data-stu-id="e4adc-142">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="e4adc-143">В таблице описаны возможности, доступные пользователям в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4adc-143">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="e4adc-144">Значения по умолчанию позволяют звонить через Work, разрешить голосовую почту по протоколу IP (VoIP) и включить мобильное подключение.</span><span class="sxs-lookup"><span data-stu-id="e4adc-144">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="e4adc-145">Ниже приведен полный набор доступных параметров.</span><span class="sxs-lookup"><span data-stu-id="e4adc-145">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e4adc-146">Имя функции/параметра/область (имена параметров политики могут отличаться от указанных)</span><span class="sxs-lookup"><span data-stu-id="e4adc-146">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="e4adc-147">Описание</span><span class="sxs-lookup"><span data-stu-id="e4adc-147">Description</span></span></th>
    <th><span data-ttu-id="e4adc-148">Внедрил</span><span class="sxs-lookup"><span data-stu-id="e4adc-148">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="e4adc-149">Включение мобильной связи</span><span class="sxs-lookup"><span data-stu-id="e4adc-149">Enable Mobility</span></span></p>
    <p><span data-ttu-id="e4adc-150">Имя параметра:<code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="e4adc-150">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="e4adc-151">Область действия: Global/site/User</span><span class="sxs-lookup"><span data-stu-id="e4adc-151">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-152">Административный параметр для управления пользователями в заданной области с установленным приложением Lync Mobile, если для политики задано значение false, пользователи не смогут войти в клиент.</span><span class="sxs-lookup"><span data-stu-id="e4adc-152">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="e4adc-153">Значение по умолчанию — true.</span><span class="sxs-lookup"><span data-stu-id="e4adc-153">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-154">Накопительное обновление для Lync Server 2010: Ноябрь 2011</span><span class="sxs-lookup"><span data-stu-id="e4adc-154">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e4adc-155">Включить внешний голос</span><span class="sxs-lookup"><span data-stu-id="e4adc-155">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="e4adc-156">Имя параметра:<code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="e4adc-156">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="e4adc-157">Область действия: Global/site/User</span><span class="sxs-lookup"><span data-stu-id="e4adc-157">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-158">Управление способностью пользователя использовать функцию "звонок через работу", которая позволяет пользователям совершать и принимать звонки с помощью рабочего номера вместо номера мобильного.</span><span class="sxs-lookup"><span data-stu-id="e4adc-158">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="e4adc-159">Если задано значение false, пользователь не сможет совершать и принимать звонки с помощью своего рабочего номера на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="e4adc-159">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="e4adc-160">Значение по умолчанию — истина</span><span class="sxs-lookup"><span data-stu-id="e4adc-160">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-161">Накопительное обновление для Lync Server 2010: Ноябрь 2011</span><span class="sxs-lookup"><span data-stu-id="e4adc-161">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e4adc-162">Включение IP-аудио/видео</span><span class="sxs-lookup"><span data-stu-id="e4adc-162">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="e4adc-163">Имя параметра:<code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="e4adc-163">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="e4adc-164">Область действия: Global/site/User</span><span class="sxs-lookup"><span data-stu-id="e4adc-164">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-165">Определяет, может ли пользователь использовать VoIP для совершения и приема голосовых и видеозвонков на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="e4adc-165">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="e4adc-166">Если задано значение false, пользователь не сможет совершать и принимать звонки по протоколу VoIP или видеосвязь на своем устройстве.</span><span class="sxs-lookup"><span data-stu-id="e4adc-166">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="e4adc-167">Значение по умолчанию — true.</span><span class="sxs-lookup"><span data-stu-id="e4adc-167">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-168">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4adc-168">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e4adc-169">Использование WiFi для интернет-аудио</span><span class="sxs-lookup"><span data-stu-id="e4adc-169">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="e4adc-170">Имя параметра:<code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="e4adc-170">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="e4adc-171">Область действия: Global/site/User</span><span class="sxs-lookup"><span data-stu-id="e4adc-171">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-172">Этот параметр определяет, должен ли клиент совершать и принимать звонки по протоколу VoIP для WiFi вместо сотовой сети передачи данных.</span><span class="sxs-lookup"><span data-stu-id="e4adc-172">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="e4adc-173">Если установлено значение true, пользователи могут звонить и принимать звонки VoIP только при подключении к сети Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="e4adc-173">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="e4adc-174">По умолчанию используется значение false.</span><span class="sxs-lookup"><span data-stu-id="e4adc-174">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-175">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4adc-175">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e4adc-176">Использование WiFi для интернет-видео</span><span class="sxs-lookup"><span data-stu-id="e4adc-176">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="e4adc-177">Имя параметра:<code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="e4adc-177">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="e4adc-178">Область действия: Global/site/User</span><span class="sxs-lookup"><span data-stu-id="e4adc-178">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-179">Этот параметр определяет, должен ли клиент совершать и принимать видеозвонки в Wi-Fi, а не в сотовой сети передачи данных.</span><span class="sxs-lookup"><span data-stu-id="e4adc-179">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="e4adc-180">Если установлено значение true, пользователь может принимать и принимать видеозвонки только при подключении к сети Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="e4adc-180">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="e4adc-181">По умолчанию используется значение false.</span><span class="sxs-lookup"><span data-stu-id="e4adc-181">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="e4adc-182">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4adc-182">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="e4adc-183">Описание параметров политики, которые можно настроить, и способы управления этими политиками: " [создать ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)", " [Set-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)", " [Get-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)", " [Grant-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) " и [ Remove-Ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="e4adc-183">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="e4adc-184">**Вы хотите, чтобы пользователи, которым не разрешено использовать корпоративную голосовую почту, смогли присоединиться к конференциям, нажмите кнопку "ОК".**</span><span class="sxs-lookup"><span data-stu-id="e4adc-184">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="e4adc-185">Чтобы пользователи могли получать доступ к функциям мобильных устройств и звонить через работу, они должны быть включены для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e4adc-185">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="e4adc-186">Тем не менее пользователи, не поддерживающие корпоративную голосовую почту, могут присоединиться к конференциям, перейдя по ссылке на мобильном устройстве, если им назначена соответствующая политика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e4adc-186">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="e4adc-187">Вы можете назначить для этих пользователей специальную политику голосовой связи или убедиться, что в ней есть глобальная политика или политика уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="e4adc-187">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="e4adc-188">Назначаемая вами политика голосовой связи должна иметь записи использования общедоступной телефонной сети (КТСОП) и маршруты, определяющие области, в которых пользователи могут звонить для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="e4adc-188">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="e4adc-189">Подробнее об установке политики голосовой связи, записей использования PSTN и маршрутов можно узнать [в разделе Настройка политик голосовой связи, записей использования PSTN и голосовых маршрутов в Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="e4adc-189">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4adc-190">Мобильные пользователи, которым нужно присоединиться, требуют политики голосовой связи, а также связанные записи использования PSTN и голосовые маршруты, так как при нажатии ссылки на мобильном устройстве происходит исходящий вызов из Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4adc-190">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4adc-191">См. также</span><span class="sxs-lookup"><span data-stu-id="e4adc-191">See Also</span></span>


[<span data-ttu-id="e4adc-192">Технические требования для организации мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4adc-192">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="e4adc-193">Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4adc-193">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: требования к сертификатам для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda45706b8c55bf99120ec3776702060998a6921
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ed416-102">Требования к сертификатам для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed416-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed416-103">_**Последнее изменение темы:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="ed416-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="ed416-104">Программное обеспечение Microsoft Lync Server 2013 Communications поддерживает использование единого общедоступного сертификата для внешних интерфейсов Access и пограничных интерфейсов веб-конференций, а также службы проверки подлинности аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="ed416-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="ed416-105">Внутренние пограничные интерфейсы, как правило, используют закрытый сертификат, выпущенный внутренним центром сертификации, но также могут использовать общедоступный сертификат, при условии что он выпущен доверенным общим ЦС.</span><span class="sxs-lookup"><span data-stu-id="ed416-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="ed416-106">Обратный прокси-сервер в развертывании использует общедоступный сертификат и выполняет шифрование обмена данными между обратным прокси-сервером и клиентами, а также между обратным прокси-сервером и внутренними серверами по протоколу HTTP (TLS через HTTP).</span><span class="sxs-lookup"><span data-stu-id="ed416-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="ed416-107">Ниже приведены требования к общедоступным сертификатам, используемым для внешних пограничных интерфейсов доступа и веб-конференций и службы проверки подлинности A/V.</span><span class="sxs-lookup"><span data-stu-id="ed416-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="ed416-108">Сертификат должен быть выпущен утвержденным общим ЦС, который поддерживает альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="ed416-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="ed416-109">Подробные сведения можно найти в статье 929395 базы знаний Майкрософт "Партнеры сертификатов Объединенных коммуникаций для Exchange Server и Communications Server" по адресу [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="ed416-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="ed416-p103">Если сертификат будет использоваться для пограничного пула, он должен создаваться как экспортируемый; один и тот же сертификат должен использоваться на каждом пограничном сервере в пограничном пуле. Требование экспортируемого закрытого ключа связано с работой службы проверки подлинности A/V, которая должна использовать один и тот же закрытый ключ для всех пограничных серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="ed416-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="ed416-112">Если вы хотите максимально увеличить время работы служб аудио-и видеоданных, ознакомьтесь с требованиями к сертификатам для реализации несвязанного сертификата пограничного сервера аудио-и видеоданных (то есть, отдельного сертификата пограничной службы аудио-и видеосвязи в других внешних целях сертификации).</span><span class="sxs-lookup"><span data-stu-id="ed416-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="ed416-113">Сведения об [изменениях в Lync server 2013, влияющих на планирование пограничных серверов](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [запланируйте сертификаты пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) и [промежуточные сертификаты OAuth и сертификаты OAuth в Lync Server 2013 using Set — CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="ed416-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="ed416-114">Имя субъекта сертификата — это полное доменное имя внешнего интерфейса службы пограничного сервера доступа (полное доменное имя) или виртуальный IP-адрес аппаратного балансировщика нагрузки (например, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ed416-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="ed416-115">).</span><span class="sxs-lookup"><span data-stu-id="ed416-115">).</span></span> <span data-ttu-id="ed416-116">Имя субъекта не может содержать подстановочный знак, оно должно быть явным.</span><span class="sxs-lookup"><span data-stu-id="ed416-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed416-117">Для Lync Server 2013 это не обязательно, но рекомендуется по-прежнему для совместимости с Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="ed416-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="ed416-118">Список альтернативных имен субъекта содержит полные доменные имена следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="ed416-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="ed416-119">Внешний интерфейс службы пограничной службы доступа или виртуальный IP-адрес аппаратного балансировщика нагрузки (например, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ed416-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ed416-120">Даже если в качестве имени субъекта сертификата указано полное доменное имя пограничного интерфейса доступа, альтернативное имя субъекта должно также содержать полное доменное имя пограничного интерфейса, так как протокол TLS пропускает имя субъекта и использует записи альтернативных имен субъекта для проверки.</span><span class="sxs-lookup"><span data-stu-id="ed416-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="ed416-121">Имя внешнего пограничного интерфейса веб-конференций или виртуальный IP-адрес аппаратного балансировщика нагрузки (например, webcon.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ed416-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="ed416-122">Если используются функции автонастройки клиентов или федерации, необходимо также включить полные доменные имена всех SIP-доменов, используемых в организации (например, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="ed416-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="ed416-123">Пограничная служба аудио-и видеоданных не использует записи имени субъекта или альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="ed416-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed416-124">Порядок полных доменных имен в списке альтернативных имен субъектов не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="ed416-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="ed416-p106">При развертывании нескольких пограничных серверов с балансировкой нагрузки в сайте, сертификаты службы проверки подлинности A/V, установленные на каждом пограничном сервере, должны быть выпущены одним ЦС и должны иметь один и тот же закрытый ключ. Учтите, что закрытый ключ сертификата должен быть экспортируемым, независимо от того, используется ли он на одном или на нескольких пограничных серверах. Кроме того, ключ должен быть экспортируемым при запросе сертификата с любого компьютера кроме пограничного сервера. Поскольку служба проверки подлинности A/V не использует имя субъекта или альтернативное имя субъекта, можно использовать один и тот же пограничный сертификат, если он отвечает требованиям к имени и альтернативному имени субъекта для пограничных серверов доступа и веб-конференции, и закрытый ключ сертификата является экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="ed416-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="ed416-129">Требования к закрытому (или общедоступному) сертификату для внутреннего пограничного интерфейса включают перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="ed416-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="ed416-130">Сертификат может быть выпущен внутренним или утвержденным общим центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="ed416-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="ed416-p107">Имя субъекта сертификата, как правило, является полным доменным именем внутреннего пограничного интерфейса или виртуальным IP-адресом аппаратного балансировщика нагрузки (например, lsedge.contoso.com). Тем не менее, для внутреннего пограничного интерфейса можно использовать групповой сертификат.</span><span class="sxs-lookup"><span data-stu-id="ed416-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="ed416-133">Не требуется создавать список альтернативных имен субъектов.</span><span class="sxs-lookup"><span data-stu-id="ed416-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="ed416-134">Требования обратного прокси-сервера в развертывании включают следующие:</span><span class="sxs-lookup"><span data-stu-id="ed416-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="ed416-135">доступ внешних пользователей к содержимому собраний для собраний;</span><span class="sxs-lookup"><span data-stu-id="ed416-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="ed416-136">доступ внешних пользователей для расширения и отображения членов группы распространения;</span><span class="sxs-lookup"><span data-stu-id="ed416-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="ed416-137">доступ внешних пользователей к загружаемым файлам из службы адресной книги;</span><span class="sxs-lookup"><span data-stu-id="ed416-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="ed416-138">Доступ внешних пользователей к клиенту Lync Web App</span><span class="sxs-lookup"><span data-stu-id="ed416-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="ed416-139">доступ внешних пользователей к веб-странице параметров конференц-связи с телефонным подключением;</span><span class="sxs-lookup"><span data-stu-id="ed416-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="ed416-140">доступ внешних пользователей к службе сведений о расположении;</span><span class="sxs-lookup"><span data-stu-id="ed416-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="ed416-141">доступ внешних устройств к службе обновления устройств и получению обновлений.</span><span class="sxs-lookup"><span data-stu-id="ed416-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="ed416-142">Обратный прокси-сервер публикует URL-адрес внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="ed416-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="ed416-143">URL-адреса веб-компонентов определяются на директоре, сервере переднего плана или интерфейсном пуле в качестве **внешних веб-служб** в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="ed416-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="ed416-144">Подстановочные записи поддерживаются в поле альтернативного имени субъекта сертификата, назначенного обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="ed416-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="ed416-145">Дополнительные сведения о настройке запроса на сертификат для обратного прокси-сервера приведены [в разделе Request and Configure the обратный HTTP-прокси в Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="ed416-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ed416-146">См. также</span><span class="sxs-lookup"><span data-stu-id="ed416-146">See Also</span></span>


[<span data-ttu-id="ed416-147">Поддержка сертификатов с подстановочными знаками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed416-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


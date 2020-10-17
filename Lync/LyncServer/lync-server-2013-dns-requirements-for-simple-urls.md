---
title: 'Lync Server 2013: требования к DNS для простых URL-адресов'
description: 'Lync Server 2013: требования DNS для простых URL-адресов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564965"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="5630c-103">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5630c-103">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5630c-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5630c-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5630c-105">Lync Server 2013 поддерживает простые URL-адреса, которые упрощают присоединение к собраниям для пользователей, а также упрощают работу средств администрирования Lync Server для администраторов.</span><span class="sxs-lookup"><span data-stu-id="5630c-105">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="5630c-106">Подробные сведения об простых URL-адресах приведены [в статье Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="5630c-106">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="5630c-107">Lync Server поддерживает три следующих простых URL-адреса: "Встреча", "Входящие звонки" и "Администратор". Необходимо настроить простые URL-адреса для соответствия и телефонного подключения, а простой URL-адрес администратора — необязательный.</span><span class="sxs-lookup"><span data-stu-id="5630c-107">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="5630c-108">Записи службы доменных имен (DNS), необходимые для поддержки простых URL-адресов, зависят от того, как именно вы определили эти простые URL-адреса, а также необходима ли поддержка аварийного восстановления для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="5630c-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="5630c-109">Вариант 1 простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5630c-109">Simple URL Option 1</span></span>

<span data-ttu-id="5630c-110">В варианте 1 для каждого простого URL-адреса вы создаете новый базовый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="5630c-110">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5630c-p103">Когда пользователь выбирает ссылку собрания с простым URL-адресом, сервер, в который разрешается запись A DNS, определяет правильное клиентское программное обеспечение, которое необходимо запустить. После запуска этого клиентского программного обеспечения оно автоматически соединяется с пулом, где размещается конференция. В этом случае пользователи направляются на подходящий сервер с содержимым собрания независимо от того, в какой сервер или пул разрешаются записи A DNS простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="5630c-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="5630c-114">Вариант 1 простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5630c-114">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5630c-115"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="5630c-115"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="5630c-116"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="5630c-116"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5630c-117">Согласно</span><span class="sxs-lookup"><span data-stu-id="5630c-117">Meet</span></span></p></td>
<td><p><span data-ttu-id="5630c-118">https://meet.contoso.com, https://meet.fabrikam.com и так далее (по одному для каждого домена SIP в организации).</span><span class="sxs-lookup"><span data-stu-id="5630c-118">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5630c-119">Телефонное подключение</span><span class="sxs-lookup"><span data-stu-id="5630c-119">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5630c-120">Администратор</span><span class="sxs-lookup"><span data-stu-id="5630c-120">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5630c-121">Если вы используете вариант 1, вам необходимо определить следующее:</span><span class="sxs-lookup"><span data-stu-id="5630c-121">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="5630c-p104">Для каждого простого URL-адреса Meet вам требуется запись A DNS, которая разрешает этот URL-адрес в IP-адрес Директора (если вы его развернули). В противном случае он должен разрешаться в IP-адрес подсистемы балансировки нагрузки интерфейсного пула. Если вы еще не развернули пул и используете развертывание сервера Standard Edition, запись A DNS должна разрешаться в IP-адрес одного сервера Standard Edition в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5630c-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="5630c-125">Если в вашей организации более одно домена SIP и вы используете данный вариант, вам следует создать простые URL-адреса Meet для каждого домена SIP и использовать по записи A DNS на каждый простой URL-адрес Meet.</span><span class="sxs-lookup"><span data-stu-id="5630c-125">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="5630c-126">Например, если у вас есть как contoso.com, так и fabrikam.com, вы создадите записи A DNS для обоих https://meet.contoso.com и https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="5630c-126">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="5630c-127">Если же у вас имеется несколько доменов SIP и вы хотите до минимума сократить потребность в записях DNS и сертификатах для этих простых URL-адресов, воспользуйтесь описанным ниже вариантом 3.</span><span class="sxs-lookup"><span data-stu-id="5630c-127">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="5630c-p106">Для простого URL-адреса Dial-in вам требуется запись A DNS, которая разрешает этот URL-адрес в IP-адрес Директора (если вы его развернули). В противном случае он должен разрешаться в IP-адрес подсистемы балансировки нагрузки интерфейсного пула. Если вы еще не развернули пул и используете развертывание сервера Standard Edition, запись A DNS должна разрешаться в IP-адрес одного сервера Standard Edition в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5630c-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="5630c-p107">Простой URL-адрес Admin предназначен только для внутреннего использования и требует запись A DNS, которая разрешает этот URL-адрес в IP-адрес Директора (если вы его развернули). В противном случае он должен разрешаться в IP-адрес подсистемы балансировки нагрузки интерфейсного пула. Если вы еще не развернули пул и используете развертывание сервера Standard Edition, запись A DNS должна разрешаться в IP-адрес одного сервера Standard Edition в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5630c-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="5630c-135">Вариант 2 простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5630c-135">Simple URL Option 2</span></span>

<span data-ttu-id="5630c-p108">В варианте 2 все простые URL-адреса Meet, Dial-in и Admin имеют общий базовый URL-адрес, например lync.contoso.com. Таким образом, для этих простых URL-адресов вам требуется только одна запись A DNS, которая разрешает lync.contoso.com в IP-адрес пула Директоров или интерфейсный пул. Если вы еще не развернули пул и используете развертывание сервера Standard Edition, запись A DNS должна разрешаться в IP-адрес одного сервера Standard Edition в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5630c-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="5630c-139">Если в вашей организации более одно домена SIP, вам все равно следует создать простые URL-адреса Meet для каждого домена SIP и использовать по записи A DNS на каждый простой URL-адрес Meet.</span><span class="sxs-lookup"><span data-stu-id="5630c-139">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="5630c-140">Хотя все три простых URL-адреса в данном примере основаны на lync.contoso.com, дополнительный простой URL-адрес Meet для fabrikam.com настраивается с использованием другого базового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="5630c-140">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="5630c-141">В этом примере необходимо создать записи A DNS для обоих типов https://lync.contoso.com и https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="5630c-141">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="5630c-142">В вариант 3 простого URL-адреса показан другой способ именования и обработки записей A DNS при наличии нескольких доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="5630c-142">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="5630c-143">Вариант 2 простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5630c-143">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5630c-144"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="5630c-144"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="5630c-145"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="5630c-145"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5630c-146">Согласно</span><span class="sxs-lookup"><span data-stu-id="5630c-146">Meet</span></span></p></td>
<td><p><span data-ttu-id="5630c-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet и так далее (по одному для каждого домена SIP в организации).</span><span class="sxs-lookup"><span data-stu-id="5630c-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5630c-148">Телефонное подключение</span><span class="sxs-lookup"><span data-stu-id="5630c-148">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5630c-149">Администратор</span><span class="sxs-lookup"><span data-stu-id="5630c-149">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="5630c-150">Вариант 3 простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5630c-150">Simple URL Option 3</span></span>

<span data-ttu-id="5630c-p110">Вариант 3 наиболее удобен в том случае, если у вас имеется множество доменов SIP и вы хотите, чтобы все они имели отдельные простые URL-адреса при минимальной потребности в записях DNS и сертификатах для этих простых URL-адресов. В данном примере вам требуется только одна запись A DNS, которая разрешает lync.contoso.com в IP-адрес пула Директоров или интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="5630c-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="5630c-153">Вариант 3 простого URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5630c-153">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5630c-154"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="5630c-154"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="5630c-155"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="5630c-155"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5630c-156">Согласно</span><span class="sxs-lookup"><span data-stu-id="5630c-156">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5630c-157">Телефонное подключение</span><span class="sxs-lookup"><span data-stu-id="5630c-157">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5630c-158">Администратор</span><span class="sxs-lookup"><span data-stu-id="5630c-158">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="5630c-159">Вариант аварийного восстановления для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5630c-159">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="5630c-160">Если у вас есть несколько сайтов с интерфейсными пулами и поставщик DNS поддерживает GeoDNS, можно настроить записи DNS для простых URL-адресов, чтобы обеспечить поддержку аварийного восстановления, чтобы функции простого URL-адреса продолжались, даже если один пул переднего плана отключается.</span><span class="sxs-lookup"><span data-stu-id="5630c-160">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="5630c-161">Этот компонент аварийного восстановления поддерживает простые URL-адреса Meet и Dial-In.</span><span class="sxs-lookup"><span data-stu-id="5630c-161">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="5630c-p112">Для выполнения этой настройки создайте два адреса GeoDNS. Каждый адрес содержит две записи DNS A или CNAME, которые разрешаются в два пула, спаренных в целях аварийного восстановления. Один адрес GeoDNS используется для внутреннего доступа и разрешается в полное доменное имя внутренней веб-службы или IP-адрес балансировщика нагрузки для двух пулов. Другой адрес GeoDNS используется для внешнего доступа и разрешается в полное доменное имя внешней веб-службы или IP-адрес балансировщика нагрузки для двух пулов. Ниже приведен пример простого URL-адреса Meet для полных имен доменов этих пулов.</span><span class="sxs-lookup"><span data-stu-id="5630c-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="5630c-167">Затем создайте записи CNAME, которые разрешают простой URL-адрес meet (например, meet.contoso.com) в два адреса GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="5630c-167">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5630c-168">Если сеть поддерживает <EM>разворот пакетов</EM> (маршрутизация всего трафика простых URL-адресов через внешнюю ссылку, включая трафик из организации), можно просто настроить внешний адрес GeoDNS и разрешать простой URL-адрес Meet только во внешний адрес.</span><span class="sxs-lookup"><span data-stu-id="5630c-168">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="5630c-169">При использовании этого метода можно настроить каждый адрес GeoDNS для использования метода циклического перебора для распределения запросов между двумя пулами или для подключения в основном к одному пулу (например, к пулу, который географически ближе расположен) и использования другого пула только в случае сбоя подключения.</span><span class="sxs-lookup"><span data-stu-id="5630c-169">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="5630c-170">Можно задать ту же конфигурацию для простого URL-адреса Dial-In.</span><span class="sxs-lookup"><span data-stu-id="5630c-170">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="5630c-171">Для этого создайте дополнительные записи, такие как в предыдущем примере, подставив `dialin` `meet` в записях DNS.</span><span class="sxs-lookup"><span data-stu-id="5630c-171">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="5630c-172">Для простого URL-адреса Admin используйте один из трех вариантов, приведенных выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5630c-172">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="5630c-173">После настройки этой конфигурации необходимо использовать приложение мониторинга для настройки мониторинга HTTP на предмет сбоев.</span><span class="sxs-lookup"><span data-stu-id="5630c-173">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="5630c-174">Для внешнего доступа следите, чтобы убедиться в том, что запросы на автообнаружение по протоколу HTTPS получают самообнаружение для внешнего веб-адреса полного доменного имени или IP-адреса подсистемы балансировки нагрузки для двух пулов.</span><span class="sxs-lookup"><span data-stu-id="5630c-174">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="5630c-175">Например, следующие запросы не должны содержать какие-либо заголовки **ACCEPT** и должны возвращать **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="5630c-175">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="5630c-p115">Для внутреннего доступа следует отслеживать порт 5061 на полном доменном имени внутреннего интерфейса или IP-адресе балансировщика нагрузки применительно к двум пулам. Если обнаруживаются какие-либо проблемы с подключением, на виртуальном IP-адресе этих пулов должны быть закрыты порты 80, 443 и 444.</span><span class="sxs-lookup"><span data-stu-id="5630c-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


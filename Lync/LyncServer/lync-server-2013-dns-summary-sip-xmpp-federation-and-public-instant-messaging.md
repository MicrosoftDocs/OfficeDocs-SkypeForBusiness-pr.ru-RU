---
title: Сводка по DNS — SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b7b6f9639a43a1eb16623fe0ea174b6e932ab5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="69e58-102">Сводка по DNS — SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69e58-103">_**Последнее изменение темы:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="69e58-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="69e58-104">Записи доменных имен (DNS), которые необходимы для определения Федерации с партнерами Office Communications Server или Lync Server, определяются вашим решением для разрешения автоматического обнаружения DNS для домена другими перспективными партнерами.</span><span class="sxs-lookup"><span data-stu-id="69e58-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="69e58-105">Если вы публикуете \_сипфедератионтлс. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="69e58-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="69e58-106">\* \<Имя\> домена SIP\* Запись SRV, любой другой федеративный домен SIP будет иметь возможность "Обнаружение" Федерации.</span><span class="sxs-lookup"><span data-stu-id="69e58-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="69e58-107">Вы можете контролировать, какие федеративные домены могут связываться с вами с помощью параметров "разрешить домены и заблокированные домены" в панели управления Lync Server, а также путем установки конфигурации разрешенных или заблокированных доменов с помощью командной консоли Lync Server и командлетов **Get**, **Set**, **New**, **reCsAllowedDomain** и **CsBlockedDomain** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69e58-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="69e58-108">Дополнительные сведения о том, как настроить эти параметры и использование командлетов PowerShell, можно найти в разделе **связанные темы** в конце этой статьи.</span><span class="sxs-lookup"><span data-stu-id="69e58-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="69e58-109">В таблице Сводка записей DNS показаны необходимые записи для открытой или обнаруживаемой Федерации.</span><span class="sxs-lookup"><span data-stu-id="69e58-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="69e58-110">Если вы не хотите внедрять обнаружение Федерации, вы можете не настроить \_сипфедератионтлс. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="69e58-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="69e58-111">*Запись имени\> домена SIP. \<*</span><span class="sxs-lookup"><span data-stu-id="69e58-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="69e58-112">Существуют определенные сценарии, в которых необходим _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="69e58-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="69e58-113"><EM> &lt;Имя&gt; домена SIP</EM> Запись SRV, но вы не хотите иметь обнаруживаемую Федерацию.</span><span class="sxs-lookup"><span data-stu-id="69e58-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="69e58-114">Один из таких экземпляров заключается в том, где вы развернули мобильность для пользователей.</span><span class="sxs-lookup"><span data-stu-id="69e58-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="69e58-115">The Clearinghouse Push push-уведомлений (PNCH) — это специальный тип Федерации, который используется для мобильных клиентов Microsoft Lync в Apple iPhone или iPad с помощью мобильного клиента Lync 2010 или Windows Phone с помощью мобильных клиентов Lync 2010 Mobile или Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="69e58-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="69e58-116">_Sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="69e58-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="69e58-117"><EM> &lt;Имя&gt; домена SIP</EM> Запись SRV используется в случае мобильных устройств и Push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="69e58-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="69e58-118">Чтобы устранить эту ошибку и контролировать свое обнаружение, снимите флажок <STRONG>включить обнаружение домена партнера</STRONG> , чтобы отключить обнаружение.</span><span class="sxs-lookup"><span data-stu-id="69e58-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="69e58-119">Чтобы настроить расширенный протокол обмена сообщениями (XMPP) для развертывания, создайте две записи службы доменных имен (DNS) на внешнем DNS-сервере, которые будут разрешать записи в пограничной службе доступа пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="69e58-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="69e58-120">При настройке службы доменных имен (DNS) для подключения к общедоступным службам обмена мгновенными сообщениями вы обнаружите, что конфигурация, поддерживающая внешних пользователей, будет поддерживать связь общедоступных МГНОВЕНных сообщений.</span><span class="sxs-lookup"><span data-stu-id="69e58-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="69e58-121">Если вы уже настроили пограничный сервер или пограничный пул, у вас должны быть записи DNS, необходимые для поддержки подключения к общедоступным системам обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="69e58-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="69e58-122">Сводка по DNS — Федерация SIP, включая общедоступные службы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="69e58-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69e58-123">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="69e58-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="69e58-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="69e58-124">FQDN</span></span></th>
<th><span data-ttu-id="69e58-125">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="69e58-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="69e58-126">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="69e58-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69e58-127">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="69e58-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="69e58-128">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="69e58-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="69e58-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="69e58-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="69e58-130">Внешний интерфейс службы пограничного доступа, необходимый для автоматического обнаружения DNS для Федерации другим потенциальным партнерам Федерации, называется "разрешенные домены SIP" (называемые расширенной Федерацию в предыдущих выпусках). Повторять при необходимости для всех доменов SIP с пользователями с включенной поддержкой Lync</span><span class="sxs-lookup"><span data-stu-id="69e58-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="69e58-131">Эта SRV-запись требуется для расчетной палаты push-уведомлений и мобильности.</span><span class="sxs-lookup"><span data-stu-id="69e58-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="69e58-132">В случаях, когда имеется несколько доменов SIP, создайте и опубликуйте запись SRV для каждого домена, у которого будут клиенты Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="69e58-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="69e58-133">Служба push-уведомлений и Служба push-уведомлений Apple могут работать не так, как ожидалось, если отсутствует явная запись SRV для каждого домена SIP, поддерживаемого развертыванием.</span><span class="sxs-lookup"><span data-stu-id="69e58-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="69e58-134">Сводка по DNS — расширяемый протокол обмена сообщениями и присутствия (XMPP)</span><span class="sxs-lookup"><span data-stu-id="69e58-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69e58-135">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="69e58-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="69e58-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="69e58-136">FQDN</span></span></th>
<th><span data-ttu-id="69e58-137">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="69e58-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="69e58-138">Соответствует/комментарии</span><span class="sxs-lookup"><span data-stu-id="69e58-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69e58-139">Внешний DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="69e58-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="69e58-140">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="69e58-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="69e58-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="69e58-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="69e58-142">Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к Пользователь с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="69e58-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="69e58-143">Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="69e58-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="69e58-144">Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</span><span class="sxs-lookup"><span data-stu-id="69e58-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69e58-145">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="69e58-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="69e58-146">xmpp.contoso.com (пример)</span><span class="sxs-lookup"><span data-stu-id="69e58-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="69e58-147">IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</span><span class="sxs-lookup"><span data-stu-id="69e58-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="69e58-148">Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="69e58-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="69e58-149">Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="69e58-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="69e58-150">См. также</span><span class="sxs-lookup"><span data-stu-id="69e58-150">See Also</span></span>


[<span data-ttu-id="69e58-151">Настройка Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="69e58-152">Настройка для push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="69e58-153">Включение и отключение обнаружения партнеров Федерации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="69e58-154">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="69e58-155">Определение требований к DNS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="69e58-156">Управление федеративными доменами SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69e58-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


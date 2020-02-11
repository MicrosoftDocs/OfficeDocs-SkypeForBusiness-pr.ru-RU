---
title: 'Lync Server 2013: требования DNS для простых URL-адресов'
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
ms.openlocfilehash: 2a05b5e5afc645c9219d02c8a551e4c0af9d93b0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="0c139-102">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c139-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c139-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0c139-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0c139-104">Lync Server 2013 поддерживает простые URL-адреса, благодаря которым пользователи могут легко присоединиться к собраниям, а затем упростить работу с администрированием Lync Server для администраторов.</span><span class="sxs-lookup"><span data-stu-id="0c139-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="0c139-105">Подробнее об использовании простых URL-адресов можно найти [в разделе Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="0c139-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="0c139-106">Lync Server поддерживает три простых URL-адреса: "Встреча", "Входящие звонки" и "Администратор". Вам необходимо настроить простые URL-адреса для "Встреча" и "Входящие звонки", а простой URL-адрес администратора — необязательный.</span><span class="sxs-lookup"><span data-stu-id="0c139-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="0c139-107">DNS-записи, необходимые для поддержки простых URL-адресов, зависят от того, как вы определили эти простые URL-адреса, и нужно ли поддерживать аварийное восстановление для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="0c139-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="0c139-108">Простой URL-адрес (вариант 1)</span><span class="sxs-lookup"><span data-stu-id="0c139-108">Simple URL Option 1</span></span>

<span data-ttu-id="0c139-109">В варианте 1 вы создаете базовый URL-адрес для каждого простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="0c139-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="0c139-110">Когда пользователь щелкает простую ссылку для собрания по URL-адресу, сервер, к которому разрешается запись DNS, определяет корректное клиентское программное обеспечение для запуска.</span><span class="sxs-lookup"><span data-stu-id="0c139-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="0c139-111">После запуска клиентское программное обеспечение автоматически связывается с пулом, на котором размещена конференция.</span><span class="sxs-lookup"><span data-stu-id="0c139-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="0c139-112">Таким образом, пользователи направляются на соответствующий сервер для содержимого собраний независимо от того, на каком сервере или в каком пуле вы хотите разрешить записи DNS.</span><span class="sxs-lookup"><span data-stu-id="0c139-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="0c139-113">Простой URL-адрес (вариант 1)</span><span class="sxs-lookup"><span data-stu-id="0c139-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c139-114"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="0c139-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="0c139-115"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="0c139-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c139-116">Подходит</span><span class="sxs-lookup"><span data-stu-id="0c139-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="0c139-117">https://meet.contoso.com, https://meet.fabrikam.comи т. д. (для каждого домена SIP в вашей организации)</span><span class="sxs-lookup"><span data-stu-id="0c139-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c139-118">Телефонные подключения</span><span class="sxs-lookup"><span data-stu-id="0c139-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c139-119">RAS</span><span class="sxs-lookup"><span data-stu-id="0c139-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0c139-120">Если вы используете вариант 1, необходимо определить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0c139-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="0c139-121">Для каждого такого простого URL-адреса вам понадобится запись DNS A, которая разрешает URL-адрес в каталог, если у вас есть один из развертываний.</span><span class="sxs-lookup"><span data-stu-id="0c139-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="0c139-122">В противном случае оно должно разрешаться в IP-адрес подсистемы балансировки нагрузки в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0c139-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="0c139-123">Если вы не развернули пул и используете стандартное развертывание сервера выпусков, запись DNS A должна разрешаться в IP-адрес одного стандартного выпуска сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="0c139-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="0c139-124">Если у вас есть несколько доменов SIP в Организации и вы используете этот параметр, необходимо создать для каждого домена SIP простые URL-адреса, и для каждого из них требуется запись DNS A для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="0c139-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="0c139-125">Например, если у вас есть и contoso.com, и fabrikam.com, вы создадите записи A для обоих типов https://meet.contoso.com и https://meet.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0c139-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="0c139-126">Кроме того, если у вас есть несколько доменов SIP и вы хотите минимизировать требования к записям DNS и сертификатам для этих простых URL-адресов, воспользуйтесь вариантом 3, описанным ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0c139-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="0c139-127">Для простого URL-адреса с телефонным подключением вам понадобится запись DNS A, которая разрешает URL-адрес в каталог, если у вас есть один из развертываний.</span><span class="sxs-lookup"><span data-stu-id="0c139-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="0c139-128">В противном случае оно должно разрешаться в IP-адрес подсистемы балансировки нагрузки в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0c139-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="0c139-129">Если вы не развернули пул и используете стандартное развертывание сервера выпусков, запись DNS A должна разрешаться в IP-адрес одного стандартного выпуска сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="0c139-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="0c139-130">Простой URL-адрес администратора является внутренним.</span><span class="sxs-lookup"><span data-stu-id="0c139-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="0c139-131">Для этого требуется запись DNS A, которая разрешает URL-адрес в каталог, если один из них развернут.</span><span class="sxs-lookup"><span data-stu-id="0c139-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="0c139-132">В противном случае оно должно разрешаться в IP-адрес подсистемы балансировки нагрузки в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0c139-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="0c139-133">Если вы не развернули пул и используете стандартное развертывание сервера выпусков, запись DNS A должна разрешаться в IP-адрес одного стандартного выпуска сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="0c139-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="0c139-134">Параметр простого URL-адреса 2</span><span class="sxs-lookup"><span data-stu-id="0c139-134">Simple URL Option 2</span></span>

<span data-ttu-id="0c139-135">В параметре 2 простые URL-адреса для "Встреча", "Входящие" и "Администратор" имеют общий базовый URL-адрес, например lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0c139-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="0c139-136">Таким образом, для простых URL-адресов требуется только одна запись DNS A, которая разрешает lync.contoso.com IP-адресу пула пулов или интерфейсов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0c139-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="0c139-137">Если вы не развернули пул и используете стандартное развертывание сервера выпусков, запись DNS A должна разрешаться в IP-адрес одного стандартного выпуска сервера в Организации.</span><span class="sxs-lookup"><span data-stu-id="0c139-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="0c139-138">Обратите внимание, что если у вас есть несколько доменов SIP в вашей организации, вам по-прежнему необходимо создавать простые URL-адреса для каждого домена SIP, и для каждого из них требуется запись DNS A.</span><span class="sxs-lookup"><span data-stu-id="0c139-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="0c139-139">В данном примере три простых URL-адреса в соответствии с lync.contoso.com, для дополнительного простого URL-адреса для fabrikam.com настраивается с использованием другого базового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="0c139-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="0c139-140">В этом примере необходимо создать записи DNS A для обоих типов https://lync.contoso.com и. https://lync.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0c139-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="0c139-141">Параметр "простой URL-адрес 3" показывает другой способ обработки именования и DNS-записей A, если у вас есть несколько доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="0c139-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="0c139-142">Параметр простого URL-адреса 2</span><span class="sxs-lookup"><span data-stu-id="0c139-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c139-143"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="0c139-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="0c139-144"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="0c139-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c139-145">Подходит</span><span class="sxs-lookup"><span data-stu-id="0c139-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="0c139-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meetи т. д. (для каждого домена SIP в вашей организации)</span><span class="sxs-lookup"><span data-stu-id="0c139-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c139-147">Телефонные подключения</span><span class="sxs-lookup"><span data-stu-id="0c139-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c139-148">RAS</span><span class="sxs-lookup"><span data-stu-id="0c139-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="0c139-149">Простой URL-адрес (вариант 3)</span><span class="sxs-lookup"><span data-stu-id="0c139-149">Simple URL Option 3</span></span>

<span data-ttu-id="0c139-150">Вариант 3 полезен, если у вас есть большое количество доменов SIP и вы хотите, чтобы они были разными простыми URL-адресами, но хотели минимизировать требования к записям DNS и сертификатам для этих простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="0c139-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="0c139-151">В этом примере требуется только одна запись DNS A, которая разрешается в lync.contoso.com с IP-адресом пула директоров или интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="0c139-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="0c139-152">Простой URL-адрес (вариант 3)</span><span class="sxs-lookup"><span data-stu-id="0c139-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c139-153"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="0c139-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="0c139-154"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="0c139-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c139-155">Подходит</span><span class="sxs-lookup"><span data-stu-id="0c139-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c139-156">Телефонные подключения</span><span class="sxs-lookup"><span data-stu-id="0c139-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c139-157">RAS</span><span class="sxs-lookup"><span data-stu-id="0c139-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="0c139-158">Параметры аварийного восстановления для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="0c139-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="0c139-159">Если у вас есть несколько сайтов, которые содержат пулы интерфейсов и поставщик DNS поддерживает Жеоднс, вы можете настроить записи DNS для простых URL-адресов, чтобы обеспечить поддержку аварийного восстановления, чтобы сделать простые функции URL-адресов более близкими, даже если весь пул переднего плана выйдет из резервной точки.</span><span class="sxs-lookup"><span data-stu-id="0c139-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="0c139-160">Это средство аварийного восстановления поддерживает простые URL-адреса для "Встреча" и "телефон-подключение".</span><span class="sxs-lookup"><span data-stu-id="0c139-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="0c139-161">Чтобы настроить это, создайте два адреса Жеоднс.</span><span class="sxs-lookup"><span data-stu-id="0c139-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="0c139-162">У каждого адреса есть две записи DNS A или CNAME, которые разрешают два пула, которые сопоставлены вместе для целей аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="0c139-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="0c139-163">Для внутреннего доступа используется один адрес Жеоднс и разрешение на внутренние доменные имена и IP-адреса подсистемы балансировки нагрузки для двух пулов.</span><span class="sxs-lookup"><span data-stu-id="0c139-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="0c139-164">Другой адрес Жеоднс используется для внешнего доступа и разрешается в внешнем полном доменном имени или IP-адресе подсистемы балансировки нагрузки для двух пулов.</span><span class="sxs-lookup"><span data-stu-id="0c139-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="0c139-165">Ниже приведен пример для простого URL-адреса, используя полные доменные имена для пулов.</span><span class="sxs-lookup"><span data-stu-id="0c139-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

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

<span data-ttu-id="0c139-166">Затем создайте записи CNAME, которые разрешают выполнение вашего простого URL-адреса (например, meet.contoso.com) для двух адресов Жеоднс.</span><span class="sxs-lookup"><span data-stu-id="0c139-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="0c139-167">Если в вашей сети используется <EM>хаирпиннинг</EM> (маршрутизация всего простого трафика по URL-адресу с помощью внешней ссылки, включая трафик из вашей организации), вы можете просто настроить внешний адрес жеоднс и разрешить всему ПРОСТОМУ URL-адресу только этот внешний адрес.</span><span class="sxs-lookup"><span data-stu-id="0c139-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="0c139-168">При использовании этого метода вы можете настроить каждый адрес Жеоднс таким образом, чтобы он использовал метод циклического перераспределения, чтобы распределять запросы к двум пулам или подключаться преимущественно к одному пулу (например, пул, который расположен географически ближе), и использовать другой пул только в случае Ошибка подключения.</span><span class="sxs-lookup"><span data-stu-id="0c139-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="0c139-169">Вы можете настроить такую же конфигурацию для простого URL-адреса с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="0c139-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="0c139-170">Для этого создайте дополнительные записи, такие как в предыдущем примере, с заменой `dialin` `meet` в DNS-записях.</span><span class="sxs-lookup"><span data-stu-id="0c139-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="0c139-171">Для простого URL-адреса администратора используйте один из трех описанных выше параметров в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0c139-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="0c139-172">После настройки конфигурации вы должны использовать приложение мониторинга для настройки наблюдения HTTP для отслеживания сбоев.</span><span class="sxs-lookup"><span data-stu-id="0c139-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="0c139-173">Для внешнего доступа убедитесь в том, что протокол HTTPS получил запросы на автообнаружение полного доменного имени или IP-адреса подсистемы балансировки нагрузки для двух пулов.</span><span class="sxs-lookup"><span data-stu-id="0c139-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="0c139-174">Например, следующие запросы не должны содержать заголовков **приема** и должны возвращать **200 ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c139-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="0c139-175">Для внутреннего доступа необходимо следить за портом 5061 на внутреннем полном доменном имени или IP-адресе подсистемы балансировки нагрузки для двух пулов.</span><span class="sxs-lookup"><span data-stu-id="0c139-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="0c139-176">Если обнаружены ошибки подключения, VIP для этих пулов должен закрыть порты 80, 443 и 444.</span><span class="sxs-lookup"><span data-stu-id="0c139-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


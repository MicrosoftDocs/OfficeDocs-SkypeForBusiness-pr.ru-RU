---
title: 'Lync Server 2013: процесс развертывания мобильных клиентов'
description: 'Lync Server 2013: процесс развертывания мобильных клиентов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563485"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="b19db-103">Процесс развертывания мобильных клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b19db-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b19db-104">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b19db-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b19db-105">После завершения развертывания Microsoft Lync Server 2013 пользователи могут установить приложение Lync 2013 из мобильного магазина, с которым они привычны для конкретных устройств.</span><span class="sxs-lookup"><span data-stu-id="b19db-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="b19db-106">Процесс развертывания Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="b19db-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b19db-107">Этап</span><span class="sxs-lookup"><span data-stu-id="b19db-107">Phase</span></span></th>
<th><span data-ttu-id="b19db-108">Действия</span><span class="sxs-lookup"><span data-stu-id="b19db-108">Steps</span></span></th>
<th><span data-ttu-id="b19db-109">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b19db-109">Permissions</span></span></th>
<th><span data-ttu-id="b19db-110">Документация</span><span class="sxs-lookup"><span data-stu-id="b19db-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b19db-111">Выполните задачи, выполняемые перед установкой.</span><span class="sxs-lookup"><span data-stu-id="b19db-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b19db-112">Проверьте развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b19db-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="b19db-113">Проверьте требования к сертификатам.</span><span class="sxs-lookup"><span data-stu-id="b19db-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b19db-114">Администратор</span><span class="sxs-lookup"><span data-stu-id="b19db-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="b19db-115"><a href="lync-server-2013-planning-for-mobility.md">Планирование мобильных устройств в Lync server 2013</a> в документации по планированию серверов.</span><span class="sxs-lookup"><span data-stu-id="b19db-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="b19db-116"><a href="lync-server-2013-deploying-mobility.md">Развертывание мобильных устройств в Lync server 2013</a> в документации по развертыванию серверов.</span><span class="sxs-lookup"><span data-stu-id="b19db-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="b19db-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Требования к инфраструктуре сертификатов для Lync Server 2013</a> в документации по планированию серверов.</span><span class="sxs-lookup"><span data-stu-id="b19db-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19db-118">Установите приложение Lync на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="b19db-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b19db-119">Установите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="b19db-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="b19db-120">Установка из магазина, относящегося к мобильному устройству.</span><span class="sxs-lookup"><span data-stu-id="b19db-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b19db-121">Администратор</span><span class="sxs-lookup"><span data-stu-id="b19db-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="b19db-122">Инструкции по установке, относящиеся к мобильному устройству при <a href="lync-server-2013-deploying-mobile-clients.md">развертывании мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b19db-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19db-123">Настройте клиент.</span><span class="sxs-lookup"><span data-stu-id="b19db-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b19db-124">Настройка параметров входа и сведений о сервере.</span><span class="sxs-lookup"><span data-stu-id="b19db-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b19db-125">Администратор</span><span class="sxs-lookup"><span data-stu-id="b19db-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="b19db-126"><a href="lync-server-2013-deploying-mobile-clients.md">Развертывание мобильных клиентов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b19db-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19db-127">Протестируйте сценарии для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="b19db-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b19db-128">Протестируйте обмен мгновенными сообщениями и сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="b19db-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="b19db-129">Проверка конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="b19db-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="b19db-130">Поиск контакта в корпоративном каталоге.</span><span class="sxs-lookup"><span data-stu-id="b19db-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="b19db-131">Протестируйте push-уведомления.</span><span class="sxs-lookup"><span data-stu-id="b19db-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b19db-132">Администратор</span><span class="sxs-lookup"><span data-stu-id="b19db-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="b19db-133">Инструкции по проверке, характерные для мобильного устройства при <a href="lync-server-2013-deploying-mobile-clients.md">развертывании мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b19db-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19db-134">Установите приложение Lync на мобильных телефонах.</span><span class="sxs-lookup"><span data-stu-id="b19db-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b19db-135">Установите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="b19db-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="b19db-136">Установка из магазина, относящегося к мобильному устройству.</span><span class="sxs-lookup"><span data-stu-id="b19db-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b19db-137">Пользователь</span><span class="sxs-lookup"><span data-stu-id="b19db-137">User</span></span></p></td>
<td><p><span data-ttu-id="b19db-138">Инструкции по установке, относящиеся к мобильному устройству при <a href="lync-server-2013-deploying-mobile-clients.md">развертывании мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b19db-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: процесс развертывания мобильного клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d0bf17fe4906d49fefd8bd319d25d1268191e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="a54cf-102">Процесс развертывания мобильных клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a54cf-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a54cf-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a54cf-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a54cf-104">После завершения развертывания Microsoft Lync Server 2013 пользователи могут установить приложение Lync 2013 из мобильного магазина, с помощью которого они привычны для определенного устройства.</span><span class="sxs-lookup"><span data-stu-id="a54cf-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="a54cf-105">Процесс развертывания Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="a54cf-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a54cf-106">Этап</span><span class="sxs-lookup"><span data-stu-id="a54cf-106">Phase</span></span></th>
<th><span data-ttu-id="a54cf-107">Шаги</span><span class="sxs-lookup"><span data-stu-id="a54cf-107">Steps</span></span></th>
<th><span data-ttu-id="a54cf-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a54cf-108">Permissions</span></span></th>
<th><span data-ttu-id="a54cf-109">Документация</span><span class="sxs-lookup"><span data-stu-id="a54cf-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a54cf-110">Выполнять задачи, выполняемые перед настройкой.</span><span class="sxs-lookup"><span data-stu-id="a54cf-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a54cf-111">Убедитесь, что развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a54cf-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="a54cf-112">Проверка требований сертификата.</span><span class="sxs-lookup"><span data-stu-id="a54cf-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a54cf-113">Администратор</span><span class="sxs-lookup"><span data-stu-id="a54cf-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a54cf-114"><a href="lync-server-2013-planning-for-mobility.md">Планирование мобильных устройств в Lync server 2013</a> в документации по планированию сервера.</span><span class="sxs-lookup"><span data-stu-id="a54cf-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="a54cf-115"><a href="lync-server-2013-deploying-mobility.md">Развертывание мобильных устройств в Lync server 2013</a> в документации по развертыванию сервера.</span><span class="sxs-lookup"><span data-stu-id="a54cf-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="a54cf-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Требования к инфраструктуре сертификатов для Lync Server 2013</a> в документации по планированию сервера.</span><span class="sxs-lookup"><span data-stu-id="a54cf-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54cf-117">Установите приложение Lync на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="a54cf-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a54cf-118">Установите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="a54cf-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="a54cf-119">Установка из магазина, относящегося к мобильному устройству.</span><span class="sxs-lookup"><span data-stu-id="a54cf-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a54cf-120">Администратор</span><span class="sxs-lookup"><span data-stu-id="a54cf-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a54cf-121">Инструкции по установке, связанные с мобильным устройством на странице <a href="lync-server-2013-deploying-mobile-clients.md">развертывание мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a54cf-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54cf-122">Настройте клиент.</span><span class="sxs-lookup"><span data-stu-id="a54cf-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a54cf-123">Настройте параметры входа и сведения о сервере.</span><span class="sxs-lookup"><span data-stu-id="a54cf-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a54cf-124">Администратор</span><span class="sxs-lookup"><span data-stu-id="a54cf-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a54cf-125"><a href="lync-server-2013-deploying-mobile-clients.md">Развертывание мобильных клиентов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a54cf-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54cf-126">Протестируйте сценарии для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="a54cf-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a54cf-127">Протестируйте обмен мгновенными сообщениями и сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="a54cf-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="a54cf-128">Протестируйте Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="a54cf-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="a54cf-129">Поиск контакта в корпоративном справочнике.</span><span class="sxs-lookup"><span data-stu-id="a54cf-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="a54cf-130">Тест push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a54cf-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a54cf-131">Администратор</span><span class="sxs-lookup"><span data-stu-id="a54cf-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="a54cf-132">Инструкции для проверки, специфичные для мобильного устройства при <a href="lync-server-2013-deploying-mobile-clients.md">развертывании мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a54cf-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54cf-133">Установите приложение Lync на мобильных телефонах.</span><span class="sxs-lookup"><span data-stu-id="a54cf-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a54cf-134">Установите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="a54cf-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="a54cf-135">Установка из магазина, относящегося к мобильному устройству.</span><span class="sxs-lookup"><span data-stu-id="a54cf-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a54cf-136">Пользователь</span><span class="sxs-lookup"><span data-stu-id="a54cf-136">User</span></span></p></td>
<td><p><span data-ttu-id="a54cf-137">Инструкции по установке, связанные с мобильным устройством на странице <a href="lync-server-2013-deploying-mobile-clients.md">развертывание мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a54cf-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: процесс развертывания мобильного клиента'
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
ms.openlocfilehash: e6beaeac91dae0ff5fbf755c4ccb33cae288df75
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="006c4-102">Процесс развертывания мобильных клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="006c4-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="006c4-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="006c4-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="006c4-104">После завершения развертывания Microsoft Lync Server 2013 пользователи могут установить приложение Lync 2013 из мобильного магазина, с помощью которого они привычны для определенного устройства.</span><span class="sxs-lookup"><span data-stu-id="006c4-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="006c4-105">Процесс развертывания Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="006c4-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="006c4-106">Этап</span><span class="sxs-lookup"><span data-stu-id="006c4-106">Phase</span></span></th>
<th><span data-ttu-id="006c4-107">Шаги</span><span class="sxs-lookup"><span data-stu-id="006c4-107">Steps</span></span></th>
<th><span data-ttu-id="006c4-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="006c4-108">Permissions</span></span></th>
<th><span data-ttu-id="006c4-109">Документация</span><span class="sxs-lookup"><span data-stu-id="006c4-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="006c4-110">Выполнять задачи, выполняемые перед настройкой.</span><span class="sxs-lookup"><span data-stu-id="006c4-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="006c4-111">Убедитесь, что развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="006c4-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="006c4-112">Проверка требований сертификата.</span><span class="sxs-lookup"><span data-stu-id="006c4-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="006c4-113">Администратор</span><span class="sxs-lookup"><span data-stu-id="006c4-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="006c4-114"><a href="lync-server-2013-planning-for-mobility.md">Планирование мобильных устройств в Lync server 2013</a> в документации по планированию сервера.</span><span class="sxs-lookup"><span data-stu-id="006c4-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="006c4-115"><a href="lync-server-2013-deploying-mobility.md">Развертывание мобильных устройств в Lync server 2013</a> в документации по развертыванию сервера.</span><span class="sxs-lookup"><span data-stu-id="006c4-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="006c4-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Требования к инфраструктуре сертификатов для Lync Server 2013</a> в документации по планированию сервера.</span><span class="sxs-lookup"><span data-stu-id="006c4-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006c4-117">Установите приложение Lync на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="006c4-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="006c4-118">Установите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="006c4-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="006c4-119">Установка из магазина, относящегося к мобильному устройству.</span><span class="sxs-lookup"><span data-stu-id="006c4-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="006c4-120">Администратор</span><span class="sxs-lookup"><span data-stu-id="006c4-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="006c4-121">Инструкции по установке, связанные с мобильным устройством на странице <a href="lync-server-2013-deploying-mobile-clients.md">развертывание мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="006c4-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="006c4-122">Настройте клиент.</span><span class="sxs-lookup"><span data-stu-id="006c4-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="006c4-123">Настройте параметры входа и сведения о сервере.</span><span class="sxs-lookup"><span data-stu-id="006c4-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="006c4-124">Администратор</span><span class="sxs-lookup"><span data-stu-id="006c4-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="006c4-125"><a href="lync-server-2013-deploying-mobile-clients.md">Развертывание мобильных клиентов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="006c4-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="006c4-126">Протестируйте сценарии для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="006c4-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="006c4-127">Протестируйте обмен мгновенными сообщениями и сведения о присутствии.</span><span class="sxs-lookup"><span data-stu-id="006c4-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="006c4-128">Протестируйте Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="006c4-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="006c4-129">Поиск контакта в корпоративном справочнике.</span><span class="sxs-lookup"><span data-stu-id="006c4-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="006c4-130">Тест push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="006c4-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="006c4-131">Администратор</span><span class="sxs-lookup"><span data-stu-id="006c4-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="006c4-132">Инструкции для проверки, специфичные для мобильного устройства при <a href="lync-server-2013-deploying-mobile-clients.md">развертывании мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="006c4-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="006c4-133">Установите приложение Lync на мобильных телефонах.</span><span class="sxs-lookup"><span data-stu-id="006c4-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="006c4-134">Установите необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="006c4-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="006c4-135">Установка из магазина, относящегося к мобильному устройству.</span><span class="sxs-lookup"><span data-stu-id="006c4-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="006c4-136">Пользователь</span><span class="sxs-lookup"><span data-stu-id="006c4-136">User</span></span></p></td>
<td><p><span data-ttu-id="006c4-137">Инструкции по установке, связанные с мобильным устройством на странице <a href="lync-server-2013-deploying-mobile-clients.md">развертывание мобильных клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="006c4-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


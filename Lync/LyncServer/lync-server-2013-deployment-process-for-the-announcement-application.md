---
title: 'Lync Server 2013: процесс развертывания для приложения "оповещение"'
description: 'Lync Server 2013: процесс развертывания для приложения "извещения".'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559977c32f63fae312164b5b0c36698fa13afb09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550995"
---
# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="dbfe3-103">Процесс развертывания приложения "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbfe3-103">Deployment process for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbfe3-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dbfe3-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dbfe3-105">В этом разделе представлен обзор действий, необходимых при развертывании приложения извещения.</span><span class="sxs-lookup"><span data-stu-id="dbfe3-105">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="dbfe3-106">Перед настройкой объявлений необходимо развернуть корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="dbfe3-106">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="dbfe3-107">Компоненты, необходимые для приложения извещения, устанавливаются и включаются при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="dbfe3-107">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="dbfe3-108">Процесс развертывания объявлений</span><span class="sxs-lookup"><span data-stu-id="dbfe3-108">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbfe3-109">Этап</span><span class="sxs-lookup"><span data-stu-id="dbfe3-109">Phase</span></span></th>
<th><span data-ttu-id="dbfe3-110">Действия</span><span class="sxs-lookup"><span data-stu-id="dbfe3-110">Steps</span></span></th>
<th><span data-ttu-id="dbfe3-111">Роли</span><span class="sxs-lookup"><span data-stu-id="dbfe3-111">Roles</span></span></th>
<th><span data-ttu-id="dbfe3-112">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="dbfe3-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbfe3-113">Настройка параметров объявлений</span><span class="sxs-lookup"><span data-stu-id="dbfe3-113">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfe3-114">Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</span><span class="sxs-lookup"><span data-stu-id="dbfe3-114">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="dbfe3-115">Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="dbfe3-115">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbfe3-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="dbfe3-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="dbfe3-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="dbfe3-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="dbfe3-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="dbfe3-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="dbfe3-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="dbfe3-119">CsAdministrator</span></span></p>
<p><span data-ttu-id="dbfe3-120">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="dbfe3-120">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="dbfe3-121"><a href="lync-server-2013-create-an-announcement.md">Создание извещения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbfe3-121"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="dbfe3-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Настройка таблицы неназначенных номеров в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbfe3-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfe3-123">Проверка развертывания объявления</span><span class="sxs-lookup"><span data-stu-id="dbfe3-123">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="dbfe3-124">Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</span><span class="sxs-lookup"><span data-stu-id="dbfe3-124">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="dbfe3-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Необязательно Проверка развертывания объявлений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbfe3-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


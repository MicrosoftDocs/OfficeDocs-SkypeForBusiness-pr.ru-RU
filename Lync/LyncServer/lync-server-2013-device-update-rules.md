---
title: 'Lync Server 2013: правила обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce4b0be575665d23b2b09126905fc35791f61ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="ff137-102">Правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff137-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ff137-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ff137-104">Периодически Корпорация Майкрософт выпускает новый набор обновлений встроенного по устройства для Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ff137-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="ff137-105">*Правила обновления устройства* связывают обновления встроенного по с аппаратными устройствами (телефоны и другие устройства, на которых работает Lync Phone Edition).</span><span class="sxs-lookup"><span data-stu-id="ff137-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="ff137-106">Чтобы получить последний набор правил обновления устройства, перейдите на страницу справки и поддержки на веб-сайте Майкрософт и выполните поиск по слову "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="ff137-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="ff137-107">Загрузите пакет обновления и извлеките файлы в папку на компьютере, куда нужно отправить обновления.</span><span class="sxs-lookup"><span data-stu-id="ff137-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="ff137-108">После того как файлы будут извлечены, импортируйте правила обновления устройств, найденные в извлеченном файле. CAB-файл (с именем Укупдатес. cab).</span><span class="sxs-lookup"><span data-stu-id="ff137-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="ff137-109">Затем с помощью панели управления Lync Server или командлетов Windows PowerShell просмотрите эти правила для устройств организации и управляйте ими.</span><span class="sxs-lookup"><span data-stu-id="ff137-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="ff137-110">В следующих разделах объясняется, как импортировать, просматривать правила обновления устройств и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="ff137-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff137-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="ff137-111">In This Section</span></span>

  - [<span data-ttu-id="ff137-112">Просмотр сведений о правилах обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="ff137-113">Импорт правил обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="ff137-114">Утверждение правила обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="ff137-115">Удаление правила обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="ff137-116">Сброс правила обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="ff137-117">Восстановление правила обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff137-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


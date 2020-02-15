---
title: 'Lync Server 2013: правила обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b52fa2f2aefae05f713972df5c3b15e6db7c0b57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="45fa8-102">Правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45fa8-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="45fa8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="45fa8-104">Корпорация Майкрософт выпускает новый набор обновлений встроенного по устройства для Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="45fa8-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="45fa8-105">*Правила обновления устройств* связывают обновления встроенного по с аппаратными устройствами, телефонами и другими устройствами, работающими с Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="45fa8-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="45fa8-106">Чтобы получить последний набор правил обновления устройств, перейдите на страницу справки и поддержки на веб-сайте Майкрософт и выполните поиск по слову "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="45fa8-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="45fa8-107">Скачайте пакет обновления и извлеките файлы в папку на компьютере, где будут отправляться обновления.</span><span class="sxs-lookup"><span data-stu-id="45fa8-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="45fa8-108">После извлечения файлов импортируйте правила обновления устройств, обнаруженные в извлеченном файле. CAB-файл (с именем UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="45fa8-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="45fa8-109">Затем используйте панель управления Lync Server или командлеты Windows PowerShell, чтобы просматривать эти правила для устройств организации и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="45fa8-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="45fa8-110">В следующих разделах рассказывается, как импортировать, просматривать правила обновления устройств и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="45fa8-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="45fa8-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="45fa8-111">In This Section</span></span>

  - [<span data-ttu-id="45fa8-112">Просмотр сведений о правилах обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="45fa8-113">Импорт правил обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="45fa8-114">Утверждение правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="45fa8-115">Удаление правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="45fa8-116">Сброс правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="45fa8-117">Восстановление правила обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fa8-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


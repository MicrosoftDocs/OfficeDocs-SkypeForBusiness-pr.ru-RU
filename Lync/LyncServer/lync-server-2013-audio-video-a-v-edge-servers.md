---
title: 'Lync Server 2013: пограничные серверы аудио-и видеоданных (A/V)'
description: 'Lync Server 2013: пограничные серверы аудио-и видеоданных (A/V).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5aefd4516540485b84ba0eb80f1a809d89eba0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568795"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="b4243-103">Пограничные серверы аудио/видео (A/V) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4243-103">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4243-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b4243-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b4243-p101">Пограничная служба обработки аудио- и видеоданных позволяет внутренним пользователям (пользователям, вошедшим в сеть организации) обмениваться аудио- и видеоданными с внешними пользователями (не вошедшими в сеть организации). Помимо этого, она обеспечивает поддержку таких возможностей, как совместный доступ к рабочему столу и передача файлов.</span><span class="sxs-lookup"><span data-stu-id="b4243-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="b4243-p102">Управление пограничной службой обработки аудио- и видеоданных в первую очередь осуществляется с помощью параметров ее конфигурации. Эти параметры позволяют вам управлять максимальной пропускной способностью, выделенной для каждого порта и пользователя, и указывать количество времени, в течение которого может быть использован маркер проверки подлинности до истечения срока его действия, после которого он должен быть обновлен. Параметры конфигурации пограничной службы обработки аудио- и видеоданных можно применять к сайтам или отдельным пограничным серверам аудио- и видеоданных. При определении того, какой набор параметров будет иметь приоритет, руководствуйтесь следующими правилами.</span><span class="sxs-lookup"><span data-stu-id="b4243-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="b4243-110">Параметры, настроенные на уровне службы (то есть для отдельного сервера), имеют приоритет над остальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="b4243-110">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="b4243-p103">Параметры, настроенные на уровне сайта, имеют приоритет над параметрами, настроенными на глобальном уровне. Однако они переопределяются параметрами на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="b4243-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="b4243-113">Параметры глобального уровня используются только в том случае, если нет параметров, настроенных на уровне службы для отдельного сервера, и параметров уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="b4243-113">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="b4243-114">Пограничная служба аудио-и видеоданных может управляться только с помощью командлетов Lync Server PowerShell и командлетов CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b4243-114">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4243-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="b4243-115">In This Section</span></span>

  - [<span data-ttu-id="b4243-116">Возврат сведений о конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4243-116">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="b4243-117">Создание или изменение коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4243-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="b4243-118">Удаление существующей коллекции параметров конфигурации пограничного сервера аудио-и видеоданных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4243-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


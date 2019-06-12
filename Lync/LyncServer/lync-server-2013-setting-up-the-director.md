---
title: 'Lync Server 2013: настройка директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de0fe7b06bbeed714aca444e75086fba9579e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="a18c1-102">Настройка директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18c1-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a18c1-103">_**Тема последнего изменения:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="a18c1-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="a18c1-104">Если вы разрабатываете доступ для внешних пользователей, развертывая пограничные серверы, один из вариантов — развернуть директорию.</span><span class="sxs-lookup"><span data-stu-id="a18c1-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="a18c1-105">Режиссер — это сервер, на котором работает Microsoft Lync Server 2013, который проверяет подлинность запросов пользователей, но не имеет домашних учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="a18c1-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="a18c1-106">Теперь это не является требованием, но очень полезно, если вы беспокоитесь о производительности и хотите упростить запросы на проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="a18c1-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="a18c1-107">Если вы решите, что это хорошая идея для вашей организации, действия, которые необходимо выполнить для настройки режиссера или режиссера, похожи на настройку пула переднего плана Enterprise Edition или стандартного сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a18c1-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="a18c1-108">После определения режиссеров в построителе топологии вам потребуется выполнить действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a18c1-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a18c1-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="a18c1-109">In This Section</span></span>

  - [<span data-ttu-id="a18c1-110">Установка локального хранилища конфигурации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18c1-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="a18c1-111">Установка Lync Server 2013 на директоре</span><span class="sxs-lookup"><span data-stu-id="a18c1-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="a18c1-112">Настройка сертификатов для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18c1-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="a18c1-113">Запуск служб в директоре в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18c1-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="a18c1-114">Проверка директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18c1-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="a18c1-115">Настройка автоматического входа клиента для использования директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18c1-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


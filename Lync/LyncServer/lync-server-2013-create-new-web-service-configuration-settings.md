---
title: 'Lync Server 2013: создание новых параметров конфигурации веб-служб'
description: 'Lync Server 2013: создание новых параметров конфигурации веб-службы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc66b0c8f394260fbe30e444f800640c774b6bcf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553965"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d4fc0-103">Создание новых параметров конфигурации веб-службы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4fc0-103">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4fc0-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d4fc0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d4fc0-105">С помощью страницы **веб-службы** можно настроить методы проверки подлинности для доступа к веб-серверам, связанным с Lync Server 2013, и веб-службам.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="d4fc0-106">Чтобы создать политику веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-106">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="d4fc0-107">Создание новых параметров конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="d4fc0-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="d4fc0-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="d4fc0-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4fc0-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4fc0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4fc0-111">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="d4fc0-112">На странице **Веб-служба** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d4fc0-112">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="d4fc0-p102">Чтобы настроить веб-службу для сайта, щелкните **Конфигурация сайта**. В разделе **выбора сайта** щелкните сайт, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-p102">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="d4fc0-p103">Чтобы настроить веб-службу для пула, щелкните **Конфигурация пула**. В разделе **выбора службы** щелкните службу, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-p103">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="d4fc0-117">На странице **Создание параметров веб-службы** в раскрывающемся списке **Встроенная проверка подлинности Windows** выберите **Согласование**, **Встроенная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-117">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="d4fc0-118">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="d4fc0-118">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="d4fc0-119">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-119">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="d4fc0-120">**Включить проверку подлинности с использованием сертификатов**, чтобы разрешить серверам пула выдавать сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="d4fc0-121">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-121">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="d4fc0-122">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="d4fc0-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


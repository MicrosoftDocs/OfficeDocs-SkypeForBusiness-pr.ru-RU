---
title: 'Lync Server 2013: изменение параметров конфигурации существующей веб-службы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6d29868c6f4b18bd4bb02dac651a671684ecc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b4649-102">Изменение параметров конфигурации существующей веб-службы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4649-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4649-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b4649-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b4649-104">С помощью страницы **веб-службы** можно настроить методы проверки подлинности для доступа к веб-серверам, связанным с Lync Server 2013, и веб-службам.</span><span class="sxs-lookup"><span data-stu-id="b4649-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="b4649-105">Чтобы изменить политику существующей веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b4649-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b4649-106">Изменение параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="b4649-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="b4649-107">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4649-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b4649-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4649-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b4649-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4649-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b4649-110">В левой панели навигации щелкните **Безопасность** и затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="b4649-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="b4649-111">На странице **Веб-служба**  выберите конфигурацию, щелкните **Изменить** и затем щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="b4649-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b4649-112">На странице **Изменение параметров веб-службы** в раскрывающемся списке **Интегрированная проверка подлинности Windows** выберите **Согласование**, **Интегрированная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="b4649-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="b4649-113">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="b4649-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="b4649-114">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="b4649-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="b4649-115">**Включить проверку подлинности с использованием сертификатов**, чтобы разрешить серверам пула выдавать сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="b4649-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="b4649-116">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="b4649-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="b4649-117">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="b4649-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4649-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b4649-118">See Also</span></span>


[<span data-ttu-id="b4649-119">Настройка проверки подлинности на панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4649-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: изменение существующих параметров конфигурации веб-службы'
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
ms.openlocfilehash: 11bd7f4629d4a3cf0f356a47760810e380af7deb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="177d7-102">Изменение существующих параметров конфигурации веб-службы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="177d7-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="177d7-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="177d7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="177d7-104">На странице **веб-службы** можно настроить методы проверки подлинности для доступа к веб-серверам, связанным с Lync Server 2013 и веб-службам.</span><span class="sxs-lookup"><span data-stu-id="177d7-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="177d7-105">Чтобы изменить политику существующей веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="177d7-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="177d7-106">Изменение параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="177d7-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="177d7-107">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="177d7-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="177d7-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="177d7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="177d7-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="177d7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="177d7-110">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="177d7-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="177d7-111">На странице **Веб-служба** выберите конфигурацию, щелкните **Правка**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="177d7-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="177d7-112">На странице **Изменение параметров веб-службы** в раскрывающемся списке **Интегрированная проверка подлинности Windows** выберите **Согласование**, **Интегрированная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="177d7-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="177d7-113">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="177d7-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="177d7-114">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="177d7-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="177d7-115">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="177d7-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="177d7-116">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="177d7-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="177d7-117">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="177d7-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="177d7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="177d7-118">See Also</span></span>


[<span data-ttu-id="177d7-119">Настройка проверки подлинности на панели управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="177d7-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


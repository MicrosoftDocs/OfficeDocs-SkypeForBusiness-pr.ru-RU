---
title: 'Lync Server 2013: изменение параметров конфигурации существующего регистратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32d59c31497f4a7d1a67087f47175184bd5665f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a18d0-102">Изменение параметров конфигурации существующего регистратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18d0-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a18d0-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a18d0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a18d0-104">Для настройки протоколов проверки подлинности прокси-сервера можно использовать службу Регистратора.</span><span class="sxs-lookup"><span data-stu-id="a18d0-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="a18d0-105">Сведения о доступных протоколах приведены в разделе [Create a Configuration регистратор Settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a18d0-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a18d0-p102">Если сервер обеспечивает проверку подлинности удаленных клиентов и клиентов организации, то рекомендуется включить проверку подлинности Kerberos и NTLM. Пограничный сервер и внутренние серверы проверяют, включена ли проверка подлинности NTLM для удаленных клиентов. Если на этих серверах включена только проверка подлинности Kerberos, они не смогут выполнять проверку подлинности удаленных пользователей. Если пользователи организации проходят проверку подлинности на сервере, то используется протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a18d0-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="a18d0-110">Чтобы изменить параметры службы Регистратора, выполните действия, описанные в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="a18d0-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a18d0-111">Изменение параметров конфигурации существующего регистратора</span><span class="sxs-lookup"><span data-stu-id="a18d0-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="a18d0-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18d0-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="a18d0-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a18d0-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a18d0-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a18d0-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a18d0-115">В левой панели навигации щелкните **Security** (Безопасность) и затем щелкните **Registrar** (Регистратор).</span><span class="sxs-lookup"><span data-stu-id="a18d0-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="a18d0-116">На странице **Registrar** (Регистратор) выберите службу, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="a18d0-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a18d0-117">На странице **Edit Registrar Setting** (Изменение параметров Регистратора) установите один флажок или несколько в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="a18d0-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="a18d0-118">**Enable Kerberos authentication** (Включить проверку подлинности Kerberos) — для запросов проверки подлинности серверы пула используют протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a18d0-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="a18d0-119">**Включить проверку подлинности NTLM** — чтобы серверы в пуле выдавали запросы с использованием NTLM.</span><span class="sxs-lookup"><span data-stu-id="a18d0-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="a18d0-120">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="a18d0-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="a18d0-121">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a18d0-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: изменение существующих параметров конфигурации регистратора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42629c027157c33bc9431d04d493019e4907d87b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="18314-102">Изменение существующих параметров конфигурации регистратора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18314-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18314-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="18314-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="18314-104">Вы можете использовать регистратор для настройки протоколов проверки подлинности прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="18314-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="18314-105">Сведения о доступных протоколах можно найти [в разделе Создание параметров конфигурации регистратора в Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="18314-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18314-p102">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="18314-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="18314-110">Чтобы изменить параметры службы Регистратора, выполните действия, описанные в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="18314-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="18314-111">Изменение параметров конфигурации существующего регистратора</span><span class="sxs-lookup"><span data-stu-id="18314-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="18314-112">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18314-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="18314-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18314-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18314-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="18314-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="18314-115">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="18314-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="18314-116">На странице **Регистратор** щелкните службу, затем щелкните **Изменить** (Изменить) и **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="18314-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="18314-117">На странице **редактирования параметров регистратора** установите один или несколько флажков в зависимости от возможностей клиентов и наличия поддержки в среде.</span><span class="sxs-lookup"><span data-stu-id="18314-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="18314-118">**Разрешить проверку подлинности Kerberos**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="18314-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="18314-119">**Разрешить проверку подлинности NTLM**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности NTLM.</span><span class="sxs-lookup"><span data-stu-id="18314-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="18314-120">**Разрешить проверку подлинности на основе сертификатов**. В этом режиме серверы в пуле выдают сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="18314-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="18314-121">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="18314-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


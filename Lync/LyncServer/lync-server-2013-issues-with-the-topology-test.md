---
title: 'Lync Server 2013: проблемы с проверкой топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="c1ff6-102">Проблемы с проверкой топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1ff6-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1ff6-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c1ff6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c1ff6-104">Как и командлет **Test-кстопологи** , анализатор соответствия рекомендациям предоставляет способ проверки правильности функционирования Lync Server 2013 на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="c1ff6-105">По умолчанию анализатором соответствия рекомендациям, например командлет, проверяется вся инфраструктура Lync Server 2013, проверка того, что запущены необходимые службы и установлены ли соответствующие права и разрешения для этих служб, а также для универсальных пользователей. группы безопасности, созданные при установке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="c1ff6-106">Помимо проверки действительности сервера Lync Server, **Test-кстопологи** также проверяет правильность определенной службы.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="c1ff6-107">Подробные сведения об использовании командлета для проверки конкретных служб можно найти в разделе [Test-кстопологи](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="c1ff6-108">Чтобы устранить проблемы с топологией, воспользуйтесь приведенными ниже сведениями.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1ff6-109">В зависимости от конфигурации пограничных серверов и всех связанных с ней параметров периметра сети, включая параметры брандмауэра и разрешения, анализатор соответствия рекомендациям может не получить доступ к пограничным серверам и их проверку.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="c1ff6-110">Если вы включаете пограничные серверы в вашем сканировании, а отчеты указывают на то, что возникают неполадки при доступе к пограничным серверам, снимите флажок <STRONG>пограничные серверы</STRONG> и снова запустите проверку, чтобы предотвратить возникновение этой ошибки в отчетах.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="c1ff6-111">Устранение проблем с топологией</span><span class="sxs-lookup"><span data-stu-id="c1ff6-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="c1ff6-112">Если при тестировании топологии возникли проблемы с топологией, это может быть вызвано проблемами, возникающими при публикации или включении топологии.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="c1ff6-113">После внесения изменений в топологию изменения вступают в силу только после того, как они были опубликованы и включены.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="c1ff6-114">Для внесения изменений в топологию необходимо использовать Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="c1ff6-115">После внесения изменений вы можете опубликовать и включить эти изменения с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="c1ff6-116">Когда вы публикуете изменения, новые сведения (например, новый сайт или роль новой серверной роли) записываются в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="c1ff6-117">Однако эти новые (или только что измененные) объекты не присоединяются к топологии сразу.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="c1ff6-118">Объекты подключаются к топологии только в том случае, если вы включите обновленную топологию.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="c1ff6-119">Если выбрать параметр Опубликовать в построителе топологии, выполняются оба указанных ниже действия. изменения публикуются (то есть они записываются в хранилище Центрального управления), а затем включена новая топология.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="c1ff6-120">По умолчанию членам группы Рткуниверсалсерверадминс разрешено выполнять командлет **Publish-кстопологи** и командлет **Enable-кстопологи** .</span><span class="sxs-lookup"><span data-stu-id="c1ff6-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="c1ff6-121">Однако если разрешения на установку не делегированы, необходимо войти в учетную запись администратора домена, чтобы запустить команду **Publish-кстопологи**.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="c1ff6-122">Чтобы предоставить Рткуниверсалсерверадминс право на фактическое использование командлета **Publish-кстопологи** , необходимо выполнить командлет **Grant-кссетуппермиссион** в каждом контейнере Active Directory, содержащем компьютеры, на которых выполняются службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="c1ff6-123">Чтобы предоставить Рткуниверсалсерверадминс право на использование командлета **Enable-кстопологи** , необходимо выполнить командлет **Set-кссетуппермиссион** для каждого контейнера доменных служб Active Directory, содержащего компьютеры, на которых выполняются службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="c1ff6-124">Обратите внимание, что это касается включения и публикации топологии с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="c1ff6-125">Если вы не делегированы разрешения с помощью **Set-кссетуппермиссион**, только администратор домена может включать и публиковать топологию с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="c1ff6-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: проблемы с проверкой топологии'
description: 'Lync Server 2013: проблемы с проверкой топологии.'
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
ms.openlocfilehash: 2a0f24942844bcf371eff94ee04c8faafcf513d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554445"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="957da-103">Проблемы, связанные с проверкой топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957da-103">Issues with the topology test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="957da-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="957da-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="957da-105">Как и командлет **Test-CsTopology** , анализатор соответствия рекомендациям позволяет убедиться, что Lync Server 2013 правильно работает на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="957da-105">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="957da-106">По умолчанию анализатор соответствия рекомендациям, как и командлет, проверяет всю инфраструктуру Lync Server 2013, проверку выполнения необходимых служб и наличие соответствующих прав и разрешений пользователя для этих служб, а также для универсальных групп безопасности, создаваемых при установке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="957da-106">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="957da-107">Кроме проверки допустимости Lync Server в целом, **Test-CsTopology** также проверяет допустимость определенной службы.</span><span class="sxs-lookup"><span data-stu-id="957da-107">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="957da-108">Дополнительные сведения об использовании командлета для тестирования определенных служб приведены в статье [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="957da-108">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="957da-109">Используйте следующие сведения для устранения неполадок с топологией.</span><span class="sxs-lookup"><span data-stu-id="957da-109">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="957da-p103">В зависимости от конфигурации пограничных серверов и связанных параметров сети периметра, в том числе настроек и разрешений брандмауэра, у BPA может не получить доступ к пограничным серверам и не сможет их проверить. Если включить пограничные серверы в проверку, а в отчетах будет содержаться информация о проблеме с доступом к пограничным серверам, снимите флажок <STRONG>Пограничные серверы</STRONG> и выполните проверку еще раз, чтобы проблема не отображалась в отчетах.</span><span class="sxs-lookup"><span data-stu-id="957da-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="957da-112">Устранение неполадок с топологией</span><span class="sxs-lookup"><span data-stu-id="957da-112">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="957da-113">Если при тестировании топологии были найдены ошибки, они, вероятно, вызваны проблемами, которые возникли при публикации или включении топологии.</span><span class="sxs-lookup"><span data-stu-id="957da-113">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="957da-114">При внесении изменений в топологию они применяются только после публикации и включении топологии.</span><span class="sxs-lookup"><span data-stu-id="957da-114">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="957da-115">Для внесения изменений в топологию необходимо использовать построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="957da-115">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="957da-116">После внесения изменений можно опубликовать и включить эти изменения с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="957da-116">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="957da-117">При публикации изменений в центральном хранилище управления записывается новая информация (например, новый сайт или новая роль сервера).</span><span class="sxs-lookup"><span data-stu-id="957da-117">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="957da-118">Однако эти новые (или только что измененные) объекты не присоединяются к топологии сразу же.</span><span class="sxs-lookup"><span data-stu-id="957da-118">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="957da-119">Объекты присоединяются к топологии только при включении обновленной топологии.</span><span class="sxs-lookup"><span data-stu-id="957da-119">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="957da-120">Если выбрать параметр Опубликовать в построителе топологий, выполняются оба этих действия: изменения публикуются (то есть они записываются в хранилище Центрального управления), а затем Новая топология включена.</span><span class="sxs-lookup"><span data-stu-id="957da-120">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="957da-121">По умолчанию участники группы RTCUniversalServerAdmins имеют право на выполнение командлетов **Publish-CsTopology** и **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="957da-121">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="957da-122">Но если разрешения установки не были делегированы, для запуска **Publish-CsTopology** необходимо войти в систему как администратор домена.</span><span class="sxs-lookup"><span data-stu-id="957da-122">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="957da-123">Чтобы предоставить RTCUniversalServerAdmins право на фактическое использование командлета **Publish – CsTopology** , необходимо выполнить командлет **Grant – CsSetupPermission** для каждого контейнера Active Directory, содержащего компьютеры, на которых работают службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="957da-123">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="957da-124">Чтобы предоставить RTCUniversalServerAdmins право на использование командлета **Enable – CsTopology** , необходимо выполнить командлет **Set – CsSetupPermission** для каждого контейнера доменных служб Active Directory, содержащего компьютеры, на которых работают службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="957da-124">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="957da-125">Обратите внимание, что это относится к разрешении и публикации топологии с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="957da-125">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="957da-126">Если у вас нет делегированных разрешений с помощью **Set – CsSetupPermission**, только администратор домена может включить и опубликовать топологию с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="957da-126">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


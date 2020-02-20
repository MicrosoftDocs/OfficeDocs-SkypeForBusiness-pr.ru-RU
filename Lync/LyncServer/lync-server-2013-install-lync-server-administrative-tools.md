---
title: 'Lync Server 2013: Установка средств администрирования Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7d1b29ce4bad3b5a50c59d0da6911964f9e108
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="cc5db-102">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc5db-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc5db-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cc5db-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cc5db-104">В этом разделе описывается установка средств администрирования, необходимых для развертывания и управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc5db-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="cc5db-105">Средства администрирования устанавливаются по умолчанию на каждом сервере, на котором работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc5db-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="cc5db-106">Кроме того, вы можете установить административные средства на другие компьютеры, например на выделенные административные консоли.</span><span class="sxs-lookup"><span data-stu-id="cc5db-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="cc5db-107">Настоятельно рекомендуется установить средства администрирования на компьютер, который находится в том же домене или лесу, что и сервер Lync Server 2013, который вы создаете, так как это позволяет убедиться, что этапы подготовки доменных служб Active Directory уже полная, которая позволяет позднее использовать средства администрирования на этом компьютере для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="cc5db-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="cc5db-108">Убедитесь, что вы просматриваете требования к инфраструктуре, операционной системе, программному обеспечению и правам администратора до установки или использования средств администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc5db-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="cc5db-109">Сведения о требованиях к инфраструктуре приведены [в статье требования к инфраструктуре средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc5db-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="cc5db-110">Дополнительные сведения о требованиях к операционной системе и программному обеспечению для установки средств администрирования Lync Server 2013 можно найти [в разделе Поддержка серверов и средств операционной системы в Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Дополнительные требования к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md), а также [дополнительную поддержку и требования к серверу в Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc5db-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="cc5db-111">Для получения дополнительных сведений о правах и разрешениях пользователей, необходимых для установки и использования средств, обратитесь к разделу [права и разрешения администратора, необходимые для установки и администрирования Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="cc5db-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc5db-112">Если вашей организации требуется разместить службы IIS и все веб-службы не на системном диске, вы можете изменить путь установки для файлов Lync Server в диалоговом окне программы установки.</span><span class="sxs-lookup"><span data-stu-id="cc5db-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="cc5db-113">Если вы устанавливаете файлы установки по этому пути, включая OCSCore. msi, остальные файлы Lync Server 2013 будут развернуты на этом диске.</span><span class="sxs-lookup"><span data-stu-id="cc5db-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="cc5db-114">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc5db-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="cc5db-p104">Войдите в качестве локального администратора (минимальное требование) на компьютер, на котором требуется установить средства администрирования. Если вы вошли в систему с учетной записью обычного пользователя в Windows Vista или Windows 7 и включен контроль учетных записей (UAC), вам будет предложено ввести учетные данные локального администратора или доменный эквивалент имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="cc5db-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="cc5db-117">Найдите установочный носитель на компьютере, а затем дважды щелкните \\Setup. exe\\для\\установки amd64.</span><span class="sxs-lookup"><span data-stu-id="cc5db-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="cc5db-118">Если предлагается установить Microsoft Visual C++ 2008, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="cc5db-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="cc5db-119">На странице " **Расположение установки Microsoft Lync Server 2013** " нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc5db-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="cc5db-120">Измените этот путь на другую папку или диск, если вы хотите установить файлы в другом местоположении.</span><span class="sxs-lookup"><span data-stu-id="cc5db-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cc5db-121">Если для организации требуется размещать службы IIS и все веб-службы на диске, отличном от системного диска, можно изменить путь к папке установки для файлов Lync Server 2013 в диалоговом окне программы установки.</span><span class="sxs-lookup"><span data-stu-id="cc5db-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="cc5db-122">Если вы устанавливаете файлы установки по этому пути, включая OCSCore. msi, остальные файлы Lync Server 2013 будут развернуты на этом диске.</span><span class="sxs-lookup"><span data-stu-id="cc5db-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="cc5db-p107">На странице **Лицензионное соглашение** просмотрите условия лицензионного соглашения, нажмите кнопку **Принимаю**, а затем нажмите **ОК**. Этот шаг обязателен для продолжения.</span><span class="sxs-lookup"><span data-stu-id="cc5db-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="cc5db-125">На странице **мастера развертывания Microsoft Lync Server 2013 —** **установите средства администрирования**.</span><span class="sxs-lookup"><span data-stu-id="cc5db-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="cc5db-126">После успешного завершения установки нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="cc5db-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc5db-127">См. также</span><span class="sxs-lookup"><span data-stu-id="cc5db-127">See Also</span></span>


[<span data-ttu-id="cc5db-128">Откройте Lync Server 2013 администрирование</span><span class="sxs-lookup"><span data-stu-id="cc5db-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="cc5db-129">Lync Server 2013 административные средства</span><span class="sxs-lookup"><span data-stu-id="cc5db-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


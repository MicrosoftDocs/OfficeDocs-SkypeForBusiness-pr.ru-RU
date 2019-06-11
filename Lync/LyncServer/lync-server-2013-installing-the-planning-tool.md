---
title: 'Lync Server 2013: установка средства планирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e528062d5fd04e1a11df934cbc01b2dc8c92aa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="4e035-102">Установка средства планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e035-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e035-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="4e035-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="4e035-104">Прежде чем начать разработку и планирование инфраструктуры Lync Server 2013 с помощью Microsoft Lync Server 2013, средства планирования, необходимо сначала установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="4e035-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="4e035-105">Средство планирования не нужно развертывать на рабочей станции или сервере, входящем в домен или инфраструктуру, в которой вы планируете установить Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e035-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="4e035-106">В файле readme, прилагаемом к средству планирования, подробно описаны важные сведения об установке и использовании этого средства.</span><span class="sxs-lookup"><span data-stu-id="4e035-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="4e035-107">Some of the information in the Readme file is duplicated here for clarity.</span><span class="sxs-lookup"><span data-stu-id="4e035-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e035-108">Для установки средства планирования требуется установка пользователем с правами администратора и разрешениями на компьютере, на котором оно должно быть установлено.</span><span class="sxs-lookup"><span data-stu-id="4e035-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="4e035-109">Ниже перечислены операционные системы, поддерживаемые при установке и работе средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4e035-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="4e035-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="4e035-110">Windows 8</span></span>

  - <span data-ttu-id="4e035-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4e035-111">Windows 8.1</span></span>

  - <span data-ttu-id="4e035-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4e035-112">Windows Server 2012</span></span>

  - <span data-ttu-id="4e035-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4e035-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="4e035-114">Windows 7, 32-разрядный выпуск;</span><span class="sxs-lookup"><span data-stu-id="4e035-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="4e035-115">Windows 7, 64-разрядный выпуск с применением технологии Windows on Win32 (WOW);</span><span class="sxs-lookup"><span data-stu-id="4e035-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="4e035-116">Windows Server 2008 R2, с применением технологии WOW.</span><span class="sxs-lookup"><span data-stu-id="4e035-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="4e035-117">Кроме того, для средства планирования требуется Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="4e035-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="4e035-118">После того как требования к предварительной установке выполнены, вы можете установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="4e035-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="4e035-119">Установка средства планирования</span><span class="sxs-lookup"><span data-stu-id="4e035-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="4e035-120">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="4e035-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="4e035-121">С помощью проводника или командного окна найдите каталог, в который вы загрузили установочные файлы средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4e035-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="4e035-122">Найдите Линкпланнингтул. msi.</span><span class="sxs-lookup"><span data-stu-id="4e035-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="4e035-123">В проводнике дважды щелкните файл.</span><span class="sxs-lookup"><span data-stu-id="4e035-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="4e035-124">В окне командной строки введите имя файла и нажмите клавишу **ВВОД**, чтобы запустить файл.</span><span class="sxs-lookup"><span data-stu-id="4e035-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="4e035-125">На странице приветствия **Microsoft Lync Server 2013, мастера настройки средства планирования**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e035-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="4e035-126">Просмотрите **Лицензионное соглашение**, установите флажок **Я принимаю условия лицензионного соглашения**, если вы принимаете условия использования по лицензионному соглашению, и затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e035-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="4e035-127">Выберите папку, в которую следует установить файлы средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4e035-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="4e035-128">По умолчанию используется расположение C\\: Program Files (\\x86) Microsoft Lync\\Server 2013 (планирование).</span><span class="sxs-lookup"><span data-stu-id="4e035-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="4e035-129">Если требуется изменить папку установки, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4e035-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="4e035-130">В окне **Изменение конечной папки** найдите или введите расположение для установки файлов, нажмите кнопку **ОК**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e035-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="4e035-131">Теперь Установщик готов установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="4e035-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="4e035-132">Click **Install** to begin the installation process.</span><span class="sxs-lookup"><span data-stu-id="4e035-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="4e035-133">Начнется установка, и будет отображаться ход процесса.</span><span class="sxs-lookup"><span data-stu-id="4e035-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="4e035-134">После успешного завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4e035-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="4e035-135">Средство планирования готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="4e035-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e035-136">См. также</span><span class="sxs-lookup"><span data-stu-id="4e035-136">See Also</span></span>


[<span data-ttu-id="4e035-137">Установка дополнительного программного обеспечения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e035-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


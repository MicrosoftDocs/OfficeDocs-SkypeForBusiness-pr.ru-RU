---
title: 'Lync Server 2013: Установка средства планирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5ba88a00ed00a36005f9c1a60806e18253d2ce1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="4936c-102">Установка средства планирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4936c-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4936c-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="4936c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="4936c-104">Прежде чем приступить к разработке и планированию инфраструктуры Lync Server 2013 с помощью средства планирования Microsoft Lync Server 2013, Planning Tool, необходимо сначала установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="4936c-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="4936c-105">Средство планирования не требуется развертывать на рабочей станции или сервере, входящем в домен или инфраструктуру, в которой планируется установить Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4936c-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="4936c-106">В файле readme, прилагаемом к средству планирования, описывается важная информация об установке и использовании средства.</span><span class="sxs-lookup"><span data-stu-id="4936c-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="4936c-107">Некоторые сведения в файле readme повторяются здесь для ясности.</span><span class="sxs-lookup"><span data-stu-id="4936c-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4936c-108">Для работы средства планирования необходимо установить пользователь с правами и разрешениями администратора на компьютере, на котором будет установлен инструмент.</span><span class="sxs-lookup"><span data-stu-id="4936c-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="4936c-109">Для установки и работы средства планирования поддерживаются следующие операционные системы:</span><span class="sxs-lookup"><span data-stu-id="4936c-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="4936c-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="4936c-110">Windows 8</span></span>

  - <span data-ttu-id="4936c-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4936c-111">Windows 8.1</span></span>

  - <span data-ttu-id="4936c-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4936c-112">Windows Server 2012</span></span>

  - <span data-ttu-id="4936c-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4936c-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="4936c-114">Windows 7, 32 — разрядная версия</span><span class="sxs-lookup"><span data-stu-id="4936c-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="4936c-115">Windows 7, 64-разрядный выпуск с использованием Windows в Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="4936c-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="4936c-116">Windows Server 2008 R2 с использованием WOW</span><span class="sxs-lookup"><span data-stu-id="4936c-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="4936c-117">Кроме того, для средства планирования требуется Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="4936c-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="4936c-118">После выполнения требований по предварительной установке вы можете установить средство планирования.</span><span class="sxs-lookup"><span data-stu-id="4936c-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="4936c-119">Установка средства планирования</span><span class="sxs-lookup"><span data-stu-id="4936c-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="4936c-120">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="4936c-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="4936c-121">С помощью проводника Windows или командного окна откройте каталог, в который вы скачали установочные файлы средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4936c-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="4936c-122">Откройте файл Линкпланнингтул. msi.</span><span class="sxs-lookup"><span data-stu-id="4936c-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="4936c-123">В проводнике Windows дважды щелкните файл.</span><span class="sxs-lookup"><span data-stu-id="4936c-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="4936c-124">В командной строке введите имя файла, а затем нажмите клавишу **Ввод** , чтобы запустить файл.</span><span class="sxs-lookup"><span data-stu-id="4936c-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="4936c-125">На странице приветствия в **Microsoft Lync Server 2013, мастере установки средства планирования**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4936c-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="4936c-126">Ознакомьтесь с лицензионным **соглашением**, установите флажок **я принимаю условия лицензионного соглашения** , если вы приняли условия использования в лицензионном соглашении, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4936c-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="4936c-127">Выберите место установки файлов средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4936c-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="4936c-128">Расположение по умолчанию: C\\: Program Files (\\x86) средство планирования\\Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4936c-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="4936c-129">Если вы хотите изменить расположение установки, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="4936c-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="4936c-130">В разделе **Изменение конечной папки**найдите или введите расположение для установки файлов, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4936c-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="4936c-131">Теперь Установщик готов к установке средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4936c-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="4936c-132">Нажмите кнопку **установить** , чтобы начать процесс установки.</span><span class="sxs-lookup"><span data-stu-id="4936c-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="4936c-133">Начнется установка, и отобразится ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="4936c-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="4936c-134">После успешного завершения установки нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4936c-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="4936c-135">Средство планирования готово к использованию.</span><span class="sxs-lookup"><span data-stu-id="4936c-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4936c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="4936c-136">See Also</span></span>


[<span data-ttu-id="4936c-137">Установка дополнительного программного обеспечения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4936c-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


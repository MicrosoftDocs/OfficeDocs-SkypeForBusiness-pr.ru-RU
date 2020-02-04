---
title: 'Lync Server 2013: необходимые условия для подключаемого модуля Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51fb0081188618b6a5ea2951968effb0d55c4af7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="87fb0-102">Необходимые условия для подключаемого модуля Lync VDI в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87fb0-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87fb0-103">_**Тема последнего изменения:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="87fb0-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="87fb0-104">В среде инфраструктуры виртуальных рабочих столов (VDI) виртуальные машины и локальный компьютер пользователя должны соответствовать требованиям, описанным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="87fb0-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87fb0-105">Сведения о том, как устанавливать и развертывать виртуализированную среду, можно найти в поставщике решения для виртуализации.</span><span class="sxs-lookup"><span data-stu-id="87fb0-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="87fb0-106">Сведения о развертывании виртуализованной среды на основе служб Hyper-V и удаленных рабочих столов можно найти в следующих статьях в библиотеке Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="87fb0-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="87fb0-107">Hyper-V на<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="87fb0-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="87fb0-108">Службы удаленных рабочих столов в Windows&nbsp;Server&nbsp;2008 R2 по адресу<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="87fb0-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="87fb0-109">Ниже приведены требования для виртуальных машин, запущенных на компьютере центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="87fb0-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="87fb0-110">Виртуальные машины должны быть настроены в Windows 10, Windows 8,1, Windows 8, Windows 7 или Windows Server 2008 R2 с самыми последними пакетами обновления.</span><span class="sxs-lookup"><span data-stu-id="87fb0-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="87fb0-111">Ниже приведены требования для пользователя и локального компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="87fb0-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="87fb0-112">Пользователь должен быть расположен на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87fb0-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="87fb0-113">На локальном компьютере должна быть установлена Windows Embedded Standard 7 с пакетом обновления 1 (SP1), Windows 7 с пакетом обновления 1, Windows 8, Windows 8,1 Embedded или Windows 8,1 (не внедрено).</span><span class="sxs-lookup"><span data-stu-id="87fb0-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="87fb0-114">При использовании служб удаленных рабочих столов (то есть независимо от того, является ли приложение 32-битным или 64-разрядным), должно соответствовать операционной системе разрядности локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="87fb0-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="87fb0-115">Разрядность операционной системы на локальном компьютере и операционной системы на виртуальной машине не должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="87fb0-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="87fb0-116">Если вы используете другое решение или платформу для виртуализации, ознакомьтесь с разделом, предоставленным поставщиком решений виртуализации, о требованиях к разрядности.</span><span class="sxs-lookup"><span data-stu-id="87fb0-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="87fb0-117">На локальном компьютере должна быть установлена самая свежая версия клиента удаленного доступа к удаленному рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="87fb0-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="87fb0-118">Установите последние обновления клиента служб удаленного рабочего стола (Майкрософт) или последнюю версию клиента удаленного рабочего стола другого поставщика решения виртуализации.</span><span class="sxs-lookup"><span data-stu-id="87fb0-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="87fb0-119">Последние обновления служб удаленных рабочих столов можно найти в [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)разделе.</span><span class="sxs-lookup"><span data-stu-id="87fb0-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="87fb0-120">Параметры клиента удаленного рабочего стола на локальном компьютере необходимо настроить так, чтобы звук воспроизводился на локальном компьютере, а удаленная запись была отключена.</span><span class="sxs-lookup"><span data-stu-id="87fb0-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="87fb0-121">Чтобы настроить эти параметры подключения к удаленному рабочему столу в Windows, ознакомьтесь со следующей разделом "Настройка параметров подключения к удаленному рабочему столу".</span><span class="sxs-lookup"><span data-stu-id="87fb0-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="87fb0-122">Настройка параметров подключения к удаленному рабочему столу</span><span class="sxs-lookup"><span data-stu-id="87fb0-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="87fb0-123">Чтобы подготовить подключение к удаленному рабочему столу в Windows для плагина Lync VDI, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="87fb0-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="87fb0-124">Если на локальном компьютере установлена операционная система Windows 8, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="87fb0-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="87fb0-125">Если на локальном компьютере установлена операционная система Windows 7 с пакетом обновления 1 (SP1), установите последнюю версию клиента служб удаленных рабочих столов [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)для Windows 8, которую можно найти по адресу.</span><span class="sxs-lookup"><span data-stu-id="87fb0-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="87fb0-126">Запустите клиент служб удаленных рабочих столов, выбрав в меню \*\*Пуск \*\* пункт **Подключение к удаленному рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="87fb0-127">Нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-127">Click **Options**.</span></span>

4.  <span data-ttu-id="87fb0-128">Перейдите на вкладку **Локальные ресурсы**. В разделе **Звук удаленного рабочего стола** щелкните **Параметры**, а затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="87fb0-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="87fb0-129">В разделе **Воспроизведение звука удаленного рабочего стола** выберите **Проигрывать на этом компьютере**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="87fb0-130">В разделе **Запись звука удаленного рабочего стола** выберите **Не записывать**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="87fb0-131">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-131">Click **OK**.</span></span>

5.  <span data-ttu-id="87fb0-132">Перейдите на вкладку **Взаимодействие**. В разделе **Производительность** снимите флажок **Постоянное кэширование точечных рисунков**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="87fb0-133">Откройте вкладку **Общие** . В поле **компьютер**введите имя виртуальной машины и нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="87fb0-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: необходимые условия для подключаемого модуля VDI для Lync'
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
ms.openlocfilehash: d1e5434ed445bf19d2aaeea146ba0edb7dcac04c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="a407c-102">Необходимые условия для подключаемого модуля Lync VDI в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a407c-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a407c-103">_**Последнее изменение темы:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="a407c-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="a407c-104">В среде инфраструктуры виртуальных рабочих столов виртуальные машины и локальный компьютер пользователя должны соответствовать требованиям, описанным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a407c-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a407c-p101">Обратитесь к поставщику решений виртуализации для получения сведений об установке и развертывании виртуализованной среды. Дополнительные сведения о развертывании виртуализованной среды на основе Hyper-V и служб удаленных рабочих столов см. в следующих статьях библиотеки Microsoft TechNet:</span><span class="sxs-lookup"><span data-stu-id="a407c-p101">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment. For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a407c-107">Hyper – V в<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="a407c-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="a407c-108">Службы удаленных рабочих столов в Windows&nbsp;Server&nbsp;2008 R2 по адресу<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="a407c-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="a407c-109">Ниже приведены требования для виртуальных машин, выполняемых на компьютере центра обработки данных:</span><span class="sxs-lookup"><span data-stu-id="a407c-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="a407c-110">Виртуальные машины должны быть настроены с помощью Windows 10, Windows 8,1, Windows 8, Windows 7 или Windows Server 2008 R2 с последними пакетами обновления.</span><span class="sxs-lookup"><span data-stu-id="a407c-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="a407c-111">Ниже приведены требования для пользователя и локального компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="a407c-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="a407c-112">Пользователь должен быть размещен на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a407c-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="a407c-113">Локальный компьютер должен работать под управлением Windows Embedded Standard 7 с пакетом обновления 1 (SP1), Windows 7 с пакетом обновления 1 (SP1), Windows 8, Windows 8,1 Embedded или Windows 8,1 (не внедрено).</span><span class="sxs-lookup"><span data-stu-id="a407c-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="a407c-114">При использовании служб удаленных рабочих столов (то есть независимо от того, является ли приложение 32-разрядным или 64-разрядным), должно отличаться от разрядности операционной системы локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a407c-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="a407c-115">Совпадение разрядности ОС локального компьютера и ОС виртуальной машине не является обязательным требованием.</span><span class="sxs-lookup"><span data-stu-id="a407c-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="a407c-116">Если вы используете другое решение или платформу виртуализации, обратитесь к поставщику решения виртуализации для получения рекомендаций по требования относительно разрядности.</span><span class="sxs-lookup"><span data-stu-id="a407c-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="a407c-117">На локальном компьютере должна использоваться самая последняя версия клиента удаленного рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="a407c-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="a407c-118">Установите последние обновления клиента служб удаленного рабочего стола корпорации Майкрософт или последнюю версию клиента удаленного рабочего стола поставщика решения виртуализации.</span><span class="sxs-lookup"><span data-stu-id="a407c-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="a407c-119">Последние обновления для служб удаленных рабочих столов приведены в [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)разделе.</span><span class="sxs-lookup"><span data-stu-id="a407c-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="a407c-120">На локальном компьютере параметры клиента удаленного рабочего стола должны быть настроены таким образом, чтобы звук воспроизводился на локальном компьютере, а удаленная запись отключена.</span><span class="sxs-lookup"><span data-stu-id="a407c-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="a407c-121">Чтобы настроить эти параметры для подключения к удаленному рабочему столу в Windows, ознакомьтесь со статьей "Настройка параметров подключения к удаленному рабочему столу" в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a407c-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="a407c-122">Настройка параметров подключения к удаленному рабочему столу</span><span class="sxs-lookup"><span data-stu-id="a407c-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="a407c-123">Чтобы подготовить подключение к удаленному рабочему столу в Windows для подключаемого модуля VDI для Lync, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a407c-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="a407c-124">Если локальный компьютер работает под управлением Windows 8, пропустите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="a407c-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="a407c-125">Если локальный компьютер работает под управлением Windows 7 с пакетом обновления 1 (SP1), установите последнюю версию клиента служб удаленных рабочих столов для [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)Windows 8, доступную по адресу.</span><span class="sxs-lookup"><span data-stu-id="a407c-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="a407c-126">Запустите клиент служб удаленных рабочих столов, выбрав в меню **Пуск** пункт **Подключение к удаленному рабочему столу**.</span><span class="sxs-lookup"><span data-stu-id="a407c-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="a407c-127">Нажмите кнопку **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="a407c-127">Click **Options**.</span></span>

4.  <span data-ttu-id="a407c-128">Перейдите на вкладку **Локальные ресурсы**. В разделе **Звук удаленного рабочего стола** щелкните **Параметры**, а затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a407c-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="a407c-129">В разделе **Воспроизведение звука удаленного рабочего стола** выберите **Проигрывать на этом компьютере**.</span><span class="sxs-lookup"><span data-stu-id="a407c-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="a407c-130">В разделе **Запись звука удаленного рабочего стола** выберите **Не записывать**.</span><span class="sxs-lookup"><span data-stu-id="a407c-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="a407c-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a407c-131">Click **OK**.</span></span>

5.  <span data-ttu-id="a407c-132">Перейдите на вкладку **Experience** (Взаимодействие). В разделе **Performance** (Производительность) снимите флажок **Persistent bitmap caching** (Постоянное кэширование точечных рисунков).</span><span class="sxs-lookup"><span data-stu-id="a407c-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="a407c-133">Перейдите на вкладку **Общие**. В поле **Computer** введите имя виртуальной машины, затем нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="a407c-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: поддерживаемые технологии виртуализации и известные ограничения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="44d34-102">Поддерживаемые технологии виртуализации и известные ограничения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44d34-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44d34-103">_**Тема последнего изменения:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="44d34-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="44d34-104">Подключаемый модулей Lync VDI позволяет осуществлять голосовую и видеосвязь в поддерживаемых технологиях виртуализации.</span><span class="sxs-lookup"><span data-stu-id="44d34-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="44d34-105">Это расширяет возможности, описанные в статье Microsoft Lync Server 2010 в [виртуализации клиента в техническом документе Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="44d34-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="44d34-106">В соответствии с требованиями обычной телефонной сети поддержка стандарта E911 также включена.</span><span class="sxs-lookup"><span data-stu-id="44d34-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="44d34-107">В следующих разделах описаны технологии виртуализации, поддерживаемые внешним модулем Lync VDI и известными ограничениями функций.</span><span class="sxs-lookup"><span data-stu-id="44d34-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="44d34-108">Поддержка технологий виртуализации</span><span class="sxs-lookup"><span data-stu-id="44d34-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="44d34-109">Плагин Lync VDI поддерживает весь классическое удаленное взаимодействие в сценарии личного виртуального рабочего стола, но не в сценарии подключения к удаленному рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="44d34-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="44d34-110">Эти сценарии можно описать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="44d34-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="44d34-111">**Поддерживается: персонализированные виртуальные рабочие столы или инфраструктура виртуальных рабочих столов (VDI).**    В этом сценарии каждый пользователь входит на настраиваемый виртуальный рабочий стол и может сохранять файлы на рабочем столе, которые хранятся в разных сеансах.</span><span class="sxs-lookup"><span data-stu-id="44d34-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="44d34-112">Службы удаленных рабочих столов Microsoft, представление горизонта VMware и Citrix Ксендесктоп являются реализациями, которые были протестированы для использования с Lync.</span><span class="sxs-lookup"><span data-stu-id="44d34-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="44d34-113">Сведения о специфических средах VDI и клиентском оборудовании, проверенных корпорацией Майкрософт, описаны в разделе [инфраструктура, определенная для Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="44d34-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="44d34-114">**Не поддерживается: сеансы** подключения к удаленному рабочему столу.    В этом сценарии каждый пользователь входит в общий сеанс виртуальных рабочих столов, который нельзя настроить.</span><span class="sxs-lookup"><span data-stu-id="44d34-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="44d34-115">Примеры реализации: сеансы удаленного рабочего стола от Microsoft (RDSH) и Citrix XenApp вместе с Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="44d34-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="44d34-116">Плагин Lync VDI не поддерживает другие технологии виртуализации, такие как виртуализация приложений, что позволяет использовать приложение, не требуя установки полного приложения локально.</span><span class="sxs-lookup"><span data-stu-id="44d34-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="44d34-117">Пример реализации: Citrix XenApp и Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="44d34-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="44d34-118">Потоковое использование приложений, удаленное использование приложений и смешанные режимы виртуализации (например, удаленное использование приложений в полном наборе функций удаленной работы рабочего стола) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="44d34-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="44d34-119">Чтобы разрешить расширение среды, плагин Lync VDI был разработан для использования независимых от платформы API-интерфейсов динамических виртуальных каналов (Двкс).</span><span class="sxs-lookup"><span data-stu-id="44d34-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="44d34-120">Для сценариев, которые не поддерживаются в Lync явным образом, ознакомьтесь с инструкциями по поддержке, предоставленными поставщиком решений VDI.</span><span class="sxs-lookup"><span data-stu-id="44d34-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="44d34-121">Известные ограничения функций</span><span class="sxs-lookup"><span data-stu-id="44d34-121">Known Feature Limitations</span></span>

<span data-ttu-id="44d34-122">Ниже перечислены известные ограничения при использовании Lync 2013 в среде VDI.</span><span class="sxs-lookup"><span data-stu-id="44d34-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="44d34-123">Ограниченная поддержка функций делегирования звонков и анонимного агента групп ответов.</span><span class="sxs-lookup"><span data-stu-id="44d34-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="44d34-124">Следующие функции не поддерживаются:</span><span class="sxs-lookup"><span data-stu-id="44d34-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="44d34-125">интегрированные страницы настройки аудио- и видеоустройств;</span><span class="sxs-lookup"><span data-stu-id="44d34-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="44d34-126">видео с несколькими представлениями;</span><span class="sxs-lookup"><span data-stu-id="44d34-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="44d34-127">запись бесед;</span><span class="sxs-lookup"><span data-stu-id="44d34-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="44d34-128">Службы удаленных рабочих столов (RDS).</span><span class="sxs-lookup"><span data-stu-id="44d34-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="44d34-129">Анонимное присоединение к собраниям (то есть присоединение к собраниям Lync, размещенным в Организации, которая не является федерациюм в вашей организации).</span><span class="sxs-lookup"><span data-stu-id="44d34-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="44d34-130">Использование плагина Lync VDI вместе с устройством Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="44d34-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="44d34-131">непрерывность звонка при сбое сети;</span><span class="sxs-lookup"><span data-stu-id="44d34-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="44d34-132">настраиваемые мелодии звонков и музыка при удержании звонка.</span><span class="sxs-lookup"><span data-stu-id="44d34-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="44d34-133">Плагин Lync VDI не поддерживается в среде Office 365.</span><span class="sxs-lookup"><span data-stu-id="44d34-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


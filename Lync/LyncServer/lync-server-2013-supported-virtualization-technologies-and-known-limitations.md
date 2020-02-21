---
title: 'Lync Server 2013: Поддерживаемые технологии виртуализации и известные ограничения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c81b56fd8d0922b011840aa2b3133ce05d32ad13
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="37a7a-102">Поддерживаемые технологии виртуализации и известные ограничения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37a7a-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a7a-103">_**Последнее изменение темы:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="37a7a-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="37a7a-104">Подключаемый модуль VDI для Lync позволяет осуществлять аудио и видео звонки для поддерживаемых технологий виртуализации.</span><span class="sxs-lookup"><span data-stu-id="37a7a-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="37a7a-105">Это расширяет функциональные возможности, описанные в статье Microsoft Lync Server 2010 в [клиентской виртуализации в техническом документе Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) .</span><span class="sxs-lookup"><span data-stu-id="37a7a-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="37a7a-106">В соответствии со стандартными правилами для телефонов также включена поддержка E911.</span><span class="sxs-lookup"><span data-stu-id="37a7a-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="37a7a-107">В следующих разделах описаны технологии виртуализации, поддерживаемые подключаемым модулем Lync VDI и известные ограничения функций.</span><span class="sxs-lookup"><span data-stu-id="37a7a-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="37a7a-108">Поддержка технологий виртуализации</span><span class="sxs-lookup"><span data-stu-id="37a7a-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="37a7a-109">Подключаемый модуль VDI для Lync поддерживает полноценный удаленный доступ к рабочему столу в сценарии личного виртуального рабочего стола, но не в сценарии подключения к удаленному рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="37a7a-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="37a7a-110">Эти сценарии можно описать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="37a7a-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="37a7a-111">**Поддерживается: настроенные виртуальные рабочие столы или инфраструктура виртуальных рабочих столов (VDI).**    В этом сценарии каждый пользователь входит в настраиваемый виртуальный рабочий стол и может сохранять файлы на настольном компьютере, которые хранятся в разных сеансах.</span><span class="sxs-lookup"><span data-stu-id="37a7a-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="37a7a-112">Службы удаленного рабочего стола (Майкрософт), представление горизонта VMware и Citrix XenDesktop являются реализациями, которые были протестированы для использования с Lync.</span><span class="sxs-lookup"><span data-stu-id="37a7a-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="37a7a-113">Сведения о средах VDI и клиентских аппаратных средствах, протестированных корпорацией Майкрософт, представлены в разделе [инфраструктура, квалифицированная для Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="37a7a-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="37a7a-114">**Не поддерживается: сеансы удаленного рабочего стола.**    В этом сценарии каждый пользователь выполняет вход в общий сеанс виртуального рабочего стола, который не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="37a7a-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="37a7a-115">Примеры реализации включают в себя сеансы удаленного рабочего стола Майкрософт (узлов сеансов удаленных рабочих столов) и Citrix XenApp в сочетании с получателем Citrix.</span><span class="sxs-lookup"><span data-stu-id="37a7a-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="37a7a-116">Подключаемый модуль VDI для Lync не поддерживает другие технологии виртуализации, такие как виртуализация приложений, что позволяет использовать приложение без необходимости установки полного приложения локально.</span><span class="sxs-lookup"><span data-stu-id="37a7a-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="37a7a-117">Примеры реализации включают Citrix XenApp и Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="37a7a-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="37a7a-118">Потоки приложений, удаленное взаимодействие приложений и смешанные режимы виртуализации (например, удаленное взаимодействие приложений на полном удаленном рабочем месте) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="37a7a-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="37a7a-119">Чтобы разрешить расширяемость, подключаемый модуль VDI для Lync был разработан для использования независимых от платформы API, называемых динамическими виртуальными каналами (DVC).</span><span class="sxs-lookup"><span data-stu-id="37a7a-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="37a7a-120">Для сценариев, которые не поддерживаются в Lync напрямую, ознакомьтесь со статьей поддержка от поставщика решений VDI.</span><span class="sxs-lookup"><span data-stu-id="37a7a-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="37a7a-121">Ограничения известных компонентов</span><span class="sxs-lookup"><span data-stu-id="37a7a-121">Known Feature Limitations</span></span>

<span data-ttu-id="37a7a-122">Ниже приведены известные ограничения при использовании Lync 2013 в среде VDI.</span><span class="sxs-lookup"><span data-stu-id="37a7a-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="37a7a-123">Существует ограниченная поддержка функций делегирования вызовов и анонимного агента группы ответа.</span><span class="sxs-lookup"><span data-stu-id="37a7a-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="37a7a-124">Следующие функции не поддерживаются:</span><span class="sxs-lookup"><span data-stu-id="37a7a-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="37a7a-125">интегрированные страницы настройки аудио- и видеоустройств;</span><span class="sxs-lookup"><span data-stu-id="37a7a-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="37a7a-126">Видео с несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="37a7a-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="37a7a-127">запись бесед;</span><span class="sxs-lookup"><span data-stu-id="37a7a-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="37a7a-128">Службы удаленных рабочих столов (RDS).</span><span class="sxs-lookup"><span data-stu-id="37a7a-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="37a7a-129">Анонимное присоединение к собраниям (то есть присоединение собраний Lync, размещенных в Организации, которая не поддерживает организацию).</span><span class="sxs-lookup"><span data-stu-id="37a7a-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="37a7a-130">Использование подключаемого модуля VDI для Lync и устройства Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="37a7a-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="37a7a-131">непрерывность звонка при сбое сети;</span><span class="sxs-lookup"><span data-stu-id="37a7a-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="37a7a-132">Пользовательские мелодии звонка и функции хранения музыки.</span><span class="sxs-lookup"><span data-stu-id="37a7a-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="37a7a-133">Подключаемый модуль VDI для Lync не поддерживается в среде Office 365.</span><span class="sxs-lookup"><span data-stu-id="37a7a-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


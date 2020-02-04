---
title: 'Lync Server 2013: Настройка установки клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9491e48d107d01f86d18e8154331ef3ae7e478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="e633f-102">Настройка установки клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e633f-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e633f-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e633f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e633f-104">Администраторы предприятий могут настроить установку Office 2013 на базе установщика Windows (MSI-файла) с помощью описанных в этом разделе способов.</span><span class="sxs-lookup"><span data-stu-id="e633f-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="e633f-105">Так как ни один из средств не предоставляет никаких вариантов настройки, скорее всего, вы будете использовать сочетание этих методов в развертывании Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e633f-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="e633f-106">Как минимум, вы можете использовать инструменты, описанные в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="e633f-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="e633f-107">[С помощью средства развертывания Office (OCT) в Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) вы можете настроить параметры и функции настройки для Lync и других программ Office.</span><span class="sxs-lookup"><span data-stu-id="e633f-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="e633f-108">[С помощью файла config. XML для выполнения задач установки в Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) можно указать путь к точке сетевой установки и выполнить автоматическую установку.</span><span class="sxs-lookup"><span data-stu-id="e633f-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="e633f-109">[Использование параметров командной строки программы установки в Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) для указания файла config. XML для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="e633f-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="e633f-110">[Настройка политик начальной настройки клиента в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) с помощью оснастки MMC "Редактор объектов групповой политики".</span><span class="sxs-lookup"><span data-stu-id="e633f-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="e633f-111">Скорее всего, будут другие параметры, которые нужно будет настроить при развертывании пакета продуктов Office.</span><span class="sxs-lookup"><span data-stu-id="e633f-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="e633f-112">В этом разделе представлены общие сведения о средствах настройки и обсуждаются вопросы, связанные с Lync.</span><span class="sxs-lookup"><span data-stu-id="e633f-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="e633f-113">Здесь предоставляются ссылки на подробную справку Office по каждому средству.</span><span class="sxs-lookup"><span data-stu-id="e633f-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


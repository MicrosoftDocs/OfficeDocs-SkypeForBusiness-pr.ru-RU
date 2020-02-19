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
ms.openlocfilehash: 246d21ee5052e29b451b119bf9468defc6b07ce3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="aef6b-102">Настройка установки клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aef6b-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef6b-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="aef6b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="aef6b-104">Корпоративные администраторы могут настраивать установку Office 2013 на основе установщика Windows (MSI) с помощью методов, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="aef6b-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="aef6b-105">Так как ни одно средство не предоставляет все параметры настройки, скорее всего, вы будете использовать сочетание этих методов в развертывании Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="aef6b-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="aef6b-106">По меньшей мере, при развертывании могут пригодиться средства, перечисленные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="aef6b-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="aef6b-107">[С помощью центра развертывания Office (OCT) в Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) вы можете настроить параметры установки и функции для Lync и других программ Office.</span><span class="sxs-lookup"><span data-stu-id="aef6b-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="aef6b-108">[Использование файла config. XML для выполнения задач установки в Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) для указания пути к точке сетевой установки и выполнения автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="aef6b-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="aef6b-109">[Использование параметров командной строки программы установки в Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) для указания файла config. XML, который будет использоваться во время установки.</span><span class="sxs-lookup"><span data-stu-id="aef6b-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="aef6b-110">[Настройка политик начальной загрузки клиентов в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) с помощью оснастки MMC "Редактор объектов групповой политики".</span><span class="sxs-lookup"><span data-stu-id="aef6b-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="aef6b-p102">Скорее всего, будут другие параметры, которые нужно будет настроить при развертывании пакета продуктов Office. В этом разделе дан обзор средств настройки с обсуждением аспектов, которые следует учитывать при развертывании Lync. Здесь предоставляются ссылки на подробную справку Office по каждому средству.</span><span class="sxs-lookup"><span data-stu-id="aef6b-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


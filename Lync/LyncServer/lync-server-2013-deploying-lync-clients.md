---
title: 'Lync Server 2013: развертывание клиентов Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0004e3ce0b3e00cb90fc93cee148844ebc5d4d7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="d5045-102">Развертывание клиентов Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5045-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d5045-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d5045-104">В Lync 2013 используется другой подход к развертыванию клиента.</span><span class="sxs-lookup"><span data-stu-id="d5045-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="d5045-105">В отъезде из предыдущих выпусков Lync 2013 больше не имеет собственного установщика.</span><span class="sxs-lookup"><span data-stu-id="d5045-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="d5045-106">Вместо этого Lync включен в программу установки Office 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="d5045-107">Чтобы развернуть Lync 2013 для пользователей, вы можете использовать методы установки и средства настройки Office 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="d5045-108">**Office 2013 установщик Windows** — это пакет установки на основе установщика Windows, состоящий из нескольких MSI-файлов.</span><span class="sxs-lookup"><span data-stu-id="d5045-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="d5045-109">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="d5045-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="d5045-110">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="d5045-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="d5045-111">В подразделах этого раздела описывается, как использовать и настраивать установщик Office 2013 для развертывания Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="d5045-112">**Office 2013 нажми и работай** — это программа установки, которая создает поток файлов установки Office для пользователя на портале Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5045-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="d5045-113">Администраторы могут настраивать установку с помощью средства развертывания Office для технологии "Нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="d5045-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="d5045-114">Так как Office 2013 нажми и работай в основном используется в среде Microsoft Office 365, этот метод установки не подробно описан в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d5045-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="d5045-115">Подробные сведения об использовании и настройке установки "нажми и работай" доступны в документации по набору ресурсов Office 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="d5045-116">Кроме того, администраторы могут загрузить файлы и языковые файлы Office 2013 нажми и работай в локальное расположение, что удобно, если необходимо минимизировать потребность в сети или запретить пользователям устанавливать программное обеспечение из Интернета по истечении корпоративные требования к безопасности.</span><span class="sxs-lookup"><span data-stu-id="d5045-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="d5045-117">В подразделах этого раздела основное внимание уделяется развертыванию клиентов с помощью установщика Office 2013 на основе MSI.</span><span class="sxs-lookup"><span data-stu-id="d5045-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="d5045-118">Основной ссылкой должна быть документация по набору ресурсов Office 2013, в которой подробно описывается подготовка инфраструктуры, Настройка установки и развертывание Office 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="d5045-119">Тем не менее, следует использовать документацию по Office в сочетании с подразделами этого раздела, в которых рассматриваются вопросы развертывания, характерные для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="d5045-120">Надстройка "собрание по сети" для Lync 2013, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы Outlook, устанавливается автоматически вместе с Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d5045-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="d5045-121">Программа установки Office 2013 не удаляет предыдущие версии Lync или Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="d5045-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="d5045-122">Клиент Lync 2013 устанавливается параллельно с другими клиентами Lync или Office Communicator</span><span class="sxs-lookup"><span data-stu-id="d5045-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5045-123">Содержание</span><span class="sxs-lookup"><span data-stu-id="d5045-123">In This Section</span></span>

  - [<span data-ttu-id="d5045-124">Настройка установки клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="d5045-125">Настройка поведения Lync и пользовательского интерфейса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="d5045-126">Настройка надстройки "собрание по сети" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="d5045-127">Настройка страницы присоединения к собранию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="d5045-128">Настройка поддерживаемых версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="d5045-129">Настройка режима конфиденциальности расширенных сведений о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5045-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

